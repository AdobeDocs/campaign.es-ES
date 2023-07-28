---
title: Introducción a las API de Campaign
description: Introducción a las API de Campaign
feature: API
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 9c7a4f7d4e84fde4b74bf6f8e0432681aa7e42d3
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 13%

---

# Introducción a [!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] viene con un conjunto de funciones de Javascript que puede utilizar:

* en Scripts: en [!DNL Adobe Campaign] flujos de trabajo
* mediante API: desde sistemas externos

Puede utilizar las API de JavaScript para escribir en la base de datos en la nube de Campaign o leer desde la base de datos:

* API específicas de la empresa que le permiten actuar sobre cada objeto: envíos, flujos de trabajo, suscripciones, etc. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}.
* API genéricas de acceso a datos para consultar los datos del modelo de datos. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target="_blank"}.

Tenga en cuenta que en [Implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), Campaign funciona con dos bases de datos: una base de datos local para la mensajería en tiempo real y consultas unitarias y escritura a través de API de la interfaz de usuario, y una base de datos de Cloud para la ejecución de campañas, sistemas de informes, ingesta de datos, consultas por lotes y la ejecución del flujo de trabajo.

>[!CAUTION]
>
>* A partir de la versión 8.5.1 de Campaign, el proceso de autenticación para la versión 8 de Campaign ha cambiado. Los operadores técnicos deben utilizar Adobe Identity Management System (IMS) para conectarse a Campaign. Obtenga información sobre cómo migrar sus cuentas técnicas existentes en [esta nota técnica](../../technotes/upgrades/ims-migration.md).
>
>* [!DNL Adobe Campaign] v8 viene con un límite en el rendimiento (TPS) de nuestra capa de API. Romper el límite provoca un error HTTP estándar (429). Como usuario de Cloud Services administrados, puede ponerse en contacto con el Adobe de para adaptar la limitación de cada API.
> 

## Requisitos previos

Antes de usar [!DNL Adobe Campaign] API, debe estar familiarizado con los siguientes temas:

* JavaScript
* protocolo SOAP
* [!DNL Adobe Campaign] modelo de datos

Para utilizar API e interactuar con [!DNL Adobe Campaign]Además, también debe estar familiarizado con el modelo de datos.

>[!NOTE]
>Puede generar una descripción completa del modelo de datos. Obtenga más información en [esta página](datamodel.md).


**Temas relacionados**

* [Prácticas recomendadas del modelo de datos](datamodel-best-practices.md)
