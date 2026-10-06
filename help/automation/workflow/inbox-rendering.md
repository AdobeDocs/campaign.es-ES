---
product: campaign
title: Flujo de trabajo técnico de renderización de la bandeja de entrada
description: En esta sección se describe el flujo de trabajo técnico instalado con el paquete de renderización de la bandeja de entrada
feature: Workflows, Inbox Rendering
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: 2317b1ea-6db4-58c7-851f-717a69c0f5c0
    internal-label: Inbox Rendering
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 78%
---

# Procesamiento de la bandeja de entrada (IR){#inbox-rendering}



El flujo de trabajo detallado a continuación se instala con el módulo **Renderización de la bandeja de entrada (IR)** de forma predeterminada.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>Nombre interno</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Actualizar la red semilla para la renderización de la bandeja de entrada</strong><br /> </td> 
   <td> <span class="uicontrol">updateRenderingSeeds</span><br /> </td> 
   <td> Este flujo de trabajo actualiza las direcciones de correo electrónico utilizadas para la renderización de la bandeja de entrada y solo funciona si el puerto HTTPS está abierto para <strong>deliverability.neolane.net</strong>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

