---
title: 'Introducción a las API de Campaign '
description: 'Introducción a las API de Campaign '
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 12%

---

# Introducción con [!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] viene con un conjunto de funciones de JavaScript que puede utilizar:

* en scripts: en [!DNL Adobe Campaign] flujos de trabajo
* mediante API: desde sistemas externos

Puede utilizar las API de JavaScript para escribir en la base de datos de Campaign cloud o leer desde la base de datos:

* API específicas del negocio que le permiten actuar en cada objeto: envíos, flujos de trabajo, suscripciones, etc. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html).
* API de acceso a datos genéricas para consultar los datos del modelo de datos. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html).

Campaign v8 funciona con dos bases de datos: una base de datos local para la interfaz de usuario mensajería en tiempo real y consultas unitarias y escritura a través de API, y una base de datos de Cloud para ejecución de campañas, informes, ingesta de datos, consultas por lotes y ejecución del flujo de trabajo.

>[!CAUTION]
>
>[!DNL Adobe Campaign] La versión 8 incluye un límite en el rendimiento (TPS) de nuestra capa de API. Si se supera el límite, se produce un error HTTP estándar (429). Como usuario de Cloud Services administrados, puede ponerse en contacto con Adobe para adaptar la regulación de cada API.

## Requisitos previos

Antes de usar [!DNL Adobe Campaign] , debe conocer los siguientes temas:

* JavaScript
* Protocolo SOAP
* [!DNL Adobe Campaign] datamodel

Para utilizar las API e interactuar con [!DNL Adobe Campaign], también debe estar familiarizado con el modelo de datos.

>[!NOTE]
>Puede generar una descripción completa del modelo de datos. Obtenga más información en [esta página](datamodel.md).

## [!DNL Campaign] Mecanismo de ensayo de API

con [!DNL Campaign] No se recomiendan las llamadas unitarias a la base de datos en la nube o a blast debido al rendimiento (latencia y concurrencia). Siempre se prefiere el funcionamiento por lotes. Para garantizar un rendimiento óptimo de las API, Campaign sigue gestionando las llamadas de API a nivel de base de datos local.

![](../assets/do-not-localize/glass.png) [El mecanismo de ensayo de la API se detalla en esta página](staging.md)

## Nuevas API

Hay nuevas API disponibles para administrar la sincronización de datos entre [!DNL Campaign] base de datos local y base de datos en la nube. También se ha introducido un nuevo mecanismo para gestionar llamadas de API a nivel de base de datos local para evitar la latencia y aumentar el rendimiento general.

![](../assets/do-not-localize/glass.png) [Las nuevas API se detallan en esta página](new-apis.md)

**Temas relacionados**

* [Prácticas recomendadas del modelo de datos](datamodel-best-practices.md)