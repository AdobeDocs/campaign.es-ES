---
product: campaign
title: Actualización del agregado
description: Descubra más información acerca de la actividad del flujo de trabajo Actualización de agregado
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
TQID: https://experienceleague.adobe.com/k0rl6aa1U0pK2z1dP7aGkDYk15ML3o8I0y-VwspH4mw
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 108
ht-degree: 11%

---

# Actualización de agregado{#update-aggregate}

Los agregados definidos en [cubos](../../v8/reporting/gs-cubes.md) para la generación de informes se pueden actualizar con una actividad específica. Una ficha **[!UICONTROL Workflow]** está disponible al configurar el agregado.

Obtenga más información acerca de los cubos y los agregados en [esta sección](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

Para actualizar un agregado, edite la actividad **[!UICONTROL Update aggregate]** y seleccione el cubo y el agregado que desea actualizar.

Puede configurar una **actualización completa** o una **actualización parcial**.

![](assets/update-aggregate-details.png)

De forma predeterminada, se ejecuta una actualización completa durante cada cálculo. Para activar una actualización parcial, seleccione la opción y defina las condiciones de actualización.

![](assets/update-aggregate-partial.png)

Una práctica recomendada es agregar una actividad **[!UICONTROL Scheduler]** para configurar la frecuencia de las actualizaciones del cálculo.
