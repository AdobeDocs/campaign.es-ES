---
title: Catálogo de ofertas de interacción de Campaign
description: Obtenga información sobre cómo crear un catálogo de ofertas
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 28%

---

# Creación de un catálogo de ofertas

Como **Gestor de ofertas**, usted es el responsable de crear el catálogo de ofertas.

Un catálogo de ofertas está asociado a un solo entorno preexistente. Las ofertas de este catálogo solo pueden asociarse con los espacios especificados en este mismo entorno.

Antes de crear las ofertas, primero debe especificar una [entorno](interaction-env.md) que contiene todas las características (idoneidad, restricciones en el objetivo, reglas de presentación) de un conjunto de ofertas, ordenadas en categorías, así como la lista de sus espacios.

## Creación de categorías de oferta{#creating-offer-categories}

Las ofertas se organizan en categorías o subcategorías. Las categorías se crean en la variable **[!UICONTROL Design]** y se implementa automáticamente en la variable **[!UICONTROL Live]** cuando se aprueban las ofertas que contienen. La variable **[!UICONTROL Design]** environment contiene una categoría predeterminada para recibir todas las ofertas. Se puede crear subcategorías para añadir jerarquía a las ofertas del catálogo.

Para cada categoría, puede definir **fechas de idoneidad**, que es el periodo durante el cual las ofertas contenidas en la categoría se pueden presentar al objetivo. También puede ajustar el peso de una categoría para priorizar la presentación de la oferta.

Para crear una nueva categoría, siga los pasos a continuación:

1. Vaya al **[!UICONTROL Offer catalog]** carpeta.

   ![](assets/offer_cat_create_001.png)

1. Haga clic derecho en el ratón y, en la lista desplegable, seleccione **[!UICONTROL Create a new "Offer category" folder]**.

   ![](assets/offer_cat_create_002.png)

1. Cambie el nombre de la categoría. Se puede editar la etiqueta más adelante mediante la pestaña **[!UICONTROL General]**.

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >Repita estos pasos para crear tantas categorías como sea necesario.

   A continuación, según sea necesario, se puede:

   * asignar las fechas de idoneidad en la pestaña **[!UICONTROL Eligibility]**.

      ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]** para aplicar filtros al objetivo de la oferta.

   * Resumen de las reglas de idoneidad. Para verlas, haga clic en el botón **[!UICONTROL Schedule and eligibility rules of the offer]** vínculo.

## Añadir una categoría de reserva

Para asegurarse de que todos los destinatarios reciban una propuesta de oferta, es posible añadir de forma sistemática una o varias categorías de ofertas en las recomendaciones.

Estas ofertas de reserva deben tener un peso bajo (pero no nulo), de modo que solo se tengan en cuenta si ninguna oferta de ponderación superior es elegible.

Además, no debe haber ninguna regla de presentación aplicada a estas ofertas para asegurarse de que se incluyen siempre en las recomendaciones. Esto significa que, durante una propuesta, si no hay disponible ninguna oferta de ponderación superior, el destinatario recibe al menos una oferta de esta categoría.

Para incluir una categoría de reserva en las recomendaciones, siga los pasos a continuación:

1. Vaya al catálogo de ofertas.
1. Haga clic en el **[!UICONTROL Eligibility]** y seleccione **[!UICONTROL Always include this category in the recommendations]** .
1. Haga clic en **[!UICONTROL Save]**.

   ![](assets/offer_cat_default_001.png)
