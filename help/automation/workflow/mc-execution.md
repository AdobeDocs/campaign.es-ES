---
product: campaign
title: Message Center (Execution)
description: Message Center (Execution)
feature: Workflows
role: User
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 100%
---

# Message Center (Execution){#message-center-execution}

Los flujos de trabajo detallados a continuación se instalan con el complemento **Message Center - Execution** de forma predeterminada.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>Nombre interno</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Actualizar estado del evento</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Este flujo de trabajo permite asignar un estado a un evento. Los estados de eventos son los siguientes:<br /> 
    <ul> 
     <li> <p><strong>Pendiente</strong>: el evento está en cola. Aún no se le ha asociado ninguna plantilla de mensaje.</p> </li> 
     <li> <p><strong>Envío pendiente</strong>: el evento está en cola, se le ha asociado una plantilla de mensaje y la entrega se está procesando en ese momento.</p> </li> 
     <li> <p><strong>Enviado</strong>: este estado se copia desde los “logs” de envío. Significa que la entrega se realizó.</p> </li> 
     <li> <p><strong>Envío ignorado</strong>: este estado se copia desde los “logs” de envío. Significa que la entrega se ha ignorado.</p> </li> 
     <li> <p><strong>Error de envío</strong>: este estado se copia desde los “logs” de envío. Significa que la entrega ha fallado.</p> </li> 
     <li> <p><strong>Evento no cubierto</strong>: el evento no se ha podido asociar con una plantilla de mensaje. El evento no se vuelve a procesar.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Procesamiento de eventos por lotes</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> Este flujo de trabajo permite colocar eventos en lote en cola antes de asociarlos con una plantilla de mensaje. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Procesamiento de eventos en tiempo real</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> Este flujo de trabajo permite colocar eventos en tiempo real en cola antes de asociarlos con una plantilla de mensaje. <br /> </td> 
  </tr> 
 </tbody> 
</table>

