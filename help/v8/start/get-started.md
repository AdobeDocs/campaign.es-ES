---
title: Introducción a la versión 8 de Campaign
description: ¿Es nuevo en Adobe Campaign? Encuentre la documentación sobre cómo poner en marcha el software y dónde comenzar con la interfaz.
feature: Overview, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d
version: Campaign v8, Campaign Classic v7
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 92%

---

# Introducción a Adobe Campaign{#gs-ac-v8}

Adobe Campaign ofrece una plataforma para elaborar experiencias multicanal para los clientes, y proporciona un entorno para la orquestación visual de la campaña, la administración de interacciones en tiempo real y la ejecución multicanal.

Adobe Campaign v8 es la herramienta de campañas de última generación creada para diversos canales de marketing como el correo electrónico, las notificaciones push, los SMS y el correo directo. Proporciona sólidas capacidades de ETL y administración de datos para ayudar a diseñar y depurar la campaña perfecta. Su motor de orquestación proporciona programas de marketing multitáctil enriquecidos con un enfoque central en los recorridos impulsados por lotes. También viene acompañado de un servidor de mensajería en tiempo real escalable que permite a los equipos de marketing enviar mensajes predefinidos basados en una carga útil inclusiva desde cualquier sistema de TI para comunicaciones como restablecimiento de contraseñas, confirmación de pedidos, recibos electrónicos y mucho más.

Adobe Campaign v8 ofrece mejoras significativas en infraestructura, seguridad, entregabilidad y monitorización. Está disponible como **Cloud Service administrado** que combina servicios con supervisión proactiva y modificación oportuna. Obtenga más información sobre Campaign Managed Cloud Services [en esta página](whats-new.md#acms-desc).

Utilice Campaign para lo siguiente:

* **Impulso de la personalización y la participación mediante una única vista accesible del cliente**
* **Integración de canales de correo electrónico, móviles, en línea y sin conexión en el recorrido del cliente**
* **Automatización de la entrega de mensajes y ofertas significativos y oportunos**

![](assets/do-not-localize/ac-capabilities.png)


>[!AVAILABILITY]
>
>Excepto cuando se menciona en las páginas, la documentación de Adobe Campaign (consola) se aplica a Campaign Classic v7 y a Campaign v8.
>
>Tenga en cuenta que algunas referencias de la documentación pueden seguir haciendo referencia a marcas anteriores, pero siguen siendo aplicables a la oferta actual.

## Perfil de cliente integrado {#integrated-customer-profile}

Los perfiles están centralizados en una potente base de datos en la nube. Existen muchos mecanismos para adquirir perfiles y desarrollar esta base de datos: recopilación en línea a través de formularios web, importación manual o automática de archivos de texto, replicación con bases de datos de compañías u otros sistemas de información. Con Adobe Campaign, puede incorporar el historial de marketing, la información de compra, las preferencias, los datos CRM y cualquier dato PII relevante en una vista consolidada para analizar y actuar en consecuencia.

En Adobe Campaign, los destinatarios son los perfiles seleccionados por defecto para enviarles contenido (correos electrónicos, SMS, etc.). Gracias a los datos de los destinatarios almacenados en la base de datos, podrá filtrar quiénes reciben la entrega y añadir datos que personalicen los contenidos que quiere enviar. Existen otros tipos de perfiles en la base de datos. Están diseñados para usos diferentes. Por ejemplo se crean perfiles semilla para probar los envíos antes de enviarlos al público objetivo final.

Los conceptos básicos de administración de perfiles se explican en [esta sección](audiences.md).

Aprenda a añadir perfiles a Campaign en [esta sección](import.md).

## Segmentación dirigida {#targeted-segmentation}

Adobe Campaign tiene funcionalidades de segmentación y direccionamiento potentes y fáciles de usar que permiten crear ofertas específicas y diferenciadas. La funcionalidad de análisis descriptivo le permite analizar la información de subida y de bajada de sus campañas de marketing, y la funcionalidad [administración de filtros](../audiences/create-filters.md) y el [editor de consultas](query-editor.md) gráfico le permiten filtrar la población de suscriptores y la muestra, o crear grupos de destino según un número ilimitado de criterios.

La funcionalidad avanzada de administración de datos amplía las características de procesamiento de datos. Simplifica y optimiza el proceso de direccionamiento incluyendo información que no se encuentra en la base de datos.

Obtenga más información sobre la segmentación y la creación de públicos en [esta sección](audiences.md).

## Orquestación de campañas en canales múltiples {#cross-channel-campaign-orchestration}

Adobe Campaign le permite diseñar y organizar campañas dirigidas y personalizadas en varios canales: correo electrónico, correo directo, SMS, notificaciones push. Una sola interfaz proporciona todas las funcionalidades necesarias para programar, organizar, configurar, personalizar, automatizar, ejecutar y medir todas las campañas y comunicaciones.

Aprenda a diseñar, programar y ejecutar una campaña en [esta sección](campaigns.md).

## Flujos de trabajo {#wf-gsv8}

Adobe Campaign ofrece un entorno gráfico completo que le permite diseñar procesos complejos, incluida la segmentación, la ejecución de campañas, el procesamiento de archivos, etc. Se puede utilizar un flujo de trabajo, por ejemplo, para descargar un archivo de un servidor, descomprimirlo y, a continuación, importar registros de la base de datos de Adobe Campaign.

Un flujo de trabajo también puede incluir usuarios asignándoles tareas o haciendo que aprueben tareas realizadas. Esto significa que puede asignar una tarea a uno o varios usuarios para que trabajen en el contenido o especifiquen objetivos, y aprobar pruebas antes de enviar el mensaje.

Los flujos de trabajo se pueden utilizar en diferentes contextos, como por ejemplo:

* Direccionamiento para administrar públicos o enviar mensajes.
* Administración de datos (ETL) para manipular datos.
* Importación de datos en la base de datos de Campaign.
* Procesos técnicos, como limpieza de bases de datos, recuperación de información de seguimiento, etc.

Aprenda a diseñar y ejecutar flujos de trabajo en [esta sección](../config/workflows.md).

## Creación de informes y análisis {#analysis-and-reporting}

Adobe Campaign permite monitorizar e interpretar el comportamiento de sus clientes mediante la mejora gradual de sus datos y perfiles. Las herramientas de análisis y creación de informes le permiten poner en marcha cada nueva campaña, segmentar mejor sus iniciativas de marketing, y optimizar el impacto y el retorno de la inversión.

Además de las potentes plantillas de creación de informes disponibles de forma predeterminada, Adobe Campaign permite crear informes personalizados en los niveles de entrega, campaña, usuario o segmento. Ejecute análisis descriptivos, resuma el retorno de la inversión o exporte datos a Adobe Analytics y otras soluciones para conseguir una visualización y análisis de los datos más profundos.

La función de creación de informes de campaña facilita la elaboración de informes dinámicos. Puede usar variables de arrastrar y soltar para personalizarlos y analizar el éxito de las campañas. Según la complejidad de las consultas y los cálculos, se pueden agregar los datos a una vista de lista o acceder a ellos en un formato que facilite la generación de informes de análisis de marketing.


Obtenga más información sobre las funciones de informes y seguimiento en [esta sección](../reporting/gs-reporting.md).

## Integraciones con Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Puede combinar las funcionalidades de envío y las funcionalidades avanzadas de administración de campañas de Adobe Campaign con un conjunto de soluciones creadas para ayudarle a personalizar la experiencia de los usuarios: Adobe Experience Manager, Adobe Analytics, Adobe Target o Adobe Experience Cloud, por ejemplo.

Aprenda a integrarse con los servicios y soluciones de Adobe en [esta sección](../connect/integration.md).

## Más información acerca de las funcionalidades de Campaign {#core-capabilities-and-add-ons}

Adobe Campaign ofrece un conjunto de funcionalidades que le ayudarán a implementar y optimizar las capacidades de marketing conversacional según sus necesidades y su arquitectura. Algunas de ellas son funcionalidades básicas y algunas dependen de la instalación de un paquete y de la configuración. Aquí encontrará una descripción detallada del producto: [Descripción del producto de Adobe Campaign Classic v8](https://helpx.adobe.com/es/legal/product-descriptions/adobe-campaign-managed-cloud-services.html).

¿Ya está familiarizado con Campaign Classic? Aprenda las diferencias clave entre Campaign Classic y Campaign versión 8 en [esta página](v7-to-v8.md).

**Consulte también**

* [Espacio de trabajo de Campaign](campaign-ui.md)
* [Matriz de compatibilidad de Campaign v8](compatibility-matrix.md)
* [Conexión a Campaign](connect.md)
* [Preguntas frecuentes](campaign-faq.md)
