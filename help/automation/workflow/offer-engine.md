---
product: campaign
title: Motor de oferta
description: Motor de oferta
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: d77858e1-3cd5-4372-b1bc-ea4b518c958d
TQID: https://experienceleague.adobe.com/1ZdqlgFBd-cmAQ-B--443wvLhmUXZ9YD4l-A9enANhY
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 100%

---

# Motor de oferta{#offer-engine}

La actividad **[!UICONTROL Offer engine]** permite definir una llamada al motor de oferta antes de una entrega.

Esta actividad funciona con el mismo principio que la actividad de enriquecimiento con acceso al motor, enriquece los datos de población entrantes con una oferta calculada por el motor antes de una entrega.

![](assets/int_offerengine_activity2.png)

Después de configurar la consulta (consulte esta [sección](query.md)):

1. Añada y abra una actividad **[!UICONTROL Offer engine]**.
1. Complete los diferentes campos disponibles para especificar el uso de los parámetros del motor de oferta (ofrecer espacio, categoría o tema, fecha de contacto, número de ofertas que desea mantener). Según estos parámetros, el motor calculará automáticamente las ofertas a agregar.

   >[!CAUTION]
   >
   >Si utiliza esta actividad, solo se almacenará la oferta que se haya utilizado en la entrega.

   ![](assets/int_offerengine_activity1.png)

1. A continuación, configure una actividad de envío que corresponda al canal elegido. Consulte [Envíos multicanal](cross-channel-deliveries.md).
