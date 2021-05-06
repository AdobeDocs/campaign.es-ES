---
solution: Campaign Classic
product: campaign
title: Flujos de trabajo técnicos y duplicación de datos
description: Flujos de trabajo técnicos y duplicación de datos
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
translation-type: tm+mt
source-git-commit: 9efd6442336a62e627b0da4e17fa742f59f715f9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 2%

---

# Flujos de trabajo técnicos y duplicación de datos

## Flujos de trabajo técnicos

Adobe Campaign incluye un conjunto de flujos de trabajo técnicos integrados. Los flujos de trabajo técnicos ejecutan procesos o trabajos programados de forma regular en el servidor.

Estos flujos de trabajo realizan operaciones de mantenimiento en la base de datos, aprovechan la información de seguimiento en los registros de envío, crean campañas recurrentes y mucho más.

:arrow_upper_right: La lista completa de flujos de trabajo técnicos se detalla en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

Además de estos flujos de trabajo técnicos, Campaign v8 depende de flujos de trabajo técnicos específicos para administrar [replicación de datos](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Este flujo de trabajo realiza la duplicación automática de las tablas de referencia que deben estar presentes en la base de datos local de Campaign (Postgres) y en la base de datos de Cloud (Snowflake). Está programado para ejecutarse cada hora, diariamente. If 
**** lastModifiedfield existe, la replicación se produce gradualmente; de lo contrario, toda la tabla se duplica. El orden de las tablas de la matriz siguiente es el orden utilizado por el flujo de trabajo de replicación.
* **[!UICONTROL Replicate Staging data]**
Este flujo de trabajo duplica los datos de ensayo para las llamadas unitarias. Está programado para ejecutarse cada hora, diariamente.
* **[!UICONTROL Deploy FFDA immediately]**\
   Este flujo de trabajo realiza una implementación inmediata en la base de datos de Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Este flujo de trabajo duplica los datos XS de una cuenta externa determinada.

Estos flujos de trabajo técnicos están disponibles en el nodo **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** del explorador de Campaign.

## Duplicación de datos{#data-replication}

Las tablas se replican desde la base de datos de Campaign a la base de datos de Snowflake Cloud mediante flujos de trabajo específicos descritos anteriormente.

Las políticas de replicación se basan en el tamaño de la tabla. Se replicarán algunas tablas. Algunas tablas se replicarán en tiempo real, mientras que otras se duplicarán cada hora. Algunas tablas tendrán actualizaciones incrementales cuando otras se reemplacen.

**¿DEBEMOS ENUMERAR TODAS LAS TABLAS?**

PARA COMPROBAR

**Temas relacionados**

:arrow_upper_right: Obtenga información sobre cómo empezar a usar flujos de trabajo en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

:bulb: Acceda a los períodos de retención de datos en [esta sección](../dev/datamodel-best-practices.md#data-retention)
