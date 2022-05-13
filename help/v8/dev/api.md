---
title: 'Introducción a las API de Campaign '
description: 'Introducción a las API de Campaign '
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 15%

---

# [!DNL Campaign]{#gs-ac-api}

[!DNL Adobe Campaign]

* [!DNL Adobe Campaign]
* via APIs - from external systems

You can use JavaScript APIs to write in Campaign cloud database or read from the database:

* Business-specific APIs that let you act on each object: deliveries, workflows, subscriptions, and so on. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html).
* Generic data access APIs for querying the data model data. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html).

Campaign v8 works with two databases: a local database for the user interface real-time messaging and unitary queries and write through APIs, and a Cloud database for campaign execution, reporting, data ingestion, batch queries and workflow execution.

>[!CAUTION]
>
>[!DNL Adobe Campaign] Breaking the limit leads to standard HTTP error (429). As a Managed Cloud Services user, you can contact Adobe to adapt the throttling for each API.

## Requisitos previos

[!DNL Adobe Campaign]

* JavaScript
* SOAP protocol
* [!DNL Adobe Campaign]

[!DNL Adobe Campaign]

>[!NOTE]
>You can generate a complete description of your data model. Obtenga más información en [esta página](datamodel.md).


**Temas relacionados**

* [Prácticas recomendadas del modelo de datos](datamodel-best-practices.md)
