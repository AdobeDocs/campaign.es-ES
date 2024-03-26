---
product: campaign
title: Celdas
description: Celdas
feature: Workflows, Targeting Activity
role: User
exl-id: d85645a6-fc15-4c3a-9d67-d4230224e1f7
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 13%

---

# Celdas{#cells}

El **[!UICONTROL Cells]** La actividad de proporciona una vista de los distintos subconjuntos como columnas de datos. Facilita la manipulación de subconjuntos y está diseñado para aprovechar las capacidades de personalización.

![](assets/wf_split_cells.png)

Esta actividad se puede configurar para que introduzca parámetros específicos basados en las necesidades del usuario. De forma predeterminada, el detalle de cada subconjunto se detalla en una ventana dedicada a través de la **[!UICONTROL Cells]** y **[!UICONTROL Advanced]** pestañas.

![](assets/wf_split_cells_with_customization.png)

En el ejemplo siguiente, se ha modificado el formulario de entrada: a **[!UICONTROL Data]** se ha añadido una pestaña para habilitar la asociación de una oferta y un nivel de prioridad para cada subconjunto.

![](assets/cells-activity-sample.png)

Para esta configuración, se ha añadido la siguiente información al formulario de flujo de trabajo, en la **[!UICONTROL Administration > Configurations > Input forms]** nodo del explorador de Adobe Campaign:

```
<container img="nms:miniatures/mini-enrich.png" label="Data">
                <input xpath="@code"/>
                <container xpath="select/node[@alias='@numTest']">
                  <input alwaysActive="true" expr="'long'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Priority'" type="expr" xpath="@label"/>
                  <input label="Priority" maxValue="12" minValue="0" type="number"
                         xpath="@value" xpathEditFromType="@type"/>
                </container>
                <container xpath="select/node[@alias='@test']">
                  <input alwaysActive="true" expr="'string'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Identifier'" type="expr" xpath="@label"/>
                  <input label="Cell identifier" xpath="@value"/>
                </container>
                <container xpath="select/node[@alias='linkTest']">
                  <input alwaysActive="true" expr="'link'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'nms:offer'" type="expr" xpath="@dataType"/>
                  <input alwaysActive="true" expr="'Offre'" type="expr" xpath="@label"/>
                  <input computeStringAlias="@valueLabel" label="Offers" notifyPathList="@_cs|@valueLabel"
                         schema="nms:offer" type="linkEdit" xpath="@value"/>
                </container>
```

La personalización del formulario de entrada en Adobe Campaign está reservada para usuarios expertos.