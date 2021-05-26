---
solution: Campaign v8
product: Adobe Campaign
title: Introducción a las API de Campaign
description: Introducción a las API de Campaign
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 5%

---

# Introducción a las API [!DNL Campaign]{#gs-ac-api}

[!DNL Adobe Campaign] viene con un conjunto de funciones de JavaScript que puede utilizar:

* en scripts: en flujos de trabajo [!DNL Adobe Campaign]
* mediante API: desde sistemas externos

Puede utilizar las API de Javascript para escribir en la base de datos de Campaign cloud o leer desde la base de datos:

* API específicas del negocio que le permiten actuar en cada objeto: envíos, flujos de trabajo, suscripciones, etc. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html).
* API de acceso de datos genéricas para consultar los datos del modelo de datos. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html).

Campaign v8 funciona con dos bases de datos: una base de datos local para la interfaz de usuario mensajería en tiempo real y consultas unitarias y escritura a través de API, y una base de datos de Cloud para ejecución de campañas, informes, ingesta de datos, consultas por lotes y ejecución del flujo de trabajo.

>[!CAUTION]
>
>[!DNL Adobe Campaign] La versión 8 incluye un límite en el rendimiento (TPS) de nuestra capa de API. Si se supera el límite, se produce un error HTTP estándar (429). Como usuario de Cloud Services administrados, puede ponerse en contacto con Adobe para adaptar la regulación de cada API.


## Requisitos previos

Antes de utilizar las API [!DNL Adobe Campaign], debe conocer los siguientes temas:

* Javascript
* Protocolo SOAP
* [!DNL Adobe Campaign] datamodel

Para utilizar las API e interactuar con [!DNL Adobe Campaign], también debe estar familiarizado con su modelo de datos.

>[!NOTE]
>Puede generar una descripción completa del modelo de datos. Obtenga más información en [esta página](datamodel.md).

## [!DNL Campaign] Mecanismo de ensayo de API

Con la [!DNL Campaign] base de datos en la nube, no se recomiendan las llamadas unitarias de blast debido al rendimiento (latencia y concurrencia). Siempre se prefiere el funcionamiento por lotes. Para garantizar un rendimiento óptimo de las API, Campaign sigue gestionando las llamadas de API a nivel de base de datos local.

[!DNL :bulb:] [El mecanismo de ensayo de la API se detalla en esta página](staging.md)

## Nuevas API

Hay nuevas API disponibles para administrar la sincronización de datos entre la base de datos local [!DNL Campaign] y la base de datos de Cloud. También se ha introducido un nuevo mecanismo para gestionar llamadas de API a nivel de base de datos local para evitar la latencia y aumentar el rendimiento general

[!DNL :bulb:] [Las nuevas API se detallan en esta página](new-apis.md)

**Temas relacionados**

* [Prácticas recomendadas del modelo de datos](datamodel-best-practices.md)
