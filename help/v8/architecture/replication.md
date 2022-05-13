---
title: Technical workflows and data replication
description: Technical workflows and data replication
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: 36b7a7be766febca4448c6114f5acac35e30873a
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 3%

---

# Technical workflows and data replication

## Flujos de trabajo técnicos{#tech-wf}

[](enterprise-deployment.md) Technical workflows execute processes or jobs, scheduled on a regular basis on the server.

These workflows perform maintenance operations on the database, leverage the tracking information in the delivery logs, create recurring campaigns, and more.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)

[](#data-replication)

* **[!UICONTROL Replicate Reference tables]**[!DNL Snowflake] It is scheduled to execute every hour, daily. **** The order of the tables in the array below is the order used by the replication workflow.
* **[!UICONTROL Replicate Staging data]** It is scheduled to execute every hour, daily.
* **[!UICONTROL Deploy FFDA immediately]**\
   This workflow performs an immediate deployment to the Cloud database.
* **[!UICONTROL Replicate FFDA data immediately]**

**[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** **No deben modificarse.**

If needed, you can launch data synchronization manually. ********

## Replicación de datos{#data-replication}

[!DNL Snowflake]

Understand which databases Adobe Campaign v8 uses, why data is being replicated, which data is being replicated and how the replication process works.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### Data replication policies

Replication policies are based on the size of the tables. Some tables will be replicated in real-time, some others will be replicated on hourly basis. Some tables will have incremental updates when others will be replaced.

****

Puede hacer lo siguiente:

* ****

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* ****

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**Temas relacionados**

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

![](../assets/do-not-localize/glass.png)[](../dev/datamodel-best-practices.md#data-retention)
