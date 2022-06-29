---
title: Transición de Campaign Classic v7 a Campaign v8
description: Comprender las diferencias entre Campaign Classic v7 y Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 6f9f3ed4d2eef28b6683bf04b81431fd6a3e3dba
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 76%

---

# Transición desde [!DNL Campaign Classic] v7 a [!DNL Campaign] v8{#gs-matrix}

Como antiguo usuario de la versión 7 de [!DNL Campaign Classic], no debería sufrir grandes cambios en la forma en que usa [!DNL Adobe Campaign]. La mayoría de los cambios de la versión 8 no son visibles, excepto los pequeños cambios que aparecen en la IU y en los pasos de configuración.

>[!AVAILABILITY]
>
>* Por ahora, Campaign v8 **solo** está disponible como Cloud Service administrado y no se puede implementar en entornos locales o híbridos. [Más información](#cloud-services)
>
>* La migración automatizada desde un entorno de Campaign Classic v7 existente aún no está disponible.



## Managed Cloud Services{#cloud-services}

La versión 8 de Adobe Campaign está disponible as a **Managed Cloud Service**.

Adobe Campaign Managed Cloud Services proporciona una plataforma de Managed Services para diseñar experiencias de clientes en varios canales y proporciona un entorno para la organización de campañas visuales, la administración de interacciones en tiempo real y la ejecución en varios canales. Obtenga más información sobre los Cloud Services administrados por campaña en la [página de descripción del producto](https://helpx.adobe.com/es/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}.

La nueva oferta combina los mejores servicios con supervisión proactiva y alertas oportunas, centrándose en tres áreas:

* **Agilidad de la nube**: automatización por Adobe, con implementaciones de nube optimizadas y estandarizadas para obtener un rendimiento más predecible, una buena agilidad y una productividad de autoservicio mejorada.
* **Experiencia del servicio**: disponibilidad proactiva, capacidad y supervisión y respuesta del rendimiento para prevenir interrupciones, resolver incidentes más rápidamente y revisar el servicio regularmente para mejorar continuamente.
* **Experiencia en campañas profundas**: servicio de alta afinidad de equipos expertos en ingeniería de clientes para satisfacer las necesidades funcionales, técnicas o de capacidad de envío, reducir el riesgo de implementación y mejorar la administración de cambios.

Como antiguo usuario de [!DNL Campaign Classic], tenga en cuenta que la mayoría de las funciones de la versión 7 de [!DNL Campaign Classic] están disponibles en la versión 8 de [!DNL Campaign], excepto un pequeño conjunto de ellas, que se enumeran en [esta sección](#gs-removed).

>[!NOTE]
>
> La versión 8 de Campaign se basa en una arquitectura híbrida. Si está realizando la transición desde la versión 7 de Campaign Classic, tenga en cuenta que todas las entregas pasan al servidor intermediario. [Más información](../architecture/architecture.md)
>
> Como consecuencia, el enrutamiento interno **no es posible** en la versión 8 de Campaign, y la cuenta externa se ha deshabilitado en consecuencia.


## [!DNL Campaign] y [!DNL Snowflake] {#ac-gs-snowflake}

La versión 8 de Campaign funciona con [!DNL Snowflake].

En su [Implementación empresarial (FFDA)](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 funciona con dos bases de datos: un local [!DNL Campaign] base de datos para la interfaz de usuario mensajería en tiempo real y consultas unitarias, así como escritura a través de API y una nube [!DNL Snowflake] base de datos para ejecución de campañas, consultas por lotes y ejecución del flujo de trabajo.

La versión 8 de Campaign Enterprise incorpora el concepto de **Acceso de datos federado completo** (FDAC): todos los datos ahora son remotos en la base de datos de Cloud. Con esta nueva arquitectura, la implementación de Campaign v8 Enterprise (FFDA) simplifica la administración de datos: no se requiere ningún índice en la base de datos de Cloud. Solo es necesario crear las tablas, copiar los datos y iniciar. La tecnología de la base de datos en la nube no requiere un mantenimiento específico para garantizar el nivel de rendimiento.

![](../assets/do-not-localize/glass.png) Obtenga más información acerca la arquitectura de la versión 8 de [!DNL Campaign] en [esta página](../architecture/architecture.md).


## Utilice su Adobe ID para conectarse a Campaign{#adobe-id}

Los usuarios de Campaign solo se conectan a través de su Adobe ID. El mismo Adobe ID se utiliza para mantener todos sus planes de Adobe y productos asociados a una sola cuenta, para todas las soluciones de Adobe Experience Cloud.

![](../assets/do-not-localize/glass.png) Obtenga más información sobre cómo conectarse a [!DNL Campaign] en [esta página](connect.md).

## Analizar datos con cubos{#adobe-reporting}

Utilice el módulo Marketing Analytics para analizar y medir datos, calcular estadísticas y simplificar y optimizar la creación y el cálculo de informes. Además, cree informes y genere poblaciones objetivo: una vez identificados, se almacenan en listas que se pueden utilizar en Adobe Campaign (direccionamiento, segmentación, etc.).

Los informes de Adobe Campaign están optimizados y traen mejores prestaciones de escalado que la versión 7 de Campaign Classic. Las limitaciones anteriores de Cubes no se aplican a la versión 8 de Campaign.

## Funciones no disponibles{#gs-unavailable-features}

Tenga en cuenta que algunas funciones aún no están disponibles en esta versión de Campaign, por ejemplo:

* Administración de recursos de marketing
* Modelos de implementación híbridos/locales


## Funciones no admitidas{#gs-removed}

Para alinearse con la nueva arquitectura y el modelo de implementación de Campaign v8, algunas funciones históricas de Campaign Classic v7 ya no están disponibles en Campaign v8. Por ejemplo:

* Cupones
* Seguimiento web
* Encuestas
* Marketing social
* Conector ACS (oferta principal)
* Integración con LDAP
* Inicio de sesión con usuario/contraseña

>[!NOTE]
>
>Algunas funciones no disponibles o no admitidas siguen estando visibles en la interfaz de usuario.
