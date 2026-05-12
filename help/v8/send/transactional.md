---
title: Mensajería transaccional de Campaign
description: Introducción a la mensajería transaccional
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
TQID: https://experienceleague.adobe.com/BJSTLxMSilUemXKftd0YVYd5-6oBumTvihQWpeFWEJU
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 59%

---

# Introducción a la mensajería transaccional{#send-transactional-messages}

La mensajería transaccional (Centro de Mensajes) es un módulo de Campaign diseñado para gestionar mensajes de activación. Estas notificaciones se generan a partir de eventos activados desde sistemas de información y pueden ser: factura, confirmación de pedido, confirmación de envío, cambio de contraseña, notificación de no disponibilidad del producto, extracto de cuenta, creación de cuenta en el sitio web, etc.

>[!NOTE]
>
>Como usuario de Cloud Services administrados, [póngase en contacto con Adobe](../start/campaign-faq.md#support){target="_blank"} para configurar la mensajería transaccional de Campaign en su entorno.

Los mensajes transaccionales se utilizan para enviar:

* notificaciones, como confirmaciones de pedidos o restablecimientos de contraseña, por ejemplo
* una respuesta individual en tiempo real a una acción del cliente
* contenido no promocional

La configuración de la mensajería transaccional se detalla en [esta sección](../config/transactional-msg-settings.md).

Comprender la arquitectura de mensajería transaccional en [esta página](../architecture/architecture.md#transac-msg-archi).

## Principio operativo de mensajería transaccional {#transactional-messaging-operating-principle}

El módulo de Mensajería transaccional de Adobe Campaign está integrado en un sistema de información que devuelve eventos que se deben modificar en mensajes transaccionales personalizados. Estos mensajes se pueden enviar por separado o en serie por correo electrónico, SMS o notificaciones push.

Por ejemplo, imaginemos que es una compañía con un sitio web en el que los clientes pueden comprar productos.

Adobe Campaign le permite enviar un correo electrónico de notificación a los clientes que han añadido productos al carro de compras. Cuando uno de ellos abandona el sitio web sin finalizar sus compras (evento externo que activa un evento de Campaign), se les envía automáticamente un correo electrónico de abandono del carro de compras (entrega de mensaje transaccional).

Los pasos principales para ponerlo en práctica se detallan a continuación:

1. [Cree un tipo de evento](#create-event-types).
1. [Cree y diseñe la plantilla de mensaje](transactional-template.md#create-message-template). Debe vincular un evento al mensaje durante este paso.
1. [Pruebe el mensaje](transactional-template.md#test-message-template).
1. [Publique la plantilla de mensaje](transactional-template.md#publish-message-template).

Una vez que haya diseñado y publicado la plantilla de mensaje transaccional, si se activa un evento correspondiente, los datos relevantes se envían a Campaign mediante los [métodos SOAP](../send/event-description.md) PushEvent y PushEvents, y la entrega se realiza a los destinatarios objetivo.

## Creación de tipos de eventos {#create-event-types}

Para asegurarse de que cada evento se pueda cambiar a un mensaje personalizado, primero debe crear **tipos de eventos**.

Al [crear una plantilla de mensaje](#create-message-template), debe seleccionar el tipo de evento que coincida con el mensaje que desea enviar.

>[!CAUTION]
>
>Debe crear tipos de eventos antes de poder utilizarlos en plantillas de mensajes.

Para crear tipos de eventos que Adobe Campaign procesará, siga los pasos a continuación:

1. Vaya a la carpeta **[!UICONTROL Administration > Platform > Enumerations]** del explorador de Campaign.
1. Seleccione la enumeración **[!UICONTROL Event type]** de la lista.
1. Haga clic en **[!UICONTROL Add]** para crear un valor de enumeración. Puede ser una confirmación de pedido, cambio de contraseña o de envío de pedido, etc.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >Cada tipo de evento coincide con un valor de enumeración **[!UICONTROL Event type]**.

1. Una vez que se hayan creado los valores de la lista desglosada, cierre la sesión y vuelva a la instancia para que la creación sea eficaz.

>[!NOTE]
>
>Más información sobre [enumeraciones](../config/enumerations.md).

Para el siguiente paso, aprende a [crear y publicar tu plantilla para mensajes transaccionales](transactional-template.md).
