---
title: Introducción a los mensajes
description: Introducción a los mensajes
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 4c79078e32c77499f15906fc81f31ce2b26559d7
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 98%

---

# Introducción a los mensajes{#gs-ac-audiences}

Con Adobe Campaign, puede enviar campañas de canales múltiples, incluidos correos electrónicos, SMS, notificaciones push y correo postal, y medir su eficacia mediante varios informes dedicados. Estos mensajes están diseñados y enviados por medio de envíos y pueden personalizarse para cada destinatario.

Las funciones principales incluyen direccionamiento, definición y personalización de mensajes, ejecución de comunicaciones y los informes operativos asociados. El punto de acceso funcional principal es el asistente de entrega. Este punto de acceso lleva a varias funciones incluidas en Adobe Campaign.

Conozca los pasos clave para crear una entrega en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=es).

Adobe Campaign v8 incluye los siguientes canales de entrega:

* **Canal de correo electrónico**: las entregas de correo electrónico le permiten enviar correos electrónicos personalizados a la población objetivo. Obtenga más información en [esta página](../send/email.md).

* **Canal de correo directo**: las entregas de correo postal permiten generar un archivo de extracción que contenga datos sobre la población objetivo.  Obtenga más información en [esta página](../send/direct-mail.md)

* **Canal móvil**: las entregas en canales móviles permiten enviar mensajes SMS personalizados a la población objetivo.  Obtenga más información en [esta página](../send/sms.md)

* **Canal de aplicación móvil**: los envíos de aplicaciones móviles permiten enviar notificaciones a sistemas iOS y Android.  Obtenga más información en [esta página](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Elija cómo enviar los mensajes{#gs-send-msg}

Una vez creado el mensaje y diseñado y probado su contenido, puede elegir cómo desea enviarlo. Campaign ofrece un conjunto de funcionalidades para lo siguiente:

* Enviar mensajes manualmente al destinatario principal

   ![](assets/send-email.png)

   Obtenga información sobre cómo enviar mensajes en [esta sección](../send/send.md)

* Enviar mensajes asociados a una [campaña de marketing](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png)

   Obtenga información sobre cómo enviar mensajes en el contexto de una campaña en [esta sección](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=es)

* Enviar mensajes a través de un [flujo de trabajo](../config/workflows.md)

   ![](assets/send-in-a-wf.png)

   Obtenga información sobre cómo automatizar las entregas de correo electrónico en [esta página](../../automation/workflow/delivery.md)

* [Mensajes de activación ](../send/transactional.md) de un evento

* Programación de mensajes

   ![](assets/schedule-send.png)

[Caso de uso: obtenga información sobre cómo programar y enviar un correo electrónico de cumpleaños](../../automation/workflow/send-a-birthday-email.md)


## Adición de personalización{#personalization}

Los mensajes enviados por Adobe Campaign se pueden personalizar de varias formas. [Obtenga más información acerca las funcionalidades de personalización](../send/personalize.md)

Puede hacer lo siguiente:

* Insertar campos personalizados dinámicos. [Más información](../send/personalization-fields.md)
* Inserte bloques de personalización predefinidos. [Más información](../send/personalization-blocks.md)
* Cree contenido condicional. [Más información](../send/conditions.md)

## Enviar mensajes transaccionales{#gs-transac-messages}

La mensajería transaccional (Centro de mensajes) es el módulo de Campaign diseñado para gestionar mensajes de activación.

![](../assets/do-not-localize/glass.png) Obtenga más información acerca de la capacidad de los mensajes transaccionales en [esta sección](../architecture/architecture.md#transac-msg-archi)

![](../assets/do-not-localize/glass.png) Los pasos para configurar y enviar mensajes transaccionales se detallan en [esta página](../send/transactional.md)

![](../assets/do-not-localize/book.png) Descubra esta capacidad en un caso de uso completo en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=es){target="_blank"}

## Registros de seguimiento y entrega{#gs-tracking-logs}

La monitorización de las entregas una vez enviadas es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Puede monitorizarlas después de enviar una entrega, así como comprender cómo se administran los errores y las cuarentenas.

![](../assets/do-not-localize/book.png) Aprenda a monitorizar los envíos en la [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es){target="_blank"}

