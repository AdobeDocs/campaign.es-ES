---
title: Key management in Campaign
description: Get started with key management
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: d3137e75bfc4986e1d6badf32f21fda4c4353c8b
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 3%

---

# Administración de claves y unicidad {#key-management}

[](enterprise-deployment.md) ************

[!DNL Snowflake] [!DNL Snowflake]

Avoiding duplicates on keys, and especially on primary keys, is mandatory to preserve relational database consistency. ************ [!DNL Snowflake]


>[!CAUTION]
>
>Duplicated keys is not restricted to UUIDs. It can happen in with IDs, including custom keys created in custom tables.


## Servicio de unicidad{#unicity-service}

Unicity Service is a Cloud Database Manager component which helps users preserve and monitor the integrity of unique key constraints within Cloud Database tables. Esto le permite reducir el riesgo de insertar claves duplicadas.

As Cloud Database does not enforce unicity constraints, Unicity Service reduces the risk of inserting duplicates when managing the data with Adobe Campaign.

### Unicity workflow{#unicity-wf}

**[!UICONTROL Unicity alerting]**

**[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** ****

This workflow checks all custom and built-in schemas to detect duplicated rows.

![](assets/unicity-alerting-wf.png)

**[!UICONTROL Unicity alerting]****** **[!UICONTROL Administration > Audit > Key Unicity]**

![](assets/unicity-table.png)

As a Database Administrator, you can use a SQL activity to remove the duplicates or contact Adobe Customer Care for more guidance.

### Alerting{#unicity-wf-alerting}

**[!UICONTROL Workflow Supervisors]** ******[!UICONTROL Unicity alerting]**

![](assets/wf-alert-activity.png)


## Additional guardrails{#duplicates-guardrails}

[!DNL Snowflake]

>[!NOTE]
>
>[](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### Delivery preparation{#remove-duplicates-delivery-preparation}

Adobe Campaign removes automatically any duplicated UUID from an audience during delivery preparation. This mechanism prevents any error from happening while preparing a delivery. As an end-user, you can check this information in the delivery logs: some recipients can be excluded from the main target because of duplicated key. `Exclusion of duplicates (based on the primary key or targeted records)`

![](assets/exclusion-duplicates-log.png)

### Update data in a workflow{#duplicates-update-data}

[](enterprise-deployment.md)

![](assets/update-data-no-internal-key.png)

****

1. Deduplicating incoming data (from transition)
1. Deduplicating data with destination table (merge)


![](assets/update-data-deduplicate.png)

>[!CAUTION]
>
>**[!UICONTROL Using reconciliation keys]**


### Query a schema with duplicates{#query-with-duplicates}

[](#unicity-wf) If so, workflow logs a warning as the subsequent operation on the duplicated data should potentially impact workflow result.

![](assets/query-with-duplicates.png)

This check is performed in the following workflow activities:

* Consulta
* Incremental Query
* Lista de lectura