---
product: Adobe Campaign
title: Introducción a la arquitectura de Campaign
description: Introducción a la arquitectura de Campaign
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 8%

---

# Introducción a la arquitectura de Campaign{#gs-ac-archi}

## Entornos

Campaign está disponible como instancias individuales y cada instancia representa un entorno de Campaign completo.

Tres tipos de entornos disponibles con el Cloud Service de Campaign:

* **Entorno** de producción: aloja las aplicaciones para los profesionales del negocio.

* **Entorno de ensayo**: se utiliza para varias pruebas de rendimiento y calidad antes de que los cambios en la aplicación se inserten en el entorno de producción.

* **Entorno** de desarrollo: permite a los desarrolladores implementar Campaign en las mismas condiciones de tiempo de ejecución que los entornos de ensayo y producción.

Puede exportar e importar paquetes de un entorno a otro.

[!DNL :arrow_upper_right:] Obtenga más información sobre los paquetes en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## Implementación intermediaria{#mid-sourcing-deployment}

La comunicación general entre servidores y procesos se realiza según el esquema siguiente:

![](assets/architecture.png)

* Los módulos de administración de ejecución y devoluciones están desactivados en la instancia.

* La aplicación está configurada para realizar la ejecución de mensajes en un servidor remoto &quot;de origen intermedio&quot; que se gestiona mediante llamadas SOAP (a través de HTTP o HTTPS).

>[!NOTE]
>
> Campaign v8 se basa en una arquitectura híbrida. Si está realizando la transición desde Campaign Classic v7, tenga en cuenta que todas las entregas pasan al servidor de mid-sourcing.
> Como consecuencia, el enrutamiento interno **no es posible** en Campaign v8 y la cuenta externa se ha deshabilitado en consecuencia.

## Arquitectura del centro de mensajes{#transac-msg-archi}

La mensajería transaccional (Centro de mensajes) es el módulo de Campaign diseñado para gestionar mensajes de activación.

[!DNL :bulb:] Aprenda a enviar mensajes transaccionales en  [esta sección](../send/transactional.md).

En respuesta a una acción de un cliente en un sitio web, un evento se envía a Campaign a través de una API de REST y la plantilla de mensaje se rellena con la información o los datos proporcionados a través de la llamada de API, y se envía un mensaje transaccional en tiempo real al cliente. Estos mensajes se pueden enviar por separado o en serie por correo electrónico, SMS o notificaciones push.

En esta arquitectura específica, la celda de ejecución está separada de la instancia de control para garantizar una alta disponibilidad y una gestión de carga.

* Los especialistas en marketing y los equipos de TI utilizan la **instancia de control** (o instancia de marketing) para crear, configurar y publicar plantillas de mensajes. Esta instancia también centraliza la monitorización de eventos y el historial.

   [!DNL :bulb:] Aprenda a crear y publicar plantillas de mensajes en  [esta sección](../send/transactional.md).

* La **Execution instance** recupera eventos entrantes (restablecimiento de contraseña o pedidos de un sitio web, por ejemplo) y envía mensajes personalizados. Puede haber más de una instancia de ejecución para procesar mensajes mediante el equilibrador de carga y escalar el número de eventos que se van a procesar para obtener la máxima disponibilidad.

>[!CAUTION]
>
>La instancia de control y las instancias de ejecución deben estar instaladas en diferentes equipos. No pueden compartir la misma instancia de Campaign.

![](assets/messagecenter_diagram.png)

[!DNL :arrow_upper_right:] La arquitectura del centro de mensajes se describe en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/transactional-messaging-architecture.html?lang=en#transactional-messaging)

### Autenticación

Para utilizar estas funciones, los usuarios de Adobe Campaign inician sesión en la instancia de control para crear plantillas de mensajes transaccionales, generar la vista previa del mensaje utilizando una lista de semilla, mostrar informes y supervisar instancias de ejecución.

* Instancia de ejecución única
Al interactuar con una instancia de ejecución del Centro de mensajes alojada en un Adobe, un sistema externo puede recuperar primero un token de sesión (que de forma predeterminada caduca en 24 horas) realizando una llamada de api al método de inicio de sesión de la sesión, utilizando un inicio de sesión de cuenta y una contraseña proporcionados.
A continuación, con el sessionToken proporcionado por la instancia de ejecución en respuesta a la llamada anterior, la aplicación externa puede hacer invocaciones de la api SOAP (rtEvents o batchEvents) para enviar comunicaciones, sin necesidad de incluir en cada llamada SOAP el inicio de sesión y la contraseña de la cuenta.

* Varias instancias de ejecución
En una arquitectura de ejecución de varias celdas con varias instancias de ejecución detrás de un equilibrador de carga, el método de inicio de sesión invocado por la aplicación externa pasa por el equilibrador de carga: por este motivo, no se puede utilizar una autenticación basada en tokens. Se requiere autenticación de usuario/contraseña.

[!DNL :arrow_upper_right:] Obtenga más información sobre los eventos de mensajería transaccional en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/event-description.html?lang=en#about-transactional-messaging-datamodel)