---
title: Introducción a las API de Campaign
description: Introducción a las API de Campaign
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 75e0069ccd4e23dbf64b9052fd81817e438b333e
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 12%

---

# Introducción a las API de [!DNL Campaign] {#gs-ac-api}

[!DNL Adobe Campaign] viene con un conjunto de funciones de JavaScript que puede utilizar:

* en scripts - en [!DNL Adobe Campaign] flujos de trabajo
* mediante API: desde sistemas externos

>[!NOTE]
>
>Según el modelo de implementación, también puede utilizar las API de REST con Campaign v8. [Más información](../dev/api/get-started-apis.md).

Puede usar [las API de JavaScript de Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=es){target="_blank"} para escribir en la base de datos de la nube de Campaign o leer desde la base de datos:

* API específicas de la empresa que le permiten actuar sobre cada objeto: envíos, flujos de trabajo, suscripciones, etc. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=es){target="_blank"}.
* API genéricas de acceso a datos para consultar los datos del modelo de datos usando `queryDef` y el objeto `NLWS`. Obtenga más información en [Consulte la base de datos con queryDef](query-api.md).

Tenga en cuenta que en su implementación de [Enterprise (FDAC) Deployment](../architecture/enterprise-deployment.md), Campaign funciona con dos bases de datos: una base de datos local para la mensajería en tiempo real y consultas unitarias y escritura a través de API de la interfaz de usuario, y una base de datos de Cloud para la ejecución de campañas, la creación de informes, la ingesta de datos, las consultas por lotes y la ejecución del flujo de trabajo.

>[!CAUTION]
>
>* A partir de la versión 8.5.1 de Campaign, el proceso de autenticación para la versión 8 de Campaign ha cambiado. Los operadores técnicos deben utilizar Adobe Identity Management System (IMS) para conectarse a Campaign. Obtén información sobre cómo migrar tus cuentas técnicas existentes en [esta nota técnica](../../technotes/upgrades/ims-migration.md).
>
>* [!DNL Adobe Campaign] v8 viene con un límite en el rendimiento (TPS) de nuestra capa de API. Romper el límite provoca un error HTTP estándar (429). Como usuario de Cloud Services administrados, puede ponerse en contacto con Adobe para adaptar la limitación de cada API.
> 

## Requisitos previos {#ac-api-prerequisites}

Antes de usar las API [!DNL Adobe Campaign], debe estar familiarizado con los siguientes temas:

* JavaScript
* protocolo SOAP
* Modelo de datos [!DNL Adobe Campaign]

Para usar las API e interactuar con [!DNL Adobe Campaign], también debe estar familiarizado con el modelo de datos.

>[!NOTE]
>Puede generar una descripción completa del modelo de datos. Obtenga más información en [esta página](datamodel.md).


**Temas relacionados**

<!-- * [Query the database with queryDef](query-api.md)-->
* [Prácticas recomendadas del modelo de datos](datamodel-best-practices.md)
* [Documentación de JSAPI de Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=es){target="_blank"}
