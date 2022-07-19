---
product: campaign
title: Actualización del agregado
description: Descubra más información acerca de la actividad del flujo de trabajo Actualización de agregado
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 47%

---

# Actualización de agregado{#update-aggregate}

Los agregados se especifican en el nivel de cubo para fines de creación de informes. Una pestaña **[!UICONTROL Workflow]** está disponible al configurar un acumulado.

Para obtener más información sobre los cubos y el uso de los acumulados en Adobe Campaign, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/designing-reports-with-cubes/about-cubes.html){target=&quot;_blank&quot;}.


Para actualizar un agregado, edite la variable **[!UICONTROL Update aggregate]** y seleccione el cubo y el agregado que desea actualizar.

Puede realizar una **Actualización completa** o **Actualización parcial**.

De forma predeterminada, se ejecuta una actualización completa durante cada cálculo. Para activar una actualización parcial, seleccione la opción correspondiente y defina las condiciones de actualización.

**Good practice**: se puede utilizar una actividad **[!UICONTROL Scheduler]** para especificar la frecuencia de las actualizaciones de cálculo.

![](assets/scheduler-and-cube-aggregate.png)
