---
title: Arquitectura general
description: Obtenga más información acerca la arquitectura y los componentes de Campaign
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: 79a220ad9c9c372b64db9a33efc1843c95a2a619
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 6%

---

# Arquitectura general{#general-architecture}

The typical Adobe Campaign solution deployment consists of the following components:

* ****

   Intuitive graphical interface in which users can communicate and track marketing offers, create campaigns, review and manage all marketing activities, programs and plans - including emails, workflows and landing pages -, create and manage customer profiles, and create audiences.

* ****

   Server-side software that executes the marketing campaigns through chosen communication channels, including emails, SMS, push notifications, direct mail, web or social, based on the rules and workflows defined in the user interface.

* ****

   Based on relational database technology, the Adobe Campaign Cloud Database stores all information, campaign components, offers, workflows, and campaign results in database containers.

## Personalized Client Environment {#client-env}

The application can be accessed in different ways: Rich client, Thin client, or API integration.

![](../assets/do-not-localize/glass.png)[](../start/ac-components.md)

## Development environment {#dev-env}

Adobe Campaign is a single platform with different applications to create an open and scalable architecture. The Adobe Campaign platform is written on a flexible application layer and is easily configurable to meet your business needs. The distributed architecture ensures linear system scalability scaling from thousands of messages to millions of messages.

Some Campaign modules operate continuously, while others are started up occasionally to perform administrative tasks (e.g. to configure the database connection) or to run a recurrent task (e.g. consolidating tracking information).

There are three types of Adobe Campaign modules:

* **** This applies to the following modules: web, syslogd, trackinglogd and watchdog.
* **** This applies to the following modules: mta, wfserver, inMail, sms and stat.
* ****

The main processes are:

* **** Furthermore, it can dynamically generate the Web pages used for HTML-based access (reports, Web forms, etc). To achieve this, this process includes an Apache Tomcat JSP server. This is the process to which the Console connects.

* **** It also handles periodically executed technical workflows, including:

   * ****
   * ****
   * ****

* **** This process functions as an SMTP mail transfer agent (MTA). It performs &quot;one-to-one&quot; personalization of messages and handles their physical delivery. It runs using delivery jobs and handles automatic retries. In addition, when tracking is enabled, it automatically replaces the URLs so that they point to the redirection server. This process can handle the customization and automatic sending to a third-party router for SMS, fax and direct mail.

* **** To achieve this, the URLs incorporated in the email messages are rewritten in order to point to this module, which registers the passing of the internet user before redirecting them to the required URL.

   To guarantee highest availability, this process is fully independent from the database: the other server processes communicate with it using SOAP calls (HTTP, HTTP(S) and XML) only. Technically, this functionality is implemented in an extension module of an HTTP server (ISAPI extension in IIS, or a DSO Apache module, etc.) and is available in Windows only.

Other more technical processes are also available:

* **** These messages then undergo rule-based processing to determine the reasons for non-delivery (unknown recipient, quota exceeded, etc.) and to update the delivery status in the database. All these operations are fully automatic and preconfigured.

* ****

* **** This makes ample information available for diagnosis in case of problems.

* ****

* ****

* **** It also monitors them and relaunches them automatically in case of incidents, thus maintaining maximum system uptime.

* **** It also lets you federate several instances or machines if they share the same public IP addresses.

## Database containers {#db-containers}

[!DNL Snowflake] and the work data (purchases, leads) for the solution, and all Adobe Campaign components communicate with the database in order to perform their specific tasks.

You can deploy Adobe Campaign using the pre-defined database and schemas, and if needed this pre-defined environment can be extended. All data within the data mart is accessed by Adobe Campaign via SQL calls. Adobe Campaign also provides a full complement of Extract Transform and Load (ETL) tools to perform data import and export of data into and out of the system.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Con **Campaign Managed Cloud Services**, su entorno y la configuración inicial se han configurado con Adobe, según los términos del acuerdo de licencia. No se le permite modificar paquetes integrados, esquemas integrados o informes instalados.
>
>Si necesita utilizar un complemento de Campaign o una funcionalidad específica que no se haya aprovisionado por usted, debe ponerse en contacto con el **Servicio de atención al cliente de Adobe**.