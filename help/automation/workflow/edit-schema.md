---
product: campaign
title: Edición del esquema
description: Descubra más información sobre la actividad del flujo de trabajo Edición del esquema
feature: Workflows, Targeting Activity
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 16fb1aa5-cf99-4461-a1a4-7a68d97e2a74
TQID: 'https://experienceleague.adobe.com/uHsIfXEPlhLjwbGdRaUagbAhFhZb5JFxGurpSH4c0fI'
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
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 100%
---
# Edición del esquema{#edit-schema}



En el flujo de trabajo, los datos se pueden transformar, normalizar y, si es necesario, ampliar utilizando la actividad **[!UICONTROL Edit schema]**. Se suele utilizar para normalizar la estructura de datos: puede cambiar el nombre de las columnas de salida o modificar su contenido, por ejemplo, calculando los valores promedio de un campo o agregados.

Esta actividad no cambia los datos de la tabla de trabajo, solo cambia su esquema, es decir, la vista lógica de los datos.

![](assets/wf_manipulation_box.png)

También se pueden crear vínculos con otras tablas de trabajo a través de la pestaña **[!UICONTROL Links]**.

![](assets/wf_manipulation_box_link_tab.png)

La sección inferior permite configurar la lista de condiciones del vínculo, es decir, los criterios utilizados para reconciliar los datos de las dos tablas.
