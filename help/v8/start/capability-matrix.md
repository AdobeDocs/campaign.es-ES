---
title: 'Campaign Classic v7: Matriz de capacidades de Campaign v8'
description: Comprender las diferencias entre Campaign Classic v7 y Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 0c01b0a597e54ae93dd581ccba6f19b2ff13f956
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 40%

---

# [!DNL Campaign Classic] Funcionalidades de v7 - [!DNL Campaign] v8{#gs-matrix}

Como antiguo [!DNL Campaign Classic] usuario de la versión 7, no debería esperar grandes interrupciones en la forma en que normalmente interactúa con [!DNL Adobe Campaign]. La mayoría de los cambios de la versión 8 no son visibles, excepto los pequeños cambios que aparecen en la IU y en los pasos de configuración.

Adobe Campaign v8 está disponible como **Cloud Service administrado**. La nueva oferta combina servicios de primera clase con supervisión proactiva y alertas oportunas, centrándose en tres áreas:

* **Agilidad de la nube** : automatización por Adobe, con implementaciones de nube optimizadas y estandarizadas para obtener un rendimiento más predecible, una buena agilidad y una productividad de autoservicio mejorada.
* **Experiencia del servicio** : disponibilidad proactiva, capacidad y supervisión y respuesta del performance para prevenir interrupciones, resolver incidentes más rápidamente y revisar el servicio regularmente para mejorar continuamente.
* **Experiencia en campañas profundas** : servicio de alta afinidad de equipos expertos en ingeniería de clientes para satisfacer las necesidades funcionales, técnicas o de capacidad de envío, reducir el riesgo de implementación y mejorar la administración de cambios.

Como antiguo [!DNL Campaign Classic] tenga en cuenta que la mayoría de las [!DNL Campaign Classic] Las funciones de la versión 7 están disponibles con [!DNL Campaign] v8, excepto un pequeño conjunto de ellos, enumerados en [esta sección](#gs-removed). Se incluirán más en futuras versiones. [Obtenga más información en esta sección](#gs-unavailable-features)

>[!NOTE]
>
> Campaign v8 se basa en una arquitectura híbrida. Si está realizando la transición desde Campaign Classic v7, tenga en cuenta que todas las entregas pasan al servidor de mid-sourcing. [Más información](../architecture/architecture.md)
>
> Como consecuencia, el enrutamiento interno es **no es posible** en Campaign v8, y la cuenta externa se ha deshabilitado en consecuencia.


## [!DNL Campaign] y [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 funciona con [!DNL Snowflake]. Hay dos modelos de implementación disponibles.

![](../assets/do-not-localize/glass.png) Obtenga más información acerca la arquitectura de [!DNL Campaign] v8 en [esta página](../architecture/architecture.md).


## Utilice su Adobe ID para conectarse a Campaign{#adobe-id}

Los usuarios de Campaign se conectan mediante su Adobe ID. El mismo Adobe ID se utiliza para mantener todos sus planes de Adobe y productos asociados con una sola cuenta, para todas las soluciones de Adobe Experience Cloud.

![](../assets/do-not-localize/glass.png) Obtenga más información sobre cómo conectarse a [!DNL Campaign] en [esta página](connect.md).

## Analizar datos con cubos{#adobe-reporting}

Utilice el módulo Marketing Analytics para analizar y medir datos, calcular estadísticas y simplificar y optimizar la creación y el cálculo de informes. Además, cree informes y cree poblaciones objetivo: una vez identificados, se almacenan en listas que se pueden utilizar en Adobe Campaign (establecimiento de objetivos, segmentación, etc.).

Los informes de cubo de Adobe Campaign están optimizados y ofrecen mejores funciones de escala que Campaign Classic v7. Las limitaciones anteriores de Cubes no se aplican en Campaign v8.

## Cambio de la fuente de datos {#change-data-source}

Campaign v8 ofrece una actividad de flujo de trabajo de direccionamiento adicional: **[!UICONTROL Change data source]**.

La actividad **[!UICONTROL Change data source]** permite cambiar la fuente de datos de la **[!UICONTROL Working table]** de un flujo de trabajo para administrar los datos en diferentes fuentes de datos, como FDA, FDAC y la base de datos local.

![](../assets/do-not-localize/glass.png) Obtenga más información sobre la actividad **[!UICONTROL Change data source]** en [esta página](../config/workflows.md#change-data-source-activity).

## Funciones no disponibles{#gs-unavailable-features}

Tenga en cuenta que algunas funciones aún no están disponibles en esta versión de Campaign, por ejemplo:

* Gestión de recursos de marketing
* Modelos de implementación híbridos/locales

>[!CAUTION]
>
>* Por ahora, Campaign v8 **solo** está disponible como Cloud Service administrado y no se puede implementar en entornos locales o híbridos.
>
>* La migración desde un entorno de Campaign Classic v7 existente aún no está disponible.
>
>* Si no está seguro sobre su modelo de implementación o tiene alguna pregunta, póngase en contacto con su ejecutivo de cuentas de Adobe.


## Funciones no admitidas{#gs-removed}

Para alinearse con la nueva arquitectura y el modelo de implementación de Campaign v8, algunas funciones históricas de Campaign Classic v7 ya no están disponibles en Campaign v8. Por ejemplo:

* Cupones
* Seguimiento web
* Encuestas
* Marketing social
* Conector ACS (oferta principal)
* Integración con LDAP
* Inicio de sesión con usuario/contraseña

>[!NOTE]
>
>Algunas funciones no disponibles o no compatibles pueden seguir estando visibles en la interfaz de usuario.
