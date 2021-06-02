---
product: Adobe Campaign
title: Introducción a los mensajes
description: Introducción a los mensajes
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 41ea85bc3c616ed7cdd0718ff3368aab971a5352
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 71%

---

# Introducción a los mensajes{#gs-ac-audiences}

Con Adobe Campaign, puede enviar campañas en canales múltiples incluidos correos electrónicos, SMS, notificaciones push y correo postal y medir su eficacia mediante varios informes dedicados. Estos mensajes están diseñados y enviados por medio de envíos y pueden personalizarse para cada destinatario.

Las funciones principales incluyen establecimiento de objetivos, definición y personalización de mensajes, ejecución de comunicaciones y los informes operativos asociados. El punto de acceso funcional principal es el asistente de entrega. Este punto de acceso lleva a varias funciones incluidas en Adobe Campaign.

Conozca los pasos clave para crear un envío en la [documentación del Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=es).

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
   [!DNL :arrow_upper_right:] [Aprenda a enviar mensajes](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=es)
* Enviar mensajes asociados a una [campaña de marketing](campaigns.md)
   [!DNL :arrow_upper_right:] [Obtenga información sobre cómo enviar mensajes en el contexto de una campaña](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=es).
* Enviar mensajes a través de un [flujo de trabajo](../config/workflows.md)
   [!DNL :arrow_upper_right:] [Obtenga información sobre cómo automatizar los envíos de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=es)
* [Mensajes de déclencheur ](../send/transactional.md) de un evento
   [!DNL :arrow_upper_right:] [Caso de uso: obtenga información sobre cómo enviar un correo electrónico transaccional con un archivo adjunto](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=es)
* Programación de mensajes
   [!DNL :arrow_upper_right:] [Caso de uso: obtenga información sobre cómo programar y enviar un correo electrónico de cumpleaños](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=es)


## Adición de personalización

Los mensajes enviados por Adobe Campaign se pueden personalizar de varias formas.

Puede hacer lo siguiente:

* Insertar campos de personalización dinámicos.
   [!DNL :arrow_upper_right:] Aprenda a utilizar los campos de personalización en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=es)
* Insertar bloques de personalización predefinidos.
   [!DNL :arrow_upper_right:] Descubra qué es un bloque personalizado y cómo utilizarlo en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=es)
* Cree contenido condicional.
   [!DNL :arrow_upper_right:] Aprenda a insertar contenido condicional en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=es)

## Enviar mensajes transaccionales

La mensajería transaccional (Centro de mensajes) es el módulo de Campaign diseñado para gestionar mensajes de activación.

[!DNL :bulb:] Obtenga más información acerca de la capacidad de los mensajes transaccionales en [esta sección](../dev/architecture.md#transac-msg-archi)

[!DNL :bulb:] Los pasos para configurar y enviar mensajes transaccionales se detallan en [esta página](../send/transactional.md)

[!DNL :arrow_upper_right:] Descubra esta capacidad en un caso de uso completo en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=es#transactional-messaging)

## Registros de seguimiento y entrega

La monitorización de las entregas una vez enviadas es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Puede monitorizarlas después de enviar una entrega, así como comprender cómo se administran los errores y las cuarentenas.

[!DNL :arrow_upper_right:] [Obtenga información sobre cómo monitorizar los envíos en esta sección](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es#sending-messages)


**Temas relacionados**

[!DNL :arrow_upper_right:]  [Prácticas recomendadas relacionadas con las entregas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=es)

[!DNL :arrow_upper_right:]  [Prueba y envío de un correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

[!DNL :arrow_upper_right:]  [Envíe pruebas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=es)
