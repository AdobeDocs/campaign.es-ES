---
title: Pruebas de envío de SMS
description: Obtenga información sobre cómo enviar pruebas de un envío SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: d2ec4d92-7f00-47c8-98e6-0613d6387de0
TQID: 'https://experienceleague.adobe.com/mAVky406-MXlkv76bqxfmolzhemVCUYKhQF1ESceRdE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 6%
---
# Envío de una prueba de un envío de SMS {#sms-proof}

Adobe recomienda encarecidamente configurar un ciclo de validación de envíos. Asegúrese de que el contenido esté aprobado antes de enviarlo a su público.

Puede enviar una prueba para su envío de SMS para validarlo:

1. Haga clic en el botón **[!UICONTROL Send a proof]** para abrir una ventana

   ![](assets/proof_targeting.png){zoomable="yes"}

   Tiene varios modos para enviar una prueba:

   * **[!UICONTROL Definition of a specific proof target]**: permite consultar con filtros las direcciones de la base de datos como destino de la prueba
   * **[!UICONTROL Substitution of the address]**: permite introducir las direcciones de prueba y utilizar los datos del destinatario de destino para validar el contenido. Las direcciones de sustitución se pueden introducir manualmente o seleccionar en la lista desplegable. La [enumeración](../../config/enumerations.md) asociada es **[!UICONTROL Substitution address (rcpAddress)]**.
     De forma predeterminada, la sustitución se realiza de forma aleatoria, pero se puede seleccionar un destinatario específico del destino principal mediante el icono **[!UICONTROL Detail]**.
   * **[!UICONTROL Seed addresses]**: permite acceder a las direcciones semilla para ser el destino de la prueba. Estas direcciones pueden importarse desde un archivo o introducirse manualmente.
   * **[!UICONTROL Specific target and Seed addresses]**: permite combinar direcciones semilla y direcciones de destinatario.

1. Después de elegir su **[!UICONTROL Targeting mode]**, agregue las direcciones de revisión según corresponda

   En el ejemplo siguiente, elegimos **[!UICONTROL Definition of a specific proof target]** y agregamos un destinatario:

   ![](assets/proof_recipient.png){zoomable="yes"}

1. Haga clic en el botón **[!UICONTROL Analyze]**.
Adobe Campaign realizará todo el control antes de validar el envío de la prueba. Al final del análisis, se podrá hacer clic en el botón **[!UICONTROL Confirm delivery]**.

   ![](assets/proof_analyze.png){zoomable="yes"}

1. Para enviar la prueba de su envío de SMS, haga clic en el botón **[!UICONTROL Confirm delivery]**.

Si todo está bien en este momento, puedes continuar y [enviar tu envío de SMS a la audiencia](sms-audience.md).
