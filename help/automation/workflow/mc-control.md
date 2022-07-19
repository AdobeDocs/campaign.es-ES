---
product: campaign
title: Centro de mensajes (Control)
description: Centro de mensajes (Control)
feature: Workflows
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 100%

---


# Centro de mensajes (Control){#message-center-control}

El flujo de trabajo detallado a continuación está programado para ejecutarse cada hora. Se instala con el módulo **Centro de mensajes (Control)** de forma predeterminada.


<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>Nombre interno</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Centro de mensajes &lt;external_account_name&gt;<br /> </td> 
   <td> mcSynch_&lt;external_account_name&gt;<br /> </td> 
   <td> Este flujo de trabajo:<br /> 
    <ul> 
     <li> <p>recupera la lista de eventos procesados por las operaciones.</p> </li> 
     <li> <p>se sincroniza con la tabla NmsBroadLogMsg para poder recuperar los atributos del mensaje de la entrega.</p> </li> 
     <li> <p>recupera los registros de envío de eventos en cuanto se completa la sincronización con la tabla NmsBroadLogMsg.</p> </li> 
     <li> <p>se sincroniza con la tabla NmsTrackingUrl para recuperar el seguimiento de las URL de la entrega.</p> </li> 
     <li> <p>recupera las URL de seguimiento de eventos en cuanto se completa la sincronización con la tabla NmsTrackingUrl.</p> </li> 
     <li> <p>permite recuperar todas las direcciones de correo electrónico puestas en cuarentena cada tres horas después de realizar una entrega.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

