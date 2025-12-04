---
title: Estados de la entrega
description: Obtenga más información acerca de los estados disponibles en su tablero de entregas
feature: Monitoring, Deliverability
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 69%

---

# Estados de la entrega {#delivery-statuses}

Una vez enviada una entrega, el tablero de entregas muestra un estado que le permite monitorizar si el envío se ha realizado correctamente. Los estados posibles se detallan en la sección siguiente.

![](assets/delivery-status.png)

Para obtener más información sobre los diferentes errores de entrega que pueden surgir y cómo resolverlos, consulte [Comprender los errores de entrega](delivery-failures.md).

**Temas relacionados:**

* [Envío y monitorización de correos electrónicos](send.md)
* [Comprender los errores de envío](delivery-failures.md)
* [Introducción a la capacidad de entrega](about-deliverability.md)

## Lista de estados de entrega {#list-delivery-statuses}

<table> 
 <thead> 
  <tr> 
   <th> Estado<br /> </th> 
   <th> Definiciones y soluciones<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Enviado<br /> </td> 
   <td> La entrega se envió correctamente al proveedor de mensajes (pero es posible que el destinatario no lo haya recibido).<br /> </td> 
  </tr> 
  <tr> 
   <td> Ignorado<br /> </td> 
   <td> No se realizó la entrega al destinatario debido a un error con su dirección. Se lo incluyó en una lista de bloqueados o en cuarentena, no se proporcionó o está duplicado. <br /> </td> 
  </tr> 
  <tr> 
   <td> Error<br /> </td> 
   <td> La entrega no ha podido llegar al destinatario debido a una dirección no válida o a que la bandeja de entrada estaba llena. También puede estar relacionado con un problema con los bloques de personalización, ya que pueden generar errores cuando los esquemas no coinciden con la asignación de entregas. Consulte <a href="delivery-failures.md" target="_blank">Comprensión de los errores de entrega</a><br /> </td> 
  </tr>
  <tr> 
   <td> Pendiente<br /> </td> 
   <td> la entrega está listo para enviarse y se va a procesar mediante el servidor de entrega (MTA). Consulte <a href="#pending-status" target="_blank">Estado pendiente</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> No aplicable<br /> </td> 
   <td> El servidor (MTA) tuvo en cuenta la entrega, pero no lo procesó.<br /> </td> 
  </tr>  
  <tr> 
   <td> Entrega cancelada<br /> </td> 
   <td> Un operador ha cancelado la entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> El proveedor de servicios lo tiene en cuenta<br /> </td> 
   <td> Para las entregas SMS, el proveedor de servicios SMS recibió la entrega.<br /> Para las entregas por correo electrónico, el mensaje se retransmitió correctamente desde Campaign al servidor de correo (MTA).</td> 
  </tr> 
  <tr> 
   <td> Se ha recibido en dispositivos móviles<br /> </td> 
   <td> El destinatario recibió el SMS en su dispositivo móvil.<br /> </td> 
  </tr>
  <tr> 
   <td> Enviado al proveedor de servicios<br /> </td> 
   <td> Se realizó la entrega al proveedor de servicios SMS, pero no se ha recibido todavía.<br />
   </td> 
  </tr> 
  <tr> 
   <td> Preparado<br /> </td> 
   <td> El estado de intermediario se utiliza solo para conectores externos como el canal móvil. Sigue al estado “Pendiente” y es el conector externo que determina el estado siguiente.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Para aprender a optimizar la entrega de los correos electrónicos de Adobe Campaign, consulte [esta sección](about-deliverability.md). Para profundizar en la capacidad de entrega, consulte la [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es).

## Estado pendiente {#pending-status}

Después de confirmar la entrega, puede ver que el estado del mismo es **[!UICONTROL Pending]**. Este estado significa que el proceso de ejecución está esperando a que estén disponibles algunos recursos.

El estado **[!UICONTROL Pending]** puede significar en primer lugar que la entrega se ha programado y está pendiente hasta la fecha determinada. Para obtener más información, consulte la sección [Programar envío](configure-and-send.md#schedule-delivery-sending).

Si el envío no se realiza y su estado sigue siendo **[!UICONTROL Pending]**, puede deberse a uno de los siguientes motivos:

* **Demasiadas campañas ejecutándose simultáneamente**

  El límite de campañas simultáneas se define en la opción **[!UICONTROL NmsOperation_LimitConcurrency]**. El valor predeterminado es 10.

  Como usuario de Cloud Services administrados, puede trabajar con Adobe para ajustar este límite si es necesario. Obtenga más información acerca de las opciones en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html){target="_blank"}.

* **Problemas de disponibilidad de recursos**

  Es posible que el MTA (Agente de Transferencia de Mensajes) esté esperando a que los recursos estén disponibles antes de procesar la entrega.

>[!NOTE]
>
>Como usuario de Cloud Services administrados de Campaign v8, la infraestructura de MTA se monitoriza y administra mediante Adobe. Si tiene problemas persistentes con envíos pendientes, póngase en contacto con el Servicio de atención al cliente de Adobe.

**Temas relacionados:**

* [Envío y monitorización de correos electrónicos](send.md#email-monitoring)
* [Comprender los errores de envío](delivery-failures.md)
* [Monitorización del entorno de Campaign](../start/monitor.md#monitor-deliveries)

