---
title: Get started with Campaign architecture
description: Descubra los entornos y los conceptos básicos de implementación
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 355b9219ffd9d481d15d2d0982d49923842cc27b
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 13%

---

# Get Started with Campaign architecture{#gs-ac-archi}

## Environments {#environments}

Campaign is made available as individual instances with each instance representing a complete Campaign environment.

Two types of environments available with Campaign Cloud Service:

* ****

* ****

You can export and import packages from one environment to another.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## Deployment model{#ac-deployment}

[](enterprise-deployment.md)[!DNL Adobe Campaign][!DNL Campaign][!DNL Snowflake]

**** With this new architecture, Campaign v8 Enterprise (FFDA) deployment simplifies data management: no index is required on the Cloud Database. Basta con crear las tablas, copiar los datos y empezar. La tecnología de la base de datos en la nube no requiere un mantenimiento específico para garantizar el nivel de rendimiento.



<!--Two deployment models are available:

* **Campaign FDA [!DNL Snowflake] deployment**

In its [[!DNL Snowflake] FDA deployment](fda-deployment.md), [!DNL Adobe Campaign] v8 is connected to [!DNL Snowflake] to access data through Federated Data Access capability: you can access and process external data and information stored in your [!DNL Snowflake] database without changing the structure of Adobe Campaign data. PostgreSQL is the primary database, and Snowflake is the secondary database. You can extend your data model and store your data on Snowflake. Subsequently, you can run ETL, segmentation and reports on a large data set with outstanding performances.

* **Campaign Enterprise (FFDA) deployment**

-->

## Message Center architecture{#transac-msg-archi}

La mensajería transaccional (Centro de mensajes) es el módulo de Campaign diseñado para gestionar mensajes de activación.

![](../assets/do-not-localize/glass.png)[](../send/transactional.md)

In response to an action of a customer on a website, an event is sent Campaign through a REST API, and the message template is populated with the information or data provided through the API call, and a transactional message is sent in real-time to the customer. Estos mensajes se pueden enviar por separado o en serie por correo electrónico, SMS o notificaciones push.

In this specific architecture, execution cell is separated from the control instance to ensure high availability and load management.

* **** This instance also centralize event monitoring and history.

   ![](../assets/do-not-localize/glass.png)[](../send/transactional.md)

* **** There can be more than one execution instance to process messages via the load-balancer and scale the number of events to be proceeded for maximum availability.

>[!CAUTION]
>
>La instancia de control y las instancias de ejecución deben estar instaladas en diferentes equipos. No pueden compartir la misma instancia de Campaign.

![](assets/messagecenter_diagram.png)

### Autenticación

To use these capabilities, Adobe Campaign users log on to the control instance to create transactional message templates, generate the message preview using a seed list, display reports and monitor execution instance(s).

* Single execution instance
When interacting with an Adobe hosted Message Center execution instance, an external system can first retrieve a session token (that by default expires in 24 hours), by making an api call to the session logon method, using a provided account login and password.
Then, with the sessionToken provided by the execution instance in response to the above call, the external application can make SOAP api invocations (rtEvents or batchEvents) to send communications, without the need to include in each SOAP call the account login and password.

* Multiple execution instances
In a multi-cell execution architecture with multiple execution instances behind a load balancer, the logon method invoked by the external application is going through the load balancer: for that reason, a token-based authentication cannot  be used. A user/password-based authentication is required.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel)