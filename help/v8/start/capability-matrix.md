---
product: Adobe Campaign
title: 'Campaign Classic v7: Matriz de capacidades de Campaign v8'
description: Comprender las diferencias entre Campaign Classic v7 y Campaign v8
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 40b38168a3704f171f1f389e2d232e6a2c6f1d85
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 45%

---

# [!DNL Campaign Classic] v7: funciones  [!DNL Campaign] v8{#gs-matrix}

Como usuario [!DNL Campaign Classic] v7 existente, no debería esperar grandes interrupciones en la forma en que normalmente interactúa con [!DNL Adobe Campaign]. La mayoría de los cambios de la versión 8 no son visibles, excepto los pequeños cambios que aparecen en la IU y en los pasos de configuración.

Cambios clave:

* Cree segmentos hasta 200 veces más rápido
* Aumente la velocidad de entrega
* Informes en tiempo real con cubos

Como usuario [!DNL Campaign Classic], tenga en cuenta que la mayoría de las funciones [!DNL Campaign Classic] v7 están disponibles con [!DNL Campaign] v8, excepto un pequeño conjunto de ellas, enumeradas en [esta sección](#gs-removed). Se incluirán más en futuras versiones. [Obtenga más información en esta sección](#gs-unavailable-features)

[!DNL :bulb:] Obtenga más información sobre la arquitectura  [!DNL Campaign] v8 en  [esta página](../dev/architecture.md).

## Cambios en la configuración del producto

### [!DNL Campaign] y [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 funciona con dos bases de datos: una base de datos local para la interfaz de usuario mensajería en tiempo real y consultas unitarias y escritura a través de API, y una base de datos de Cloud para la ejecución de campañas, consultas por lotes y la ejecución del flujo de trabajo.

Este es un cambio fundamental en la arquitectura del software. Ahora, los datos son remotos y Campaign federa todos los datos, incluidos los perfiles. [!DNL Campaign]Los procesos de ahora escalan de extremo a extremo, desde la segmentación hasta la ejecución del mensaje: la ingesta de datos, la segmentación, el direccionamiento, las consultas y las entregas ahora se ejecutan normalmente en minutos. Esta nueva versión resuelve el desafío del escalado por completo, pero mantiene el mismo nivel de flexibilidad y extensibilidad. El número de perfiles es casi ilimitado y se puede ampliar la retención de datos.

El almacenamiento en la nube se realiza en **[!DNL Snowflake]**: una nueva **cuenta externa** integrada garantiza la conectividad con la base de datos de Cloud. Está configurado por Adobe y no debe modificarse. [Más información](../config/external-accounts.md).

Cualquier esquema o tabla integrada que deba moverse o replicarse en la base de datos en la nube viene con una extensión de esquema integrada en el área de nombres **xxl.** Estas extensiones contienen cualquier modificación necesaria para mover esquemas integrados de la base de datos local [!DNL Campaign] a la base de datos de [!DNL Snowflake] Cloud y adaptar su estructura en consecuencia: nuevo UUID, vínculos actualizados, etc.

>[!CAUTION]
>
> Los datos del cliente no se almacenan en la base de datos local [!DNL Campaign]. Como consecuencia, cualquier tabla personalizada debe crearse en la base de datos en la nube.


Hay API específicas disponibles para administrar los datos entre la base de datos local y la base de datos en la nube. Descubra cómo funcionan estas nuevas API y cómo utilizarlas en [esta página](../dev/new-apis.md).

### Replicación de datos

Un flujo de trabajo técnico específico gestiona la replicación de tablas que deben estar presentes en ambos lados (base de datos local de Campaign y base de datos en la nube). Este flujo de trabajo se activa cada hora y depende de una nueva biblioteca JavaScript integrada.

>[!NOTE]
>
> Se han creado varias políticas de replicación en función del tamaño de la tabla (XS, XL, etc.).
> Algunas tablas se duplican en tiempo real, mientras que otras lo hacen cada hora. Algunas tablas sufrirán actualizaciones incrementales, mientras que otras se actualizarán por completo.


[Más información acerca de la replicación de datos](../config/replication.md)

### Administración de ID

Los objetos de Campaign v8 ahora utilizan un **ID único universal (UUID)**, que permite valores únicos ilimitados para identificar datos..

Tenga en cuenta que este ID se basa en cadenas y no en secuencias. La clave principal no es un valor numérico en Campaign v8 y debe utilizar los atributos **autouuid** y **autopk** en los esquemas.

En Campaign Classic v7 y versiones anteriores, la unicidad de una clave dentro de un esquema (es decir, una tabla) se gestiona a nivel del motor de la base de datos. De forma más general, los motores de base de datos clásicos como PostgreSQL, Oracle o SQL Server incluyen un mecanismo nativo para evitar la inserción de filas duplicadas basadas en una columna o un conjunto de columnas a través de claves principales o índices únicos. El ID duplicado no existe en estas versiones cuando el índice adecuado y las claves principales se establecen en el nivel de base de datos.

La campaña de Adobe v8 viene con el Snowflake como la base de datos principal. Como aumenta drásticamente la escala de las consultas, la arquitectura distribuida de la base de datos de Snowflake no proporciona esos mecanismos para administrar y, a continuación, hacer cumplir la unicidad de una clave dentro de una tabla. Como consecuencia, con Adobe Campaign v8, nada impide la ingesta de claves duplicadas en una tabla. Los usuarios finales ahora son responsables de garantizar la coherencia de las claves en la base de datos de Adobe Campaign. [Más información](../dev/keys.md).


### Mantenimiento simplificado

Los usuarios de Campaign no tienen que ser expertos en bases de datos: ya no es necesario realizar operaciones complejas de mantenimiento de bases de datos o indexar tablas complejas.

## Funciones no disponibles{#gs-unavailable-features}

Tenga en cuenta que algunas funciones no están disponibles en esta primera versión, como:

* Gestión de recursos de marketing
* Marketing distribuido
* Administración de ofertas entrantes (módulo de interacción)
* Optimización de la campaña
* Gestor de respuestas
* Modelos de implementación híbridos/locales

>[!CAUTION]
>
>Por ahora, Campaign v8 **solo** está disponible como Cloud Service administrado y no se puede implementar en entornos locales o híbridos.
>
>La migración desde un entorno de Campaign Classic v7 existente aún no está disponible.
>
>Si no está seguro del modelo de implementación o tiene alguna pregunta, póngase en contacto con el equipo de la cuenta.

## Funciones eliminadas{#gs-removed}

Para alinearse con la nueva arquitectura y el modelo de implementación de Campaign v8, algunas funciones históricas de Campaign Classic v7 ya no están disponibles en Campaign v8.

* Cupones
* Seguimiento web
* Encuestas
* Marketing social
* Conector ACS (oferta principal)

