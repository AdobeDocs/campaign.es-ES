---
title: 'Campaign Classic v7: Matriz de capacidades de Campaign v8'
description: Comprender las diferencias entre Campaign Classic v7 y Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 220ff4ff31e55aba085f47de67347e28bcb3e30d
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 40%

---

# [!DNL Campaign Classic] Funcionalidades de v7 - [!DNL Campaign] v8{#gs-matrix}

[!DNL Campaign Classic][!DNL Adobe Campaign] La mayoría de los cambios de la versión 8 no son visibles, excepto los pequeños cambios que aparecen en la IU y en los pasos de configuración.

**** The new offering combines best-in-class services with proactive oversight and timely alerting, focusing on three areas:

* ****
* ****
* ****

[!DNL Campaign Classic][!DNL Campaign Classic][!DNL Campaign][](#gs-removed) Se incluirán más en futuras versiones. [Obtenga más información en esta sección](#gs-unavailable-features)

>[!NOTE]
>
> Campaign v8 relies on a hybrid architecture. If you are transitioning from Campaign Classic v7, note that all deliveries go through the mid-sourcing server. [Más información](../architecture/architecture.md)
>
> ****


## [!DNL Campaign] y [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Snowflake] Two deployment models are available.

![](../assets/do-not-localize/glass.png) Obtenga más información acerca la arquitectura de [!DNL Campaign] v8 en [esta página](../architecture/architecture.md).


## Use your Adobe ID to connect to Campaign{#adobe-id}

Los usuarios de Campaign se conectan mediante su Adobe ID. The same Adobe ID is used to keep all your Adobe plans and products associated with a single account, for all Adobe Experience Cloud solutions.

![](../assets/do-not-localize/glass.png) Obtenga más información sobre cómo conectarse a [!DNL Campaign] en [esta página](connect.md).

## Analyze data with cubes{#adobe-reporting}

Use the Marketing Analytics module to analyze and measure data, calculate statistics, simplify and optimize report creation and calculation. In addition, create reports and build target populations: once identified, they are stored in lists that can be used in Adobe Campaign (targeting, segmentation, etc.).

Adobe Campaign cube reports are optimized and bring better scale capabilities than Campaign Classic v7. Former limitations on Cubes do not apply in Campaign v8.

## Cambio de la fuente de datos {#change-data-source}

Campaign v8 ofrece una actividad de flujo de trabajo de direccionamiento adicional: **[!UICONTROL Change data source]**.

La actividad **[!UICONTROL Change data source]** permite cambiar la fuente de datos de la **[!UICONTROL Working table]** de un flujo de trabajo para administrar los datos en diferentes fuentes de datos, como FDA, FDAC y la base de datos local.

![](../assets/do-not-localize/glass.png) Obtenga más información sobre la actividad **[!UICONTROL Change data source]** en [esta página](../config/workflows.md#change-data-source-activity).

## Funciones no disponibles{#gs-unavailable-features}

Tenga en cuenta que algunas funciones aún no están disponibles en esta versión de Campaign, por ejemplo:

* Gestión de recursos de marketing
* Marketing distribuido
* Gestor de respuestas
* Modelos de implementación híbridos/locales

>[!CAUTION]
>
>* Por ahora, Campaign v8 **solo** está disponible como Cloud Service administrado y no se puede implementar en entornos locales o híbridos.
>
>* La migración desde un entorno de Campaign Classic v7 existente aún no está disponible.
>
>* If you are unsure of your deployment model or have any question, please get in touch with your Adobe Account executive.


## Funciones no admitidas{#gs-removed}

Para alinearse con la nueva arquitectura y el modelo de implementación de Campaign v8, algunas funciones históricas de Campaign Classic v7 ya no están disponibles en Campaign v8. Por ejemplo:

* Cupones
* Seguimiento web
* Encuestas
* Marketing social con Facebook
* Conector ACS (oferta principal)
* Integración con LDAP
* Inicio de sesión con usuario/contraseña

>[!NOTE]
>
>Some non-available or unsupported features may still be visible in the user interface.
