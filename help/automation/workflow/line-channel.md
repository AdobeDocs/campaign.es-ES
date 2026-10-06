---
product: campaign
title: Canal LINE
description: Canal LINE
feature: Workflows, Line App
role: User
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: d9d413df-4e9e-4906-bbbc-28c06c2ccf59
    internal-label: LINE App
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 90%
---

# Canal LINE{#line-channel}

Los flujos de trabajo detallados a continuación se instalan con el módulo **canal LINE** de forma predeterminada. Para obtener más información, consulte [esta página](../../v8/send/line/line.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>Nombre interno</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">LINE V2 access token update</span> <br /> </td> 
   <td> <span class="uicontrol">updateLineV2AccessToken</span> <br /> </td> 
   <td> Este flujo de trabajo actualiza el token de acceso a LINE V2.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Delete blocked LINE users</span> <br /> </td> 
   <td> <span class="uicontrol">deleteBlockedLineUsersV2</span> <br /> </td> 
   <td> Este flujo de trabajo garantiza que los datos de los usuarios de LINE V2 se eliminen después de haber bloqueado la cuenta oficial de LINE durante 180 días.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">MID to LineUserID migration</span> <br /> </td> 
   <td> <span class="uicontrol">MIDToUserIDMigration</span> <br /> </td> 
   <td> Este flujo de trabajo genera las ID de los usuarios de LINE V2 para la migración de LINE V1 a LINE V2.<br /> </td> 
  </tr> 
 </tbody> 
</table>

