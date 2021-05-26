---
solution: Campaign v8
product: Adobe Campaign
title: Introducción a Campaign v8
description: Descubra las funcionalidades clave, la interfaz de usuario y las directrices globales
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 45%

---

# Introducción a Adobe Campaign{#gs-ac-v8}

Adobe Campaign proporciona una plataforma para diseñar experiencias de clientes en canales múltiples y un entorno para la organización de campañas visuales, la administración de interacciones en tiempo real y la ejecución en canales múltiples.

Utilice Campaign para:

* **** Impulse la personalización y la participación mediante una sola vista accesible del cliente
* **** Integración de canales de correo electrónico, móviles, en línea y sin conexión en el recorrido del cliente
* **** Automatizar el envío de mensajes y ofertas significativos y oportunos

![](assets/ac-capabilities.png)

## Perfil de cliente integrado {#integrated-customer-profile}

Los perfiles están centralizados en una potente base de datos en la nube. Existen muchos mecanismos para adquirir perfiles y crear esta base de datos: recopilación en línea a través de formularios web, importación manual o automática de archivos de texto, replicación con bases de datos de fabricantes u otros sistemas de información. Con Adobe Campaign, puede incorporar el historial de marketing, la información de compra, las preferencias, los datos CRM y cualquier dato PII relevante en una vista consolidada para analizar y actuar en consecuencia.

En Adobe Campaign, los destinatarios son los perfiles seleccionados por defecto para enviarles contenido (correos electrónicos, SMS, etc.). Gracias a los datos de los destinatarios almacenados en la base de datos, podrá filtrar quiénes reciben la entrega y añadir datos que personalicen los contenidos que quiere enviar. Existen otros tipos de perfiles en la base de datos. Están diseñados para usos diferentes. Por ejemplo, se crean perfiles semilla para probar el contenido antes de enviarlo al público objetivo final.

[!DNL :bulb:] Los conceptos básicos de administración de perfiles se explican en  [esta sección](audiences.md).

[!DNL :bulb:] Aprenda a añadir perfiles a Campaign en  [esta sección](import.md).

## Segmentación dirigida {#targeted-segmentation}

Adobe Campaign tiene funcionalidades de segmentación y selección de objetivos potentes y fáciles de usar, que permiten crear ofertas específicas y diferenciadas. La funcionalidad de análisis descriptivo permite analizar la información de subida y de bajada de las campañas de marketing, y la funcionalidad de filtrado y del editor gráfico de consultas permite filtrar la población de suscriptores y la muestra, o crear grupos de destino según un número ilimitado de criterios.

La funcionalidad avanzada de Gestión de datos amplía las características de procesamiento de datos. Simplifica y optimiza el proceso de segmentación incluyendo información que no se encuentra en la base de datos.

[!DNL :bulb:] Obtenga más información sobre segmentación, creación de audiencias y personalización en  [esta sección](audiences.md).

## Organización de campañas multicanal {#cross-channel-campaign-orchestration}

Adobe Campaign le permite diseñar y organizar campañas dirigidas y personalizadas en varios canales: correo electrónico, correo postal, SMS, notificaciones push. Una sola interfaz proporciona todas las funcionalidades necesarias para programar, organizar, configurar, personalizar, automatizar, ejecutar y medir todas las campañas y comunicaciones.

[!DNL :bulb:] Aprenda a diseñar, programar y ejecutar una campaña en  [esta sección](campaigns.md).

## Flujos de trabajo

Adobe Campaign ofrece un entorno gráfico completo que le permite diseñar procesos complejos, incluida la segmentación, la ejecución de campañas, el procesamiento de archivos, etc. Por ejemplo, puede utilizar un flujo de trabajo para descargar un archivo de un servidor, descomprimirlo y, a continuación, importar sus registros en la base de datos de Adobe Campaign.

Un flujo de trabajo también puede incluir usuarios asignándoles tareas o haciendo que aprueben tareas realizadas. Esto significa que puede asignar una tarea a uno o varios usuarios para que trabajen en el contenido o especifiquen objetivos, y aprobar pruebas antes de enviar el mensaje.

Los flujos de trabajo se pueden utilizar en diferentes contextos, como por ejemplo:

* Segmentación para administrar audiencias o enviar mensajes.
* Gestión de datos (ETL) para manipular los datos.
* Importación de datos en la base de datos de Campaign.
* Procesos técnicos, como limpieza de bases de datos, recuperación de información de seguimiento, etc.

[!DNL :bulb:] Aprenda a diseñar y ejecutar flujos de trabajo en  [esta sección](../config/workflows.md).

## Informes y análisis {#analysis-and-reporting}

Adobe Campaign permite monitorizar e interpretar el comportamiento de sus clientes mediante la mejora gradual de sus datos y perfiles. Las herramientas de análisis y elaboración de informes le permiten poner en marcha cada nueva campaña, segmentar mejor sus iniciativas de marketing y optimizar el impacto y la rentabilidad de la inversión.

[!DNL :bulb:] Obtenga más información sobre las capacidades de informes y seguimiento en  [esta sección](reporting.md).

## Integraciones con Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Puede combinar las funcionalidades de entrega y las funcionalidades avanzadas de administración de campañas de Adobe Campaign con un conjunto de soluciones creadas para ayudarle a personalizar la experiencia de los usuarios: Adobe Experience Manager, Adobe Analytics, Adobe Target o Adobe Experience Cloud, por ejemplo.

[!DNL :bulb:] Aprenda a integrar con servicios de Adobe y soluciones en  [esta sección](../connect/integration.md).

## Más información sobre las funcionalidades de Campaign {#core-capabilities-and-add-ons}

Adobe Campaign ofrece un conjunto de funcionalidades que le ayudarán a implementar y optimizar las funcionalidades de marketing conversacional según sus necesidades y su arquitectura. Algunas de ellas son funcionalidades básicas y otras dependen de la instalación de un paquete en la configuración. Aquí puede encontrar una descripción detallada del producto: [Descripción del producto de Adobe Campaign v8](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-classic---product-description.html?lang=es).

[!DNL :bulb:] ¿Ya está familiarizado con el Campaign Classic? Aprenda las diferencias clave entre Campaign Classic y Campaign v8 en [esta página](capability-matrix.md).

## Espacio de trabajo y personalización

El espacio de trabajo de Campaign está disponible a través de la [Consola de cliente](../dev/general-architecture.md).

[!DNL :bulb:] [Obtenga más información sobre la consola de cliente de Campaign](../start/connect.md).

El espacio de trabajo de Campaign se puede adaptar según sus necesidades.

[!DNL :arrow_upper_right:]  Aprenda a utilizar el espacio de trabajo de Campaign en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html)

[!DNL :arrow_upper_right:]  Obtenga información sobre cómo personalizar listas en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)

También puede acceder a algunas funciones a través de la web.

[!DNL :bulb:] [Obtenga más información sobre Campaign Web Access](../start/connect.md#web-access).


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

Fechas y formatos de hora afectados por el idioma. Para obtener más información, consulte [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#date-and-time).

