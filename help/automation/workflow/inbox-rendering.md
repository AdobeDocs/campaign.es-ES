---
product: campaign
title: Flujo de trabajo técnico de renderización de la bandeja de entrada
description: En esta sección se describe el flujo de trabajo técnico instalado con el paquete de renderización de la bandeja de entrada
feature: Workflows, Inbox Rendering
role: User, Admin
version: Campaign v8, Campaign Classic v7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
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

