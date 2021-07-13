---
product: Adobe Campaign
title: Introducción a Campaign v8
description: ¿No tiene experiencia en Campaign? Descubra cómo empezar
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 96%

---

# Introducción a Adobe Campaign{#gs-ac-v8}

Adobe Campaign ofrece una plataforma para diseñar experiencias multicanal para clientes, y proporciona un entorno para la organización visual de la campaña, la administración de interacciones en tiempo real y la ejecución multicanal.

Utilice Campaign para lo siguiente:

* **Impulso de la personalización y la participación mediante una única vista accesible del cliente**
* **Integración de canales de correo electrónico, móviles, en línea y sin conexión en el recorrido del cliente**
* **Automatización de la entrega de mensajes y ofertas significativos y oportunos**

![](assets/ac-capabilities.png)

## Perfil de cliente integrado {#integrated-customer-profile}

Los perfiles están centralizados en una potente base de datos en la nube. Existen muchos mecanismos para adquirir perfiles y crear esta base de datos: recopilación en línea a través de formularios web, importación manual o automática de archivos de texto, replicación con bases de datos de fabricantes u otros sistemas de información. Con Adobe Campaign, puede incorporar el historial de marketing, la información de compra, las preferencias, los datos CRM y cualquier dato PII relevante en una vista consolidada para analizar y actuar en consecuencia.

En Adobe Campaign, los destinatarios son los perfiles seleccionados por defecto para enviarles contenido (correos electrónicos, SMS, etc.). Gracias a los datos de los destinatarios almacenados en la base de datos, podrá filtrar quiénes reciben la entrega y añadir datos que personalicen los contenidos que quiere enviar. Existen otros tipos de perfiles en la base de datos. Están diseñados para usos diferentes. Por ejemplo, se crean perfiles semilla para probar el contenido antes de enviarlo al público objetivo final.

?? Los conceptos básicos de administración de perfiles se explican en [esta sección](audiences.md).

?? Aprenda a añadir perfiles a Campaign en [esta sección](import.md).

## Segmentación dirigida {#targeted-segmentation}

Adobe Campaign tiene funcionalidades de segmentación y direccionamiento potentes y fáciles de usar que permiten crear ofertas específicas y diferenciadas. La funcionalidad de análisis descriptivo permite analizar la información de subida y de bajada de las campañas de marketing, mientras que la funcionalidad de filtrado y del editor gráfico de consultas permiten filtrar la población de suscriptores y la muestra, o crear grupos de destino según un número ilimitado de criterios.

La funcionalidad avanzada de administración de datos amplía las características de procesamiento de datos. Simplifica y optimiza el proceso de direccionamiento incluyendo información que no se encuentra en la base de datos.

?? Obtenga más información acerca de la segmentación, creación de audiencias y personalización en [esta sección](audiences.md).

## Organización de campañas en canales múltiples {#cross-channel-campaign-orchestration}

Adobe Campaign le permite diseñar y organizar campañas dirigidas y personalizadas en varios canales: correo electrónico, correo directo, SMS, notificaciones push. Una sola interfaz proporciona todas las funcionalidades necesarias para programar, organizar, configurar, personalizar, automatizar, ejecutar y medir todas las campañas y comunicaciones.

?? Aprenda a diseñar, programar y ejecutar una campaña en [esta sección](campaigns.md).

## Flujos de trabajo

Adobe Campaign ofrece un entorno gráfico completo que le permite diseñar procesos complejos, incluida la segmentación, la ejecución de campañas, el procesamiento de archivos, etc. Se puede utilizar un flujo de trabajo, por ejemplo, para descargar un archivo de un servidor, descomprimirlo y, a continuación, importar registros de la base de datos de Adobe Campaign.

Un flujo de trabajo también puede incluir usuarios asignándoles tareas o haciendo que aprueben tareas realizadas. Esto significa que puede asignar una tarea a uno o varios usuarios para que trabajen en el contenido o especifiquen objetivos, y aprobar pruebas antes de enviar el mensaje.

Los flujos de trabajo se pueden utilizar en diferentes contextos, como por ejemplo:

* Direccionamiento para administrar audiencias o enviar mensajes.
* Administración de datos (ETL) para manipular datos.
* Importación de datos en la base de datos de Campaign.
* Procesos técnicos, como limpieza de bases de datos, recuperación de información de seguimiento, etc.

?? Aprenda a diseñar y ejecutar flujos de trabajo en [esta sección](../config/workflows.md).

## Creación de informes y análisis {#analysis-and-reporting}

Adobe Campaign permite monitorizar e interpretar el comportamiento de sus clientes mediante la mejora gradual de sus datos y perfiles. Las herramientas de análisis y creación de informes le permiten poner en marcha cada nueva campaña, segmentar mejor sus iniciativas de marketing, y optimizar el impacto y el retorno de la inversión.

?? Obtenga más información acerca de las capacidades de informes y seguimiento en [esta sección](reporting.md).

## Integraciones con Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Puede combinar las funcionalidades de envío y las funcionalidades avanzadas de administración de campañas de Adobe Campaign con un conjunto de soluciones creadas para ayudarle a personalizar la experiencia de los usuarios: Adobe Experience Manager, Adobe Analytics, Adobe Target o Adobe Experience Cloud, por ejemplo.

?? Aprenda a integrar con servicios y soluciones de Adobe en [esta sección](../connect/integration.md).

## Más información acerca de las funcionalidades de Campaign {#core-capabilities-and-add-ons}

Adobe Campaign ofrece un conjunto de funcionalidades que le ayudarán a implementar y optimizar las capacidades de marketing conversacional según sus necesidades y su arquitectura. Algunas de ellas son funcionalidades básicas y algunas dependen de la instalación de un paquete y de la configuración. Aquí encontrará una descripción detallada del producto: [Descripción del producto de Adobe Campaign Classic v8](https://helpx.adobe.com/es/legal/product-descriptions/adobe-campaign-managed-cloud-services.html).

?? ¿Ya está familiarizado con el Campaign Classic? Aprenda las diferencias clave entre Campaign Classic y Campaign v8 en [esta página](capability-matrix.md).

## Espacio de trabajo y personalización

El espacio de trabajo de Campaign está disponible a través de la [consola del cliente](../dev/general-architecture.md).

![](assets/home-page.png)

?? [Obtenga más información sobre la consola del cliente de Campaign](../start/connect.md).

El espacio de trabajo de Campaign se puede adaptar según sus necesidades.

↗️ Aprenda a utilizar el espacio de trabajo de Campaign en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=es){target=&quot;_blank&quot;}

↗️ Aprenda a personalizar listas en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=es){target=&quot;_blank&quot;}

También puede acceder a algunas funciones a través de la web.

?? [Obtenga más información acerca de Campaign Web Access](../start/connect.md#web-access).


## Idiomas

La interfaz de usuario de Campaign v8 está disponible en los siguientes idiomas:

* Inglés (RU)
* Inglés (EE. UU.)
* Francés
* Alemán
* Japonés

El idioma se selecciona durante el proceso de instalación.

>[!CAUTION]
>
>No se puede cambiar el idioma después de la creación de la instancia.

Fechas y formatos de hora afectados por el idioma. Para obtener más información, consulte la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=es#date-and-time){target=&quot;_blank&quot;}.

**Consulte también**

* [Matriz de compatibilidad de Campaign v8](compatibility-matrix.md)
* [Conexión a Campaign](connect.md)
* [Preguntas frecuentes](campaign-faq.md)