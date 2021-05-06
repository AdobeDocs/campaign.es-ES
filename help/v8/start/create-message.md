---
solution: Campaign Classic
product: campaign
title: Introducción a los mensajes
description: Introducción a los mensajes
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
translation-type: tm+mt
source-git-commit: 87836271deb6bd69b7fed07108884e49a55f814a
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 27%

---

# Introducción a los mensajes{#gs-ac-audiences}

Con Adobe Campaign, puede enviar campañas en canales múltiples incluidos correos electrónicos, SMS, mensajes LINE, notificaciones push y correo postal y medir su eficacia mediante varios informes dedicados. Estos mensajes están diseñados y enviados por medio de envíos y pueden personalizarse para cada destinatario.

Las funciones principales incluyen establecimiento de objetivos, definición y personalización de mensajes, ejecución de comunicaciones y los informes operativos asociados. El punto de acceso funcional principal es el asistente de envíos. Este punto de acceso lleva a varias funciones incluidas en Adobe Campaign.

Conozca los pasos clave para crear un envío en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html).

Adobe Campaign v8 incluye los siguientes canales de envío:

* **Canal de correo electrónico**: las entregas de correo electrónico le permiten enviar correos electrónicos personalizados a la población objetivo. Obtenga más información en [esta página](../send/email.md).

* **Canal de correo postal**: las entregas de correo postal permiten generar un archivo de extracción que contenga datos sobre la población objetivo.  Obtenga más información en [esta página](../send/direct-mail.md)

* **Canal** móvil: los envíos en canales móviles permiten enviar mensajes de texto personalizados a la población objetivo.  Obtenga más información en [esta página](../send/sms.md)

* **Canal de aplicación móvil**: los envíos de aplicaciones móviles permiten enviar notificaciones a sistemas iOS y Android.  Obtenga más información en [esta página](../send/push.md)

## Elija cómo enviar los mensajes

Una vez creado el mensaje y diseñado y probado su contenido, puede elegir cómo desea enviarlo. Campaign ofrece un conjunto de funcionalidades para:

* Enviar mensajes manualmente al destinatario principal
:arrow_upper_right: [Obtenga información sobre cómo enviar mensajes](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* Enviar mensajes asociados a una [campaña de marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)
:arrow_upper_right: [Obtenga información sobre cómo enviar mensajes en el contexto de una campaña](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html).
* Enviar mensajes a través de un [flujo de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
:arrow_upper_right: [Obtenga información sobre cómo automatizar los envíos de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [Déclencheur ](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) mensajes de un evento :arrow_upper_right:  [Caso de uso: obtenga información sobre cómo enviar un correo electrónico transaccional con un archivo adjunto](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* Programación de mensajes
:arrow_upper_right: [Caso de uso: descubra cómo programar y enviar un correo electrónico de cumpleaños](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## Añadir personalización

Los mensajes enviados por Adobe Campaign se pueden personalizar de varias formas.

Puede:

* Insertar campos personalizados dinámicos.
:arrow_upper_right: Aprenda a utilizar los campos de personalización en la [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* Insertar bloques de personalización predefinidos.
:arrow_upper_right: Descubra qué es un bloque personalizado y cómo utilizarlo en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)
* Cree contenido condicional.
:arrow_upper_right: Aprenda a insertar contenido condicional en la [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)

## Enviar mensajes transaccionales

La mensajería transaccional (Centro de Mensajes) es el módulo de Campaign diseñado para administrar los mensajes de déclencheur.

:bulb: Obtenga más información sobre la capacidad de los mensajes transaccionales en [esta sección](../dev/architecture.md#transac-msg-archi)

:bulb: Los pasos para configurar y enviar mensajes transaccionales se detallan en [esta página](../send/transactional.md)

:arrow_upper_right: Descubra esta capacidad en un caso de uso completo en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)

## Registros de envío y seguimiento

La monitorización de las entregas una vez enviadas es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Puede monitorizar después de realizar un envío, así como comprender cómo se administran los errores y cuarentenas de envío.

:arrow_upper_right: [Obtenga información sobre cómo monitorizar los envíos en esta sección](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**Temas relacionados**

:arrow_upper_right:  [Prácticas recomendadas de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:arrow_upper_right:  [Pruebe y envíe un correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

:arrow_upper_right:  [Envíe pruebas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
