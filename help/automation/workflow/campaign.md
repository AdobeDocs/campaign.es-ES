---
product: campaign
title: Campaña
description: Campaña
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 92%

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
   <td> Este flujo de trabajo activa las entregas aprobadas e inicia el posprocesado del proveedor de servicios para una entrega externo. También envía notificaciones de aprobación y recordatorios.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Trabajos en campaña</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span> <br /> </td> 
   <td> Este flujo de trabajo administra los trabajos de las campañas de marketing (inicia los objetivos, la extracción de archivos, etc.). También crea flujos de trabajo relacionados con campañas recurrentes y periódicas.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Trabajos con proveedores de servicios</span> <br /> </td> 
   <td> <span class="uicontrol">supplierMgt</span> <br /> </td> 
   <td> Este flujo de trabajo comienza a procesar el proveedor (correo electrónico al enrutador y posprocesado) una vez que se aprueban las entregas. <br /> </td> 
  </tr> 
 </tbody> 
</table>

