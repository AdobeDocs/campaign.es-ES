---
title: Get started with Campaign FDA-Snowflake deployment
description: Get started with Campaign FDA-Snowflake deployment
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 355b9219ffd9d481d15d2d0982d49923842cc27b
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign][!DNL Snowflake]{#gs-fda-snowflake}

[!DNL Snowflake][!DNL Adobe Campaign][!DNL Snowflake][](../connect/fda.md)[!DNL Snowflake]

## Ventajas{#fda-benefits}

This deployment model comes with the following benefits:

* ****[!DNL Snowflake] This architecture also reduce your dependency to PostgreSQL storage and performances limits. As less data is stored in Campaign database, performances are better and maintenance tasks are performed faster.

* ****[!DNL Snowflake]

   [!DNL Snowflake] Only aggregates and temporary tables are moved to Campaign for personalization and delivery purpose.


## Arquitectura{#fda-archi}

[!DNL Snowflake] It provides users with the ability to unlock deep value from their data by offering a single, unified, and easy-to-use platform for data analysis. The cloud data platform requires no management as it infinitely scales to support any volume of marketing data from Adobe Campaign.

General communication between servers and processes is carried out according to the following schema:

![](assets/fda-architecture.png)

PostgreSQL is the primary database, and Snowflake is the secondary database. You can extend your data model and store your data on Snowflake. Subsequently, you can run ETL, segmentation and reports on a large data set with outstanding performances.
