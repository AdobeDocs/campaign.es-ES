---
product: campaign
title: Ofertas por celda
description: Ofertas por celda
feature: Workflows, Targeting Activity, Interaction
exl-id: e2216dfd-1ef8-4747-b716-576fd6498fa6
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 94%

---

# Ofertas por celda{#offers-by-cell}



La actividad **[!UICONTROL Offers by cell]** permite distribuir la población entrante (desde una consulta por ejemplo) en varios segmentos y especificar una oferta para presentar a cada uno de estos segmentos.

Esta actividad solo se puede utilizar con **Interaction**. Obtenga más información acerca de la Administración de ofertas en [esta sección](../../v8/interaction/interaction.md).

Para ello, haga lo siguiente:

1. Una vez que haya especificado la población destinataria, añada la actividad **[!UICONTROL Offers by cell]** y ábrala.
1. En la pestaña **[!UICONTROL General]**, seleccione el espacio de oferta en el que desea presentar las ofertas.
1. En la pestaña **[!UICONTROL Cells]**, especifique los diferentes subconjuntos con el botón **[!UICONTROL Add]**:

   * Especifique la población del subconjunto utilizando las reglas de filtrado y limitación disponibles.
   * A continuación, seleccione la oferta que desee presentar al subconjunto. Las ofertas disponibles son aquellas aptas en el espacio de oferta seleccionado en el paso anterior.

      ![](assets/int_offer_per_cell1.png)

1. A continuación, configure una actividad de entrega que corresponda al canal elegido. Consulte [Envíos multicanal](cross-channel-deliveries.md).
