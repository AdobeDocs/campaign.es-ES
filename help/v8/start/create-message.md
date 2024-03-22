---
title: Introducción a los mensajes
description: Introducción a los mensajes
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 93%

---

# Introducción a los mensajes{#gs-ac-audiences}

Con Adobe Campaign, puede enviar campañas de canales múltiples, incluidos correos electrónicos, SMS, notificaciones push y correo postal, y medir su eficacia mediante varios informes dedicados. Estos mensajes están diseñados y enviados por medio de envíos y pueden personalizarse para cada destinatario.

Las funciones principales incluyen direccionamiento, definición y personalización de mensajes, ejecución de comunicaciones y los informes operativos asociados. El punto de acceso funcional principal es el asistente de entrega. Este punto de acceso lleva a varias funciones incluidas en Adobe Campaign.

Adobe Campaign v8 incluye los siguientes canales de envío:

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

  Obtenga información sobre cómo enviar mensajes en el contexto de una campaña en [esta sección](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=es){target="_blank"}

* Enviar mensajes a través de un [flujo de trabajo](../config/workflows.md)

  ![](assets/send-in-a-wf.png)

  Obtenga información sobre cómo automatizar los envíos de correo electrónico en [esta página](../../automation/workflow/delivery.md)

* [Mensajes de activación ](../send/transactional.md) de un evento

* Programación de mensajes

  ![](assets/schedule-send.png)

[Caso de uso: obtenga información sobre cómo programar y enviar un correo electrónico de cumpleaños](../../automation/workflow/send-a-birthday-email.md)


## Adición de personalización{#personalization}

Los mensajes enviados por Adobe Campaign se pueden personalizar de varias formas. [Obtenga más información acerca las funcionalidades de personalización](../send/personalize.md)

Puede hacer lo siguiente:

* Insertar campos de personalización dinámicos. [Más información](../send/personalization-fields.md)
* Inserte bloques de personalización predefinidos. [Más información](../send/personalization-blocks.md)
* Cree contenido condicional. [Más información](../send/conditions.md)

## Enviar mensajes transaccionales{#gs-transac-messages}

La mensajería transaccional (Centro de mensajes) es el módulo de Campaign diseñado para gestionar mensajes de activación.

Obtenga más información acerca de la capacidad de los mensajes transaccionales en [esta sección](../architecture/architecture.md#transac-msg-archi)

Los pasos para configurar y enviar mensajes transaccionales se detallan en [esta página](../send/transactional.md)


## Registros de seguimiento y envío{#gs-tracking-logs}

La monitorización de los envíos una vez enviados es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Puede monitorizarlas después de enviar un envío, así como comprender cómo se administran los errores y las cuarentenas.

Obtenga información sobre cómo monitorizar los envíos en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es#sending-messages){target="_blank"}

