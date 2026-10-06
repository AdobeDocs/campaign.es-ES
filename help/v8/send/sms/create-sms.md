---
title: Creación de un envío de SMS
description: Obtenga información sobre cómo crear un envío de SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 3b15eb3e-8625-4049-bf0d-327407ae5ea6
TQID: 'https://experienceleague.adobe.com/9hRirStfl9Rb2piTS3xY7C4Gb7zsUGeuoTxFFKgjf-8'
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
source-wordcount: '170'
ht-degree: 12%
---
# Creación de su primer envío de SMS {#sms-delivery}

Para diseñar un envío de SMS nuevo, siga los pasos a continuación:

1. Cree una nueva entrega y seleccione la [plantilla de envíos de SMS](sms-mid-sourcing.md#sms-delivery-template) que creó para sus envíos de SMS.

   ![](assets/sms_create.png){zoomable="yes"}

   Los pasos de creación de entregas se detallan en [esta página](../../start/create-message.md).

<!--
 * For standalone instance,  [learn more here](sms-standalone-instance.md#sms-delivery-template).
* For mid-sourcing infrastructure,
-->

1. Cambie el nombre de la entrega en el campo **[!UICONTROL Label]** y agregue información en el campo **[!UICONTROL Delivery code]** y en la lista **[!UICONTROL Nature]** si es necesario para el seguimiento. También puede agregar un(a) **[!UICONTROL Description]** a su entrega.

1. Haga clic en el botón **[!UICONTROL Continue]**. Ahora, tiene todos los ajustes de la plantilla en su envío.

1. Puede comprobar en el botón **[!UICONTROL Properties]** que todo está configurado según sea necesario. [Más información sobre la ficha SMS](sms-delivery-settings.md#sms-tab)

   ![](assets/sms_settings.png){zoomable="yes"}

1. [Defina el contenido](sms-content.md) de su envío.

1. [Seleccione la audiencia](sms-audience.md).

Los pasos para definir una audiencia se detallan en [esta página](../../audiences/create-audiences.md).

## Validación y envío de SMS {#sms-validate}

Después de la creación de la entrega, puede:

1. [Enviar pruebas](sms-proofs.md) para validar la representación y el contenido,

1. A continuación, [enviar a la audiencia final](sms-send.md).

## Monitorización y seguimiento de SMS {#sms-monitor}

Después del envío, [aprenderá a monitorizar y rastrear su SMS](sms-monitor.md).
