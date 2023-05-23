---
product: campaign
title: Interacción
description: Interacción
feature: Workflows, Interaction
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 93%

---


# Interacción{#interaction}

Los flujos de trabajo detallados a continuación se instalan con el complemento **Motor de ofertas (Interacción)** de forma predeterminada.

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
   <td> Este flujo de trabajo actualiza el acumulado <strong>Completo</strong> del cubo <strong>Propuesta de oferta. </strong> Se activa todos los días a las 6 a. m. de manera predeterminada. Este acumulado captura las siguientes dimensiones: Canal, Entrega, Oferta de mercadotecnia y Fecha.<br /><strong> Luego se utiliza el cubo Propuesta de oferta para generar informes basados en ofertas.</strong><br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter full aggregate calculation</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Este flujo de trabajo actualiza el acumulado <strong>Completo</strong> del cubo <strong>Centro de mensajes</strong>. Se activa cada día a la 3 de la mañana de forma predeterminada. Este acumulado captura las siguientes dimensiones: canal, fecha, estado y tipo de evento.<br /> Luego se utiliza el cubo <strong>Centro de mensajes</strong> para generar informes basados en eventos. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Obtenga más información sobre los cubos y los acumulados en [esta sección](../../v8/reporting/gs-cubes.md).

