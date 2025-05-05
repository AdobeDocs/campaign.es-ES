---
title: Transición de Campaign Classic v7 a Campaign v8
description: Descubra las diferencias entre la versión 7 de Campaign Classic y la versión 8 de Campaign.
feature: Overview
role: User
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 76%

---

# Transición de [!DNL Campaign Classic] v7 a [!DNL Campaign] v8{#gs-matrix}

Como antiguo usuario de la versión 7 de [!DNL Campaign Classic], no debería sufrir grandes cambios en la forma en que usa [!DNL Adobe Campaign]. La mayoría de los cambios de la versión 8 no son visibles, excepto los pequeños cambios que aparecen en la IU y en los pasos de configuración.

>[!AVAILABILITY]
>
>* Por ahora, Campaign v8 **solo** está disponible como servicio en la nube administrado y no se puede implementar en entornos locales o híbridos. [Más información](#cloud-services)
>
>* La migración automatizada desde el entorno de la versión 7 de Campaign Classic existente aún no está disponible.


## Managed Cloud Services{#cloud-services}

La versión 8 de Adobe Campaign está disponible como **servicio en la nube administrado**.

Adobe Campaign Managed Cloud Services ofrece una plataforma de servicios administrados para diseñar experiencias multicanal para los clientes y proporciona un entorno para la orquestación visual de la campaña, la administración de interacciones en tiempo real y la ejecución multicanal. Obtenga más información acerca de Campaign Managed Cloud Services en la [página de descripción del producto](https://helpx.adobe.com/es/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

La nueva oferta combina los mejores servicios con supervisión proactiva y alertas oportunas, centrándose en tres áreas:

* **Agilidad de la nube**: automatización por Adobe, con implementaciones de nube optimizadas y estandarizadas para obtener un rendimiento más predecible, una buena agilidad y una productividad de autoservicio mejorada.
* **Experiencia del servicio**: disponibilidad proactiva, capacidad y supervisión y respuesta del rendimiento para prevenir interrupciones, resolver incidentes más rápidamente y revisar el servicio regularmente para mejorar continuamente.
* **Experiencia en campañas profundas**: servicio de alta afinidad de equipos expertos en ingeniería de clientes para satisfacer las necesidades funcionales, técnicas o de capacidad de envío, reducir el riesgo de implementación y mejorar la administración de cambios.

Como antiguo usuario de [!DNL Campaign Classic], tenga en cuenta que la mayoría de las funciones de la versión 7 de [!DNL Campaign Classic] están disponibles en la versión 8 de [!DNL Campaign], excepto un pequeño conjunto de ellas, que se enumeran en [esta sección](#gs-removed).

>La nueva arquitectura de la nube permite a Campaign optimizar los procesos, reducir los costes, administrar los riesgos y mejorar la seguridad de los datos. Su entorno de Campaign v8 viene con una nube privada virtual (VPC) dedicada preconfigurada para usted.


## Arquitectura híbrida {#hybrid-archi}

La versión 8 de Campaign se basa en una **arquitectura híbrida**. Si está realizando la transición desde Campaign Classic v7, tenga en cuenta que todas las entregas pasan al servidor intermediario.

Como consecuencia:

* El enrutamiento interno es **no es posible** en Campaign v8, y la cuenta externa se ha deshabilitado en consecuencia,
* El estado de los envíos no se actualiza instantáneamente: se ejecuta un proceso técnico en la instancia de Marketing que actualizará los estados de entrega de forma oportuna.


Obtenga más información acerca del envío de pruebas de mensajes transaccionales al realizar la transición desde la versión 7 en [esta página](../send/transactional-template.md#transition-from-v7).


## [!DNL Campaign] y [!DNL Snowflake] {#ac-gs-snowflake}

En su implementación [Enterprise (FDAC) Deployment](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 funciona con dos bases de datos: una base de datos [!DNL Campaign] local para la mensajería en tiempo real y consultas unitarias y escritura a través de API de la interfaz de usuario, y una base de datos [!DNL Snowflake] de la nube para la ejecución de campañas, consultas por lotes y la ejecución del flujo de trabajo.

La versión 8 de Campaign Enterprise incorpora el concepto de **Acceso de datos federado completo** (FDAC): todos los datos ahora son remotos en la base de datos en la nube. Con esta nueva arquitectura, la implementación de Campaign v8 Enterprise (FDAC) simplifica la administración de datos: no se requiere ningún índice en la base de datos en la nube. Basta con crear las tablas, copiar los datos y empezar. La tecnología de la base de datos en la nube no requiere ningún mantenimiento específico para garantizar el nivel de rendimiento.

Obtenga más información acerca de la arquitectura de [!DNL Campaign] v8 en [esta página](../architecture/architecture.md).


## Utilice su Adobe ID para conectarse a Campaign{#adobe-id}

Los usuarios de Campaign solo se conectan mediante su Adobe ID. El mismo Adobe ID se utiliza para mantener todos sus planes de Adobe y productos asociados a una sola cuenta, para todas las soluciones de Adobe Experience Cloud.

Aprenda a conectarse a [!DNL Campaign] en [esta página](connect.md).

## Analizar datos con cubos{#adobe-reporting}

Utilice el módulo Marketing Analytics para analizar y medir datos, calcular estadísticas y simplificar y optimizar la creación y el cálculo de informes. Además, cree informes y genere poblaciones objetivo: una vez identificados, se almacenan en listas que se pueden utilizar en Adobe Campaign (direccionamiento, segmentación, etc.).

Los informes cubo de Adobe Campaign versión 8 están optimizados y disponen de mejores prestaciones de escalado que la versión 7 de Campaign Classic. En ese modelo de implementación específico, las anteriores limitaciones de los cubos no se aplican en la versión 8 de Campaign. Puede obtener más información sobre los cubos en [esta sección](../../v8/reporting/gs-cubes.md).

## Funciones no disponibles{#gs-unavailable-features}

Tenga en cuenta que algunas funcionalidades no están disponibles en el contexto de una [implementación empresarial (FDAC)](../architecture/enterprise-deployment.md) de Campaign, como la siguiente:

* Administración de recursos de marketing
* Cupones
* Seguimiento web
* Encuestas

## Funciones no admitidas{#gs-removed}

Algunas funciones históricas de la versión 7 de Campaign Classic ya no son compatibles con la versión 8 de Campaign, como:

* Marketing social con Facebook
* Conector ACS (oferta principal)
* Integración con LDAP
* Inicio de sesión con usuario/contraseña
* Modelos de implementación híbridos/locales


>[!NOTE]
>
>Algunas funciones no disponibles o no admitidas siguen estando visibles en la interfaz de usuario.
