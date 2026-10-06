---
title: Comparta públicos con soluciones de Adobe Experience Cloud
description: Descubra cómo compartir públicos con soluciones de Adobe Experience Cloud
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 75%
---
# Comparta públicos con soluciones de Adobe Experience Cloud{#shared-audiences}

Opción 1: Fuentes y destinos de AEP

Opción 2: Adobe Personas/AAM

Puede integrar **Adobe Campaign** con **Servicio principal Personas** o Adobe Audience Manager. Esto le permite:

* Importar públicos y segmentos compartidos desde distintas soluciones de Adobe Experience Cloud a Adobe Campaign. Los públicos se pueden importar mediante listas en Adobe Campaign.

* Exportación de listas en la forma de públicos compartidos de Adobe Experience Cloud. Estos públicos pueden utilizarse con las diferentes soluciones de Adobe Experience Cloud que utiliza. Los públicos se pueden exportar después de la segmentación en un flujo de trabajo con la actividad específica **[!UICONTROL Update shared audience]**.

Esta integración es compatible con dos tipos de ID de Adobe Experience Cloud:

* **ID de visitante**: este tipo de identificador reconcilia los visitantes de Adobe Experience Cloud con los destinatarios de Adobe Campaign.
* **ID declarado**: este tipo de identificador reconcilia todo tipo de datos con los elementos de la base de datos de Adobe Campaign. Constituye la clave de reconciliación predefinida en Adobe Campaign.

  >[!NOTE]
  >
  > Ahora, la fuente de datos de ID declarado también se puede utilizar con la integración del servicio principal Personas.
  >
  >Si utiliza la integración del servicio principal Personas y desea añadir la integración de Audience Manager, necesitará la ayuda de un consultor de Adobe Audience Manager para evitar perder todas las sincronizaciones de ID recopiladas al realizar la transición al uso de esta fuente de datos de ID declarado en un contexto de Adobe Audience Manager.

Consulte:

[Base de conocimiento de Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=es){target="_blank"}.

[Guía de componentes de la interfaz central de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=es){target="_blank"}.
