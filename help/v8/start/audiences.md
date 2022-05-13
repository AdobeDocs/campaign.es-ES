---
title: Work with audiences in Campaign
description: Work with audiences in Campaign
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: d7e0635c6fccd70ed012a5b8148258383a1f6766
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 27%

---

# Work with audiences in Campaign{#gs-ac-audiences}

Profiles are contacts stored in Campaign database.

**** Los datos de destinatario almacenados en la base de datos permiten filtrar el destinatario que recibirá cualquier entrega dada y añadir datos de personalización en el contenido de la entrega. Existen otros tipos de perfiles en la base de datos. Están diseñados para usos diferentes. Por ejemplo, se crean perfiles semilla para probar el contenido antes de enviarlo al público objetivo final.

[](../audiences/gs-audiences.md)

## Create lists{#create-lists}

A list is a static set of contacts which can be targeted in delivery actions or updated during an import or another workflow action. For example, a population extracted from the database via a query can be stored as a list.

![](../assets/do-not-localize/glass.png)[](../audiences/create-audiences.md)

## Filter the database{#filter-the-database}

**[!UICONTROL dynamically]** You can create your own filters or use the built-in filters to define a target audience.

![](../assets/do-not-localize/glass.png)[](../audiences/create-filters.md)

## Create an audience in a workflow

Targeting can be created via a combination of queries in a graphical sequence in a workflow. You can create audiences which will be targeted according to your requirements. Para mostrar el editor de flujo de trabajo, haga clic en la pestaña **[!UICONTROL Targeting and workflows]** del panel de campañas.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)


## Perfiles activos{#active-profiles}

According to your contract, each of your Campaign instances is provisioned with a specific number of active profiles that are counted for billing purposes. Consulte su contrato más reciente para obtener una referencia sobre la cantidad de perfiles activos adquiridos.

****[](../dev/datamodel.md) Profiles are considered active if they have been targeted or communicated within the past 12 months via any channel.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

## Privacidad y consentimiento{#privacy-and-consent}

Adobe Campaign is a powerful tool for collecting and processing large volume of data, including personal information and sensitive data. Adobe Campaign le permite recopilar datos, incluida la información personal y confidencial. Por lo tanto, es esencial que reciba y supervise el consentimiento de sus destinatarios.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=es)

**Temas relacionados** en la documentación de Campaign Classic v7:

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
