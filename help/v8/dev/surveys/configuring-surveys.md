---
product: campaign
title: Configuración de encuestas en línea
description: Aprenda a configurar encuestas en línea
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 387bc362-4064-4181-9385-8e0c3423ba3e
TQID: 'https://experienceleague.adobe.com/1BTkZ--FyHkp7u0eya-lmuELDu8AMmeC96eGsonYcVM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: 2ac66c0844ec361de9a1658f666c190fcfac8ffa
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 93%
---
# Configuración de encuestas en línea{#configuring-surveys}

>[!AVAILABILITY]
>
>Las encuestas no están disponibles para [implementaciones de FDAC de Campaign](../../architecture/enterprise-deployment.md).



## Propiedades de encuesta {#survey-properties}

Las encuestas en línea son totalmente configurables y personalizables para satisfacer sus necesidades. Los parámetros deben introducirse en la ventana de propiedades.

Los parámetros disponibles se explican en [este documento](../web/defining-web-forms-properties.md).

![](assets/s_ncs_admin_survey_properties_general.png)

## Almacenamiento de datos de encuestas {#survey-data-storage}

De forma predeterminada, los campos de formulario web se almacenan en la tabla de destinatarios. Para usar otra tabla, selecciónela en el campo **[!UICONTROL Document type]**. El icono **[!UICONTROL Zoom]** le permite ver el contenido de la tabla seleccionada.

Las respuestas a las encuestas proporcionadas por los usuarios que no se almacenen en los campos (sino en las variables locales), se almacenan en la tabla **Respuestas a las encuestas.** Puede cambiar el esquema utilizado basándose en el campo **[!UICONTROL Library]**. Este campo solo está disponible para las **encuestas**.
