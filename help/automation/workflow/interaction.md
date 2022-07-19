---
product: campaign
title: Interacción
description: Interacción
feature: Workflows, Interaction
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 91%

---


# Interacción{#interaction}



Los flujos de trabajo detallados a continuación se instalan con el complemento **Motor de ofertas (Interacción)** de forma predeterminada.

Para obtener más información, consulte estas secciones en función de la versión de Campaign:

!

![](assets/do-not-localize/v8.png)[  Documentación de Campaign v8](https://experienceleague.adobe.com/docs/campaign/campaign-v8/send/interaction/interaction.html?lang=es)


<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>Nombre interno</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Full aggregate calculation (propositionrcp cube)</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span><br /> </td> 
   <td> Este flujo de trabajo actualiza el acumulado <strong>Completo</strong> del cubo <strong>Propuesta de oferta. </strong> Se activa todos los días a las 6 a. m. de manera predeterminada. Este acumulado captura las siguientes dimensiones: Canal, Entrega, Oferta de mercadotecnia y Fecha.<br /> Luego se utiliza el cubo <strong>Propuesta de oferta</strong> para generar informes basados en ofertas. Puede obtener más información sobre los cubos en .<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter full aggregate calculation</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Este flujo de trabajo actualiza el acumulado <strong>Completo</strong> del cubo <strong>Centro de mensajes</strong>. Se activa cada día a la 3 de la mañana de forma predeterminada. Este acumulado captura las siguientes dimensiones: canal, fecha, estado y tipo de evento.<br /> Luego se utiliza el cubo <strong>Centro de mensajes</strong> para generar informes basados en eventos. Puede obtener más información sobre los cubos en .<br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

