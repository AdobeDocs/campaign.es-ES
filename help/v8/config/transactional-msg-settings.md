---
title: Configuración de mensajería transaccional de Campaign
description: Configuración de mensajería transaccional de Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 42%

---

# Configuración de mensajería transaccional

La mensajería transaccional (Centro de mensajes) es un módulo de Campaign diseñado para gestionar mensajes activados. Más información sobre la Mensajería transaccional en [esta sección](../send/transactional.md).

Comprensión de la arquitectura de mensajería transaccional en [esta página](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) Como usuario de Managed Cloud Service, [Adobe de contacto](../start/campaign-faq.md#support) para instalar y configurar la mensajería transaccional de Campaign en su entorno.

## Definición de permisos

Para crear nuevos usuarios para las instancias de ejecución del Centro de Mensajes alojadas en Adobe Cloud, debe ponerse en contacto con el servicio de atención al cliente de Adobe. Los usuarios del Centro de Mensajes son operadores específicos que requieren permisos especiales para acceder a las carpetas &quot;Eventos en tiempo real&quot; (nmsRtEvent).

## Extensiones de esquema

Todas las extensiones de esquema realizadas en los esquemas utilizados por [Flujos de trabajo técnicos del Centro de mensajes](#technical-workflows) en cualquiera de las instancias de control o de ejecución debe duplicarse en las demás instancias que utiliza el módulo de mensajería transaccional de Adobe Campaign.

## Envío de notificaciones push transaccionales

Cuando se combina con [Módulo de canal de aplicaciones móviles](../send/push.md), la mensajería transaccional le permite insertar mensajes transaccionales mediante notificaciones en dispositivos móviles.

Para enviar notificaciones push transaccionales, debe realizar las siguientes configuraciones:

1. Instale el paquete del **Mobile App Channel** en las instancias de control y ejecución.

   >[!CAUTION]
   >
   >Compruebe el acuerdo de licencia antes de instalar un nuevo paquete integrado de Campaign.

1. Replicar el **aplicación móvil** y las aplicaciones móviles asociadas en las instancias de ejecución.

Además, el evento debe contener los siguientes elementos:

* ID del dispositivo móvil: **registrationId** para Android y **deviceToken** para iOS. Este ID representa la &quot;dirección&quot; a la que se envía la notificación.
* El vínculo a la aplicación móvil o clave de integración (**uuid**), que permite recuperar información de conexión específica de la aplicación.
* El canal al que se enviará la notificación (**wishedChannel**): 41 para iOS y 42 para Android.
* Cualquier otro dato de personalización.

A continuación se muestra un ejemplo de configuración de evento para enviar notificaciones push transaccionales:

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



## Purga de eventos {#purge-events}

Puede adaptar la configuración del asistente de implementación para configurar cuánto tiempo se guardan los datos en la base de datos.

La depuración de eventos la realiza automáticamente **Database cleanup** flujo de trabajo técnico. Este flujo de trabajo depura los eventos recibidos y almacenados en las instancias de ejecución y los eventos archivados en una instancia de control.

Utilice las flechas según corresponda para cambiar la configuración de depuración del **Eventos** (en una instancia de ejecución) y **Eventos archivados** (en una instancia de control)


## Flujos de trabajo técnicos {#technical-workflows}

Debe asegurarse de que los flujos de trabajo técnicos de las instancias de control y ejecución se hayan iniciado antes de implementar cualquier plantilla de mensaje transaccional.

A continuación, se puede acceder a estos flujos de trabajo de archivado desde la carpeta **Administration > Production > Message Center.**

### Flujos de trabajo de instancias de control {#control-instance-workflows}

En la instancia de control, se debe crear un flujo de trabajo de archivado para cada uno **[!UICONTROL Message Center execution instance]** cuenta externa. Haga clic en el botón **[!UICONTROL Create the archiving workflow]** para crear e iniciar el flujo de trabajo.

### Flujos de trabajo de instancias de ejecución {#execution-instance-workflows}

En las instancias de ejecución, debe iniciar los siguientes flujos de trabajo técnicos:

* **[!UICONTROL Processing batch events]** (internal name: **[!UICONTROL batchEventsProcessing]**): este flujo de trabajo permite desglosar eventos por lote en cola antes de relacionarlos con una plantilla de mensaje.
* **[!UICONTROL Processing real time events]** (internal name: **[!UICONTROL rtEventsProcessing]**): este flujo de trabajo permite desglosar eventos en tiempo real en cola antes de relacionarlos con una plantilla de mensaje.
* **[!UICONTROL Update event status]** (internal name: **[!UICONTROL updateEventStatus]**): este flujo de trabajo le permite atribuir un estado al evento.

  Los estados de eventos posibles son:

   * **[!UICONTROL Pending]**: el evento está en cola. Aún no se le ha asignado ninguna plantilla de mensaje.
   * **[!UICONTROL Pending delivery]**: el evento está en cola, se le ha asignado una plantilla de mensaje y la entrega lo está procesando.
   * **[!UICONTROL Sent]** : este estado se copia desde los registros de envío. Significa que el envío se realizó.
   * **[!UICONTROL Ignored by the delivery]** : este estado se copia desde los registros de envío. Significa que la entrega se ha omitido.
   * **[!UICONTROL Delivery failed]** : este estado se copia desde los registros de envío. Significa que la entrega ha fallado.
   * **[!UICONTROL Event not taken into account]**: el evento no se ha podido relacionar con una plantilla de mensaje. El evento no se va a procesar.
