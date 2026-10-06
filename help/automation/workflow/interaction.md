---
product: campaign
title: Interacción
description: Interacción
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 73%
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
   <td> Este flujo de trabajo actualiza el acumulado <strong>Completo</strong> del cubo <strong>Propuesta de oferta. </strong> Se activa todos los días a las 6 a. m. de manera predeterminada. Este agregado captura las siguientes dimensiones: canal, envío, oferta de marketing y fecha.<br /> Luego se usa el cubo <strong>Propuesta de oferta</strong> para generar informes basados en ofertas.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter full aggregate calculation</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Este flujo de trabajo actualiza el acumulado <strong>Completo</strong> del cubo <strong>Centro de mensajes</strong>. Se activa cada día a las 3 de la mañana de forma predeterminada. Este agregado captura las siguientes dimensiones: canal, fecha, estado y tipo de evento.<br /> Luego se usa el cubo <strong>Centro de mensajes</strong> para generar informes basados en eventos. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Obtenga más información acerca de los cubos y los agregados en [esta sección](../../v8/reporting/gs-cubes.md).

