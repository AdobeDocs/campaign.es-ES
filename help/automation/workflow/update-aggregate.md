---
product: campaign
title: Actualización del agregado
description: Descubra más información acerca de la actividad del flujo de trabajo Actualización de agregado
feature: Workflows
role: Data Engineer
level: Beginner
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 11%

---

# Actualización del agregado{#update-aggregate}

Los agregados definidos en [cubos](../../v8/reporting/gs-cubes.md) para la generación de informes se pueden actualizar con una actividad específica. Una ficha **[!UICONTROL Workflow]** está disponible al configurar el agregado.

Obtenga más información acerca de los cubos y los agregados en [esta sección](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

Para actualizar un agregado, edite la actividad **[!UICONTROL Update aggregate]** y seleccione el cubo y el agregado que desea actualizar.

Puede configurar una **actualización completa** o una **actualización parcial**.

![](assets/update-aggregate-details.png)

De forma predeterminada, se ejecuta una actualización completa durante cada cálculo. Para activar una actualización parcial, seleccione la opción y defina las condiciones de actualización.

![](assets/update-aggregate-partial.png)

Una práctica recomendada es agregar una actividad **[!UICONTROL Scheduler]** para configurar la frecuencia de las actualizaciones del cálculo.
