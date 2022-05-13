---
title: Campaign Transactional messaging settings
description: Campaign Transactional messaging settings
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 22%

---

# Configuración de mensajería transaccional

![](../assets/do-not-localize/speech.png)[](../start/campaign-faq.md#support)

![](../assets/do-not-localize/glass.png)[](../send/transactional.md)

![](../assets/do-not-localize/glass.png)[](../architecture/architecture.md)

## Define permissions

Para crear nuevos usuarios para las instancias de ejecución del Centro de Mensajes alojadas en Adobe Cloud, debe ponerse en contacto con el servicio de atención al cliente de Adobe. Message Center users are specific operators that require dedicated permissions to access ‘Real time events’ (nmsRtEvent) folders.

## Schema extensions

****

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## Send transactional push notifications

When combined with Mobile app channel module, transactional messaging enables you to push transactional messages through notifications on mobile devices.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages)

To send transactional push notifications, you need to perform the following configurations:

1. Instale el paquete del **Mobile App Channel** en las instancias de control y ejecución.

   >[!CAUTION]
   >
   >Check your license agreement before installing a new Campaign built-in package.

1. ****

In order for Campaign to send transactional push notifications, the event must contain the following elements:

* ******** Esta ID representa la “dirección” a la que se envía la notificación.
* ****
* El canal al que se enviará la notificación (**wishedChannel**): 41 para iOS y 42 para Android.
* Other data to leverage for personalization.

A continuación se muestra un ejemplo de un evento que contiene esta información:

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation=”none” uuid="com.adobe.NeoMiles"/>
                <ctx>
                    <deliveryTime>1:30 PM</deliveryTime>
                    <url>http://www.adobe.com</url>
                </ctx>
              </rtEvent>

         </urn:domEvent>
     </urn:PushEvent>           
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
