---
title: 'Introducción al modelo de datos de Campaign '
description: 'Introducción al modelo de datos de Campaign '
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 4%

---

# Introducción al modelo de datos de Campaign {#gs-ac-datamodel}

Adobe Campaign viene con un modelo de datos predefinido. This section gives some details on the built-in tables of the Adobe Campaign data model and their interaction. Adobe Campaign relies on a Cloud database containing tables that are linked together.

The basic structure of the Adobe Campaign data model can be described as follows:

* **** This table stores all the marketing profiles.

   ![](../assets/do-not-localize/glass.png)[](#ootb-profiles)

* **** Usually it is the Delivery table (NmsDelivery). Each record in this table represents a delivery action or a delivery template. It contains all the necessary parameters for performing deliveries such as target, content, etc.

* ****

   Delivery logs are all messages sent to recipients or devices across all channels. The main Delivery logs table (NmsBroadLogRcp) contains the delivery logs for all recipients.
The main Tracking logs table (NmsTrackingLogRcp) stores the tracking logs for all recipients. The tracking logs refer to reactions of recipients, such as email openings and clicks. Each reaction corresponds to a tracking log.
Delivery logs and tracking logs are deleted after a certain period, which is specified in Adobe Campaign and can be modified. Therefore, it is highly recommended to export the logs on a regular basis.

* ****

>[!NOTE]
>
>****

When starting with Adobe Campaign, you need to assess the default data model to check which table is the best suited to store your marketing data.

[](#ootb-profiles) If needed, you can extend it with two mechanisms:

* [](extend-schema.md) For example, you can add a new “Loyalty” field to the Recipient table.
* [](create-schema.md)

![](../assets/do-not-localize/glass.png)[](datamodel-best-practices.md)

## Built-in profile table {#ootb-profiles}

The built-in recipient table (nmsrecipient) in Adobe Campaign provides a good starting point for building your data model. It has a number of pre-defined fields and table links that can be easily extended. This is particularly useful when you are mainly targeting recipients, because it fits a simple recipient-centric data model.

The benefits of using the standard recipient table are:

* Working out-of-the-box with key functionalities such as subscriptions, seed lists, and more
* Providing a marketing database with a recipient-centric data model
* Faster implementation
* Easy maintainance by support and partners

It is possible to extend the recipient table, but not to reduce the number of fields or links in the table.

![](../assets/do-not-localize/glass.png)[](extend-schema.md)

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)

You can also use a different recipient table to better fit with your business or functional requirements. [](custom-recipient.md)

## Campaign tables and Cloud database

[](../architecture/enterprise-deployment.md)

![](../assets/do-not-localize/glass.png)[](../architecture/replication.md)

**Temas relacionados**

![](../assets/do-not-localize/glass.png)[](../start/import.md)![](../assets/do-not-localize/glass.png)[](../start/audiences.md)
