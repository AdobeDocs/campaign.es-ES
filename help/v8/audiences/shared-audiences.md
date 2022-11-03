---
title: Comparta audiencias con soluciones de Adobe Experience Cloud
description: Descubra cómo compartir audiencias con soluciones de Adobe Experience Cloud
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 9bea7904ea4507083d2cf45193877e7a2539d0c7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 81%

---

# Comparta audiencias con soluciones de Adobe Experience Cloud{#shared-audiences}

Opción 1: Fuentes y destinos de AEP

Opción 2: Adobe Personas/AAM

Puede integrar **Adobe Campaign** con **Servicio principal Personas** o Adobe Audience Manager. Esto le permite:

* Importar audiencias y segmentos compartidos desde distintas soluciones de Adobe Experience Cloud a Adobe Campaign. Las audiencias se pueden importar mediante listas en Adobe Campaign.

* Exportación de listas en la forma de audiencias compartidas de Adobe Experience Cloud. Estas audiencias pueden utilizarse con las diferentes soluciones de Adobe Experience Cloud que utiliza. Las audiencias se pueden exportar después de la segmentación en un flujo de trabajo con la actividad específica **[!UICONTROL Update shared audience]**.

Esta integración es compatible con dos tipos de ID de Adobe Experience Cloud:

* **ID de visitante**: este identificador concilia los visitantes de Adobe Experience Cloud con los destinatarios de Adobe Campaign.
* **ID declarado**: este identificador concilia todos los tipos de datos con los elementos de la base de datos de Adobe Campaign. Constituye la clave de reconciliación predefinida en Adobe Campaign.

   >[!NOTE]
   >
   > La fuente de datos de ID declarada también se puede utilizar con la integración del servicio principal Personas.
   >
   >Si utiliza la integración del servicio principal Personas y desea añadir la integración de Audience Manager, necesitará la ayuda de un consultor de Adobe Audience Manager para evitar perder todas las sincronizaciones de ID recopiladas al realizar la transición al uso de esta fuente de datos de ID declarados en un contexto de Adobe Audience Manager.

Consulte:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=es](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=es)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=es](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=es)
