---
title: Trabajo con entornos de interacción de Campaign
description: Aprenda a crear entornos para la interacción de Campaign
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
TQID: 'https://experienceleague.adobe.com/SQgbIgxLE5Ef10i6wI07XBeEgBsTpxpMrFIMjgv5Lwo'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 57%
---
# Trabajo con entornos{#work-with-environments}

## Entornos en directo y de diseño{#live-design-environments}

La interacción funciona con dos tipos de entornos de oferta:

* Entornos de oferta **[!UICONTROL Design]** que incluyen ofertas que se están editando y pueden modificarse. Estas ofertas no han pasado a través del ciclo de aprobación y no se entregan a los contactos.
* Entornos de oferta **[!UICONTROL Live]** que incluyen ofertas aprobadas a medida que se presentan a los contactos. Las ofertas de este entorno son de solo lectura.

![](assets/offer_environments_overview_001.png)

Cada entorno **[!UICONTROL Design]** está relacionado con un entorno **[!UICONTROL Live]**. Cuando se completa una oferta, sus reglas de contenido y de elegibilidad están sujetas a un ciclo de aprobación. Una vez completado este ciclo, la oferta correspondiente se implementa automáticamente en el entorno **[!UICONTROL Live]**. A partir de este momento, estará disponible para su envío.

De manera predeterminada, Campaign viene con un entorno **[!UICONTROL Design]** y un entorno **[!UICONTROL Live]** relacionado con él. Ambos entornos están preconfigurados para dirigirse a la [tabla de destinatarios integrada](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>Para dirigirse a la tabla de destinatarios, debe utilizar el asistente de asignación de destino para crear los entornos. [Más información](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

Los administradores de envío solo pueden ver el entorno **[!UICONTROL Live]** y aprovechar las ofertas para enviarlas. Los administradores de ofertas pueden ver y utilizar el entorno **[!UICONTROL Design]**, así como ver el entorno **[!UICONTROL Live]**. [Más información](interaction-operators.md)

## Creación de un entorno para interacciones anónimas{#create-an-offer-environment}

De forma predeterminada, Campaign viene con un entorno integrado para dirigirse a la tabla de destinatarios (ofertas identificadas). Para dirigirse a otra tabla, como perfiles anónimos que visitan el sitio web para interacciones entrantes, debe actualizar la configuración.

Siga estos pasos:

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**, haga clic con el botón derecho en la asignación de destino que desee utilizar y seleccione **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. Haga clic en **[!UICONTROL Next]**, seleccione la opción **[!UICONTROL Generate a storage schema for propositions]** y haga clic en **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Si la opción ya está marcada, anule la selección y vuelva a seleccionarla.

1. Adobe Campaign crea dos entornos - **[!UICONTROL Design]** y **[!UICONTROL Live]** - con información de direccionamiento de la asignación de destino habilitada anteriormente. El entorno está preconfigurado con la información de objetivo.

Si ha activado la asignación **[!UICONTROL Visitor]**, la casilla **[!UICONTROL Environment dedicated to incoming anonymous interactions]** se marca automáticamente en la pestaña **[!UICONTROL General]** del entorno.

Esta opción permite activar funciones específicas de interacción anónimas, especialmente al configurar espacios de oferta de entorno. También puede configurar opciones que le permiten cambiar de un entorno “identificado” a un entorno “anónimo”.

Por ejemplo, puede vincular un entorno de destinatario con espacio de ofertas (contacto identificado) con un espacio de oferta que coincida con un entorno de visitante (contacto no identificado). De esta manera, se ponen a disposición del contacto distintas ofertas en función de si está, o no, identificado. Para obtener más información, consulte [Creación de espacios de ofertas](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>Para obtener más información sobre interacciones anónimas en un canal entrante, consulte [Interacciones anónimas](anonymous-interactions.md).
