---
product: campaign
title: Presentación de una oferta (interacción entrante)
description: Obtenga información sobre cómo presentar la mejor oferta mediante el módulo de interacción de Campaign
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 21%

---

# Presentar la mejor oferta{#interaction-present-offers}

Las ofertas se pueden presentar en varios espacios de ofertas utilizando [un canal entrante o saliente](interaction-architecture.md#interaction-types). En este capítulo se detallan algunas funciones específicas de los canales entrantes.

![](assets/inbound-interactions.png)

Para que el motor de oferta pueda seleccionar una oferta, debe aprobarse y estar disponible en un entorno en directo.

Para obtener más información, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html#approving-offer-content){target="_blank"}.

En el contexto de un contacto entrante, el sitio web puede identificar o no al usuario que está explorando la página. El motor de oferta presenta diferentes ofertas para perfiles identificados y para perfiles anónimos.

Antes de poder presentar ofertas en un canal entrante, se debe configurar la llamada del motor de oferta en la que se desee presentar las ofertas. En la mayoría de los casos de una interacción entrante, esta es la página web.

>[!NOTE]
>
>Para las interacciones entrantes, se debe configurar específicamente el motor de oferta para presentar y actualizar una o varias ofertas.
>
>Asimismo, se debe activar el modo unitario en los espacios de oferta. Para obtener más información, consulte [esta página](interaction-offer-spaces.md).
