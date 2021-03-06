---
title: Configuración de mensajería transaccional de Campaign
description: Configuración de mensajería transaccional de Campaign
feature: Transactional Messaging
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 22%

---

# Configuración de mensajería transaccional

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, [Adobe de contacto](../start/campaign-faq.md#support) para instalar y configurar la mensajería transaccional de Campaign en su entorno.

![](../assets/do-not-localize/glass.png) Las capacidades de mensajería transaccional se detallan en [esta sección](../send/transactional.md).

![](../assets/do-not-localize/glass.png) Comprenda la arquitectura de mensajería transaccional en [esta página](../architecture/architecture.md).

## Definir permisos

Para crear nuevos usuarios para las instancias de ejecución del Centro de Mensajes alojadas en Adobe Cloud, debe ponerse en contacto con el servicio de atención al cliente de Adobe. Los usuarios del Centro de mensajes son operadores específicos que requieren permisos específicos para acceder a las carpetas &quot;Eventos en tiempo real&quot; (nmsRtEvent).

## Extensiones de esquema

Todas las extensiones de esquema realizadas en los esquemas utilizados por **Flujos de trabajo técnicos del centro de mensajes** en las instancias de control o ejecución deben duplicarse en las demás instancias utilizadas por el módulo de mensajería transaccional de Adobe Campaign.

![](../assets/do-not-localize/book.png) Obtenga más información sobre los flujos de trabajo técnicos del centro de mensajes en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## Enviar notificaciones push transaccionales

Cuando se combina con el módulo de canal de aplicaciones móviles, la mensajería transaccional permite enviar mensajes transaccionales mediante notificaciones en dispositivos móviles.

![](../assets/do-not-localize/book.png) El canal de aplicaciones móviles se detalla en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

Para enviar notificaciones push transaccionales, debe realizar las siguientes configuraciones:

1. Instale el paquete del **Mobile App Channel** en las instancias de control y ejecución.

   >[!CAUTION]
   >
   >Compruebe el acuerdo de licencia antes de instalar un nuevo paquete integrado de Campaign.

1. Repita el **Aplicación móvil** y las aplicaciones móviles asociadas en las instancias de ejecución.

Para que Campaign envíe notificaciones push transaccionales, el evento debe contener los siguientes elementos:

* El ID del dispositivo móvil: **registrationId** para Android y **deviceToken** para iOS. Esta ID representa la “dirección” a la que se envía la notificación.
* El vínculo a la aplicación móvil o clave de integración (**uuid**), que permite recuperar información de conexión específica de la aplicación.
* El canal al que se enviará la notificación (**wishedChannel**): 41 para iOS y 42 para Android.
* Otros datos que se pueden aprovechar para la personalización.

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
