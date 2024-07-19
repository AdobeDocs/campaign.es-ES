---
product: campaign
title: Análisis web
description: Descubra más información sobre el paquete Web Analytics
feature: Workflows, Analytics Integration
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 81%

---


# Análisis web{#web-analytics}



Los flujos de trabajo detallados a continuación se instalan con el módulo **Conectores de análisis web** de forma predeterminada.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>Nombre interno</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Sending of indicators and campaign attributes</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsSendMetrics</span><br /> </td> 
   <td> Este flujo de trabajo permite enviar indicadores de campaña de correo electrónico desde Adobe Campaign a Adobe Experience Cloud Suite a través del conector de Adobe® Analytics. Los indicadores correspondientes son los siguientes: <strong>Sent</strong> (iSent), <strong>Total count of opens</strong> (iTotalRecipientOpen), <strong>Total number of recipients who clicked</strong> (iTotalRecipientClick), <strong>Errors</strong> (iError), <strong>Opt-Out</strong> (opt-out) (iOptOut).<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Identification of converted contacts</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsFindConverted</span><br /> </td> 
   <td> Este flujo de trabajo lista a los visitantes del sitio que han finalizado su compra después de la campaña de remarketing. Se puede acceder a los datos recuperados por este flujo de trabajo en <span class="uicontrol">Informe de eficiencia de remarketing</span> (consulte este ). <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Event purge</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsPurgeWebEvents</span><br /> </td> 
   <td> Este flujo de trabajo permite eliminar todos los eventos del campo de base de datos según el periodo configurado en el campo <span class="uicontrol">Lifespan</span>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Recovery of web events</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsGetWebEvents</span><br /> </td> 
   <td> Cada hora, este flujo de trabajo descarga segmentos sobre el comportamiento de los usuarios de Internet en un sitio determinado, los integra en la base de datos de Adobe Campaign e inicia el flujo de trabajo de remarketing. <br /> </td> 
  </tr> 
 </tbody> 
</table>

