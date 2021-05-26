---
solution: Campaign v8
product: Adobe Campaign
title: Configuración de mensajería transaccional de Campaign
description: Configuración de mensajería transaccional de Campaign
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: 4ae0c968bd68d76d7ceffb91023d5426d6a810ea
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 21%

---

# Configuración de mensajería transaccional

[!DNL :speech_balloon:] Como usuario de Cloud Services administrados,  [póngase en contacto con ](../start/campaign-faq.md#support) Adobe para instalar y configurar la mensajería transaccional de Campaign en su entorno.

[!DNL :bulb:] Las funcionalidades de mensajería transaccional se detallan en  [esta sección](../send/transactional.md).

[!DNL :bulb:] Comprenda la arquitectura de mensajería transaccional en  [esta página](../dev/architecture.md).

## Definir permisos

Para crear nuevos usuarios para las instancias de ejecución del Centro de Mensajes alojadas en Adobe Cloud, debe ponerse en contacto con el servicio de atención al cliente de Adobe. Los usuarios del Centro de mensajes son operadores específicos que requieren permisos específicos para acceder a las carpetas &quot;Eventos en tiempo real&quot; (nmsRtEvent).

## Extensiones de esquema

Todas las extensiones de esquema realizadas en los esquemas utilizados por **flujos de trabajo técnicos del centro de mensajes** en cualquiera de las instancias de control o ejecución deben duplicarse en las demás instancias utilizadas por el módulo de mensajería transaccional de Adobe Campaign.

[!DNL :arrow_upper_right:] Obtenga más información sobre los flujos de trabajo técnicos del centro de mensajes en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows)

## Enviar notificaciones push transaccionales

Cuando se combina con el módulo de canal de aplicaciones móviles, la mensajería transaccional permite enviar mensajes transaccionales mediante notificaciones en dispositivos móviles.

[!DNL :arrow_upper_right:] El canal de aplicaciones móviles se detalla en la documentación [ de ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages)Campaign Classic v7 .

Para enviar notificaciones push transaccionales, debe realizar las siguientes configuraciones:

1. Instale el paquete del **Mobile App Channel** en las instancias de control y ejecución.

   >[!CAUTION]
   >
   >Compruebe el acuerdo de licencia antes de instalar un nuevo paquete integrado de Campaign.

1. Repita el servicio **Mobile application** y las aplicaciones móviles asociadas en las instancias de ejecución.

Para que Campaign envíe notificaciones push transaccionales, el evento debe contener los siguientes elementos:

* El ID del dispositivo móvil: **registrationId** para Android y **deviceToken** para iOS. Esta ID representa la “dirección” a la que se envía la notificación.
* El vínculo a la aplicación móvil o clave de integración (**uuid**) que permite recuperar la información de conexión específica de la aplicación.
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

