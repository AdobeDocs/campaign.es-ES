---
title: Introducción a los mensajes
description: Introducción a los mensajes
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 780a29dab99ad2bda554134ca95c435b9e76b494
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 100%

---

# Introducción a los mensajes{#gs-ac-audiences}

Con Adobe Campaign, puede enviar campañas de canales múltiples, incluidos correos electrónicos, SMS, notificaciones push y correo postal, y medir su eficacia mediante varios informes dedicados. Estos mensajes están diseñados y enviados por medio de envíos y pueden personalizarse para cada destinatario.

Las funciones principales incluyen establecimiento de objetivos, definición y personalización de mensajes, ejecución de comunicaciones y los informes operativos asociados. El punto de acceso funcional principal es el asistente de entrega. Este punto de acceso lleva a varias funciones incluidas en Adobe Campaign.

Conozca los pasos clave para crear una entrega en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=es).

Adobe Campaign v8 incluye los siguientes canales de entrega:

* **Canal de correo electrónico**: las entregas de correo electrónico le permiten enviar correos electrónicos personalizados a la población objetivo. Obtenga más información en [esta página](../send/email.md).

* **Canal de correo directo**: las entregas de correo postal permiten generar un archivo de extracción que contenga datos sobre la población objetivo.  Obtenga más información en [esta página](../send/direct-mail.md)

* **Canal móvil**: las entregas en canales móviles permiten enviar mensajes SMS personalizados a la población objetivo.  Obtenga más información en [esta página](../send/sms.md)

* **Canal de aplicación móvil**: los envíos de aplicaciones móviles permiten enviar notificaciones a sistemas iOS y Android.  Obtenga más información en [esta página](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Elija cómo enviar los mensajes

Una vez creado el mensaje y diseñado y probado su contenido, puede elegir cómo desea enviarlo. Campaign ofrece un conjunto de funcionalidades para lo siguiente:

* Enviar mensajes manualmente al destinatario principal

   ![](assets/send-email.png)

   ![](../assets/do-not-localize/book.png) Aprenda a enviar mensajes en la documentación de [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=es){target=&quot;_blank&quot;}

* Enviar mensajes asociados a una [campaña de marketing](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png)

   ![](../assets/do-not-localize/book.png) Aprenda a enviar mensajes en el contexto de una campaña en la documentación de [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=es){target=&quot;_blank&quot;}

* Enviar mensajes a través de un [flujo de trabajo](../config/workflows.md)

   ![](assets/send-in-a-wf.png)

   ![](../assets/do-not-localize/book.png) Aprenda a automatizar los envíos de correo electrónico en la documentación de [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=es){target=&quot;_blank&quot;}

* [Mensajes de activación ](../send/transactional.md) de un evento
   ![](../assets/do-not-localize/book.png) [Caso de uso: obtenga información sobre cómo enviar un correo electrónico transaccional con un archivo adjunto](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=es){target=&quot;_blank&quot;}

* Programación de mensajes

   ![](assets/schedule-send.png)

   ![](../assets/do-not-localize/book.png) [Caso de uso: obtenga información sobre cómo programar y enviar un correo electrónico de cumpleaños](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=es){target=&quot;_blank&quot;}


## Adición de personalización

Los mensajes enviados por Adobe Campaign se pueden personalizar de varias formas.

Puede hacer lo siguiente:

* Inserte campos de personalización dinámicos.
   ![](../assets/do-not-localize/book.png) Aprenda a utilizar los campos de personalización en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=es){target=&quot;_blank&quot;}
* Inserte bloques de personalización predefinidos.
   ![](../assets/do-not-localize/book.png) Descubra qué es un bloque de personalización y cómo utilizarlo en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=es){target=&quot;_blank&quot;}
* Cree contenido condicional.
   ![](../assets/do-not-localize/book.png) Aprenda a insertar contenido condicional en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=es){target=&quot;_blank&quot;}

## Enviar mensajes transaccionales

La mensajería transaccional (Centro de mensajes) es el módulo de Campaign diseñado para gestionar mensajes de activación.

![](../assets/do-not-localize/glass.png) Obtenga más información acerca de la capacidad de los mensajes transaccionales en [esta sección](../dev/architecture.md#transac-msg-archi)

![](../assets/do-not-localize/glass.png) Los pasos para configurar y enviar mensajes transaccionales se detallan en [esta página](../send/transactional.md)

![](../assets/do-not-localize/book.png) Descubra esta capacidad en un caso de uso completo en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=es){target=&quot;_blank&quot;}

## Registros de seguimiento y entrega

La monitorización de las entregas una vez enviadas es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Puede monitorizarlas después de enviar una entrega, así como comprender cómo se administran los errores y las cuarentenas.

![](../assets/do-not-localize/book.png) Aprenda a monitorizar los envíos en la documentación de [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es){target=&quot;_blank&quot;}


**Temas relacionados** en la documentación del Campaign Classic v7:

* [Prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=es){target=&quot;_blank&quot;}

* [Prueba y envío de un correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html){target=&quot;_blank&quot;}

* [Envío de pruebas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=es){target=&quot;_blank&quot;}
