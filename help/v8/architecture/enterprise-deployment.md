---
title: Get started with Campaign FFDA deployment
description: Get started with Campaign FFDA deployment
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 13d19f0052880c0b0930e96441163f26038c071a
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 53%

---

# [!DNL Campaign]{#gs-ac-ffda}

[[!DNL Snowflake]](https://www.snowflake.com/)

## Ventajas {#ffda-benefits}

Campaign v8 Enterprise (FFDA) brings end-to-end scale at any step of the process, from targeting to the final reporting:

* Escalar el volumen de datos que puede gestionar (hasta 8 TB)
* Escalar el rendimiento de las consultas para segmentación y direccionamiento, pero también el consumo y la salida de datos
* Escalar la preparación del envío (de horas a minutos)

Este es un cambio fundamental en la arquitectura del software. Ahora, los datos son remotos y Campaign federa todos los datos, incluidos los perfiles. Los procesos de [!DNL Campaign] ahora escalan de extremo a extremo, desde el direccionamiento hasta la ejecución del mensaje: la ingesta de datos, la segmentación, el direccionamiento, las consultas y las entregas ahora se ejecutan normalmente en minutos. Esta nueva versión resuelve el desafío del escalado por completo, pero mantiene el mismo nivel de flexibilidad y extensibilidad. El número de perfiles es casi ilimitado y se puede ampliar la retención de datos.

El almacenamiento en la nube se realiza en **[!DNL Snowflake]**: una nueva **cuenta externa** garantiza la conectividad con la base de datos en la nube. Está configurado por Adobe y no debe modificarse. [Más información](../config/external-accounts.md)

Cualquier esquema o tabla integrada que deba moverse o replicarse en la base de datos en la nube viene con una extensión de esquema integrada en el área de nombres **xxl.** Estas extensiones contienen cualquier modificación necesaria para mover esquemas integrados de la base de datos de [!DNL Campaign] local a la base de datos de [!DNL Snowflake] en la nube y adaptar su estructura en consecuencia: nuevo UUID, vínculos actualizados, etc.

>[!CAUTION]
>
> Los datos del cliente no se almacenan en la base de datos local [!DNL Campaign]. Como consecuencia, cualquier tabla personalizada debe crearse en la base de datos en la nube.

## Campaign Enterprise (FFDA) architecture{#ffda-archi}

[](../architecture/enterprise-deployment.md)[!DNL Adobe Campaign][!DNL Campaign][!DNL Snowflake]

****

Hay API específicas disponibles para administrar los datos entre la base de datos local y la base de datos en la nube. Descubra cómo funcionan estas nuevas API y cómo utilizarlas en [esta página](new-apis.md).

General communication between servers and processes is carried out according to the following schema:

![](assets/architecture.png)

* The execution and bounce management modules are disabled on the instance.
* The application is configured to perform message execution on a remote &quot;mid-sourced&quot; server that is driven using SOAP calls (over HTTP or HTTPS).

[!DNL Snowflake]

* Store all customer data: profiles, custom data such as transactions, products, locations, etc.
* Store all events and behavior data generated or collected by Campaign, such as delivery logs, tracking logs, push registrations, etc.
* Store all data aggregates of the above.
* Store a copy (h+1) of reference tables (such as deliveries, enumerations, countries, etc.) which are used in workflows, campaigns and reports.
* Run all batch processes and workloads


The PostgreSQL database on the marketing instance is used to:

* Execute certain workloads, such as low volume APIs.
* Store all Campaign data, including delivery and campaign settings, workflow and service definitions.
* Store all built-in reference tables (enumerations, countries, etc.) [!DNL Snowflake]

   However, you cannot:
   * create customizations for customer data, for example do not create a household table in PostgreSQL, but only in Snowflake
   * store any delivery logs, tracking logs, etc. on FFDA targeting dimension.
   * store large volume of data.


The PostgreSQL database on the mid-sourcing instance is used to:

* Execute batch and real-time (RT) deliveries.
* Send delivery and tracking logs - note that delivery and tracking log IDs are UUIDs and not 32-bit IDs.
* Collect and store tracking data.


## Impacts{#ffda-impacts}

### [!DNL Campaign] Mecanismo de ensayo de API{#staging-api}

[!DNL Campaign] Batch operation is always preferred. In order to guarantee optimal performances of APIs, Campaign keeps handling API calls at the local database level.

![](../assets/do-not-localize/glass.png)[](staging.md)

### Nuevas API{#new-apis}

[!DNL Campaign] A new mechanism has also been introduced to handle API calls at the local database level to avoid latency and increase the overall performance.

![](../assets/do-not-localize/glass.png)[](new-apis.md)


### Replicación de datos{#data-replication}

Un flujo de trabajo técnico específico gestiona la replicación de tablas que deben estar presentes en ambos lados (base de datos local de Campaign y base de datos en la nube). Este flujo de trabajo se activa cada hora y depende de una nueva biblioteca JavaScript integrada.

>[!NOTE]
>
> Se han creado varias políticas de replicación en función del tamaño de la tabla (XS, XL, etc.).
> Algunas tablas se duplican en tiempo real, mientras que otras lo hacen cada hora. Algunas tablas sufrirán actualizaciones incrementales, mientras que otras se actualizarán por completo.

[Más información acerca de la replicación de datos](replication.md)

### Administración de ID{#id-mgt-ffda}

Los objetos de Campaign v8 ahora utilizan un **ID único universal (UUID)**, que permite valores únicos ilimitados para identificar datos..

Tenga en cuenta que este ID se basa en cadenas y no en secuencias. La clave principal no es un valor numérico en Campaign v8, y debe utilizar los atributos **autouuid** y **autopk** en los esquemas.

En Campaign Classic v7 y versiones anteriores, la unicidad de una clave dentro de un esquema (es decir, una tabla) se gestiona en el nivel del motor de la base de datos. De forma más general, los motores de base de datos clásicos como PostgreSQL, Oracle o SQL Server incluyen un mecanismo nativo para evitar la inserción de filas duplicadas basadas en una columna o un conjunto de columnas a través de claves principales o índices únicos. El ID duplicado no existe en estas versiones cuando el índice adecuado y las claves principales se establecen en el nivel de base de datos.

Adobe Campaign v8 viene con Snowflake como base de datos principal. Como aumenta drásticamente la escala de las consultas, la arquitectura distribuida de la base de datos de Snowflake no proporciona esos mecanismos para administrar y, a continuación, hacer cumplir la unicidad de una clave dentro de una tabla. Como consecuencia, con Adobe Campaign v8, nada impide la ingesta de claves duplicadas en una tabla. Los usuarios finales ahora son responsables de garantizar la coherencia de las claves en la base de datos de Adobe Campaign. [Más información](keys.md)

**Temas relacionados**

* [Prácticas recomendadas del modelo de datos](../dev/datamodel-best-practices.md)
