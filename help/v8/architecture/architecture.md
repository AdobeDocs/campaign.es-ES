---
title: Introducción a la arquitectura de Campaign
description: Descubra los entornos y los conceptos básicos de implementación
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 13%

---

# Introducción a la arquitectura de Campaign{#gs-ac-archi}

## Entornos {#environments}

Campaign está disponible como instancias individuales y cada instancia representa un entorno de Campaign completo.

Dos tipos de entornos disponibles con el Cloud Service de Campaign:

* **Entorno de producción**: aloja las aplicaciones para los profesionales del negocio.

* **Entorno no de producción**: se utiliza para varias pruebas de rendimiento y calidad antes de que los cambios en la aplicación se inserten en el entorno de producción.

Puede exportar e importar paquetes de un entorno a otro.

![](../assets/do-not-localize/book.png) Obtenga más información sobre los paquetes en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## Modelo de implementación{#ac-deployment}

En su [Implementación empresarial (FFDA)](enterprise-deployment.md), [!DNL Adobe Campaign] v8 funciona con dos bases de datos: un local [!DNL Campaign] base de datos para la interfaz de usuario mensajería en tiempo real y consultas unitarias, así como escritura a través de API y una nube [!DNL Snowflake] base de datos para ejecución de campañas, consultas por lotes y ejecución del flujo de trabajo.

Campaign v8 Enterprise ofrece el concepto de **Acceso a datos federados completo** (FFDA): todos los datos ahora son remotos en la base de datos de Cloud. Con esta nueva arquitectura, la implementación de Campaign v8 Enterprise (FFDA) simplifica la administración de datos: no se requiere ningún índice en la base de datos de Cloud. Basta con crear las tablas, copiar los datos y empezar. La tecnología de la base de datos en la nube no requiere un mantenimiento específico para garantizar el nivel de rendimiento.



<!--Two deployment models are available:

* **Campaign FDA [!DNL Snowflake] deployment**

In its [[!DNL Snowflake] FDA deployment](fda-deployment.md), [!DNL Adobe Campaign] v8 is connected to [!DNL Snowflake] to access data through Federated Data Access capability: you can access and process external data and information stored in your [!DNL Snowflake] database without changing the structure of Adobe Campaign data. PostgreSQL is the primary database, and Snowflake is the secondary database. You can extend your data model and store your data on Snowflake. Subsequently, you can run ETL, segmentation and reports on a large data set with outstanding performances.

* **Campaign Enterprise (FFDA) deployment**

-->

## Arquitectura del centro de mensajes{#transac-msg-archi}

La mensajería transaccional (Centro de mensajes) es el módulo de Campaign diseñado para gestionar mensajes de activación.

![](../assets/do-not-localize/glass.png) Obtenga información sobre cómo enviar mensajes transaccionales en [esta sección](../send/transactional.md).

En respuesta a una acción de un cliente en un sitio web, un evento se envía a Campaign a través de una API de REST y la plantilla de mensaje se rellena con la información o los datos proporcionados a través de la llamada de API, y se envía un mensaje transaccional en tiempo real al cliente. Estos mensajes se pueden enviar por separado o en serie por correo electrónico, SMS o notificaciones push.

En esta arquitectura específica, la celda de ejecución está separada de la instancia de control para garantizar una alta disponibilidad y una gestión de carga.

* La variable **Instancia de control** (o instancia de Marketing) la utilizan los especialistas en marketing y los equipos de TI para crear, configurar y publicar plantillas de mensajes. Esta instancia también centraliza la monitorización de eventos y el historial.

   ![](../assets/do-not-localize/glass.png) Obtenga información sobre cómo crear y publicar plantillas de mensajes en [esta sección](../send/transactional.md).

* La variable **Instancia de ejecución** recupera eventos entrantes (restablecimiento de contraseña o pedidos de un sitio web, por ejemplo) y envía mensajes personalizados. Puede haber más de una instancia de ejecución para procesar mensajes mediante el equilibrador de carga y escalar el número de eventos que se van a procesar para obtener la máxima disponibilidad.

>[!CAUTION]
>
>La instancia de control y las instancias de ejecución deben estar instaladas en diferentes equipos. No pueden compartir la misma instancia de Campaign.

![](assets/messagecenter_diagram.png)

### Autenticación

Para utilizar estas funciones, los usuarios de Adobe Campaign inician sesión en la instancia de control para crear plantillas de mensajes transaccionales, generar la vista previa del mensaje utilizando una lista de semilla, mostrar informes y supervisar instancias de ejecución.

* Instancia de ejecución única Al interactuar con una instancia de ejecución del Centro de mensajes alojada en Adobe, un sistema externo puede recuperar primero un token de sesión (que de forma predeterminada caduca en 24 horas), realizando una llamada de api al método de inicio de sesión de sesión, utilizando un inicio de sesión y una contraseña de la cuenta proporcionados.
A continuación, con el sessionToken proporcionado por la instancia de ejecución en respuesta a la llamada anterior, la aplicación externa puede hacer invocaciones de la api SOAP (rtEvents o batchEvents) para enviar comunicaciones, sin necesidad de incluir en cada llamada SOAP el inicio de sesión y la contraseña de la cuenta.

* Varias instancias de ejecución En una arquitectura de ejecución de varias celdas con varias instancias de ejecución detrás de un equilibrador de carga, el método de inicio de sesión invocado por la aplicación externa pasa por el equilibrador de carga: por este motivo, no se puede utilizar una autenticación basada en tokens. Se requiere autenticación de usuario/contraseña.

![](../assets/do-not-localize/book.png) Obtenga más información sobre los eventos de mensajería transaccional en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel)