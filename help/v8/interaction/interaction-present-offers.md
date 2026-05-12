---
product: campaign
title: Presentación de una oferta (interacción entrante)
description: Obtenga información sobre cómo presentar la mejor oferta mediante el módulo de interacción de Campaign
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
TQID: https://experienceleague.adobe.com/aC-hN1JwwFkuGc6ZNV0M3uHpM7LcXTHpyC9wCbxKziQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 23%

---

# Presentar la mejor oferta{#interaction-present-offers}

Las ofertas se pueden presentar en varios espacios de ofertas usando [un canal entrante o saliente](interaction-architecture.md#interaction-types). En este capítulo se detallan algunas funciones específicas de los canales entrantes.

![](assets/inbound-interactions.png)

Para que el motor de oferta pueda seleccionar una oferta, debe aprobarse y estar disponible en un entorno en directo.

Para obtener más información, consulte la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=es#approving-offer-content){target="_blank"}.

En el contexto de un contacto entrante, el sitio web puede identificar o no al usuario que está explorando la página. El motor de oferta presenta diferentes ofertas para perfiles identificados y para perfiles anónimos.

Antes de poder presentar ofertas en un canal entrante, se debe configurar la llamada del motor de oferta en la que se desee presentar las ofertas. En la mayoría de los casos de una interacción entrante, esta es la página web.

>[!NOTE]
>
>Para las interacciones entrantes, se debe configurar específicamente el motor de oferta para presentar y actualizar una o varias ofertas.
>
>Asimismo, se debe habilitar el modo unitario en los espacios de oferta. Para obtener más información, consulte [esta página](interaction-offer-spaces.md).
