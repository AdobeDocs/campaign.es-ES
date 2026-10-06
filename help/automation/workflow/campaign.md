---
product: campaign
title: Campaña
description: Campaña
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
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
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 100%
---

# Campaña{#campaign}

Los flujos de trabajo detallados a continuación se instalan con el módulo **Campaign** de forma predeterminada.

>[!CAUTION]
>
>Estos flujos de trabajo DEBEN iniciarse para que los procesos de campaña se ejecuten a nivel de campaña.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>Nombre interno</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Calcular coste</span> <br /> </td> 
   <td> <span class="uicontrol">budgetMgt</span> <br /> </td> 
   <td> Este flujo de trabajo inicia el cálculo de las líneas de gastos y de costes sobre presupuestos, planes, programas, campañas, envíos y tareas.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Valores: Pedidos y alertas</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span> <br /> </td> 
   <td> Este flujo de trabajo inicia el cálculo de existencias en las líneas de pedido y administra los umbrales de alertas de advertencia.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Trabajos enviados en campañas</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span> <br /> </td> 
   <td> Este flujo de trabajo activa los envíos aprobados e inicia el posprocesado del proveedor de servicios para un envío externo. También envía notificaciones de aprobación y recordatorios.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Trabajos en campaña</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span> <br /> </td> 
   <td> Este flujo de trabajo administra los trabajos de las campañas de marketing (inicia la segmentación, la extracción de archivos, etc.). También crea flujos de trabajo relacionados con campañas recurrentes y periódicas.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Trabajos con proveedores de servicios</span> <br /> </td> 
   <td> <span class="uicontrol">supplierMgt</span> <br /> </td> 
   <td> Este flujo de trabajo comienza a procesar el proveedor (correo electrónico al enrutador y posprocesado) una vez que se aprueban las entregas. <br /> </td> 
  </tr> 
 </tbody> 
</table>

