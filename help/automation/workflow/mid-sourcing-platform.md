---
product: campaign
title: Mid-sourcing platform
description: Mid-sourcing platform
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
source-git-commit: 8a7bf8408d15e0bd9e1c3e72f7846bf9a79c6885
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 41%
---

# Mid-sourcing platform{#mid-sourcing-platform}



Los flujos de trabajo detallados a continuación se instalan con el módulo **Plataforma de mid-sourcing** de forma predeterminada.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>Nombre interno</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Indicadores de entregas</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryIndicators</span> <br /> </td> 
   <td> Este flujo de trabajo actualiza los indicadores de seguimiento de un envío para un envío. De forma predeterminada, este flujo de trabajo se activa cada hora.<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>El período de retención de registro en el servidor intermediario debe ser mayor que el período de validez del envío más el valor **indicatorsDuration**. De lo contrario, los indicadores de envío disminuyen cuando se depuran los registros antiguos y los valores más bajos se sincronizan con la instancia de marketing. Por ejemplo, con un período de validez de 5 días y **indicatorsDuration** de 30 días, establezca el período de retención en al menos 36 días.
