---
solution: Campaign v8
product: Adobe Campaign
title: Flujos de trabajo técnicos y duplicación de datos
description: Flujos de trabajo técnicos y duplicación de datos
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 3%

---

# Flujos de trabajo técnicos y duplicación de datos

## Flujos de trabajo técnicos{#tech-wf}

Adobe Campaign incluye un conjunto de flujos de trabajo técnicos integrados. Los flujos de trabajo técnicos ejecutan procesos o trabajos programados de forma regular en el servidor.

Estos flujos de trabajo realizan operaciones de mantenimiento en la base de datos, aprovechan la información de seguimiento en los registros de envío, crean campañas recurrentes y mucho más.

[!DNL :arrow_upper_right:] La lista completa de flujos de trabajo técnicos se detalla en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)


Además de estos flujos de trabajo técnicos, Campaign v8 depende de flujos de trabajo técnicos específicos para administrar [replicación de datos](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Este flujo de trabajo realiza la duplicación automática de las tablas integradas que deben estar presentes en la base de datos local de Campaign (Postgres) y en la base de datos de Cloud ([!DNL Snowflake]). Está programado para ejecutarse cada hora, diariamente. Si existe el campo **lastModified**, la replicación se produce de forma incremental; de lo contrario, se replica toda la tabla. El orden de las tablas de la matriz siguiente es el orden utilizado por el flujo de trabajo de replicación.
* **[!UICONTROL Replicate Staging data]**
Este flujo de trabajo duplica los datos de ensayo para las llamadas unitarias. Está programado para ejecutarse cada hora, diariamente.
* **[!UICONTROL Deploy FFDA immediately]**\
   Este flujo de trabajo realiza una implementación inmediata en la base de datos de Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Este flujo de trabajo duplica los datos XS de una cuenta externa determinada.

Estos flujos de trabajo técnicos están disponibles en el nodo **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** del explorador de Campaign. **No deben modificarse.**

Si es necesario, puede iniciar la sincronización de datos manualmente. Para ello, haga clic con el botón derecho en la actividad **Scheduler** y seleccione **Execute pending task(s) now**.

## Duplicación de datos{#data-replication}

Algunas tablas integradas se replican desde la base de datos local de Campaign a la base de datos de [!DNL Snowflake] Cloud mediante flujos de trabajo dedicados descritos anteriormente.

Las políticas de replicación se basan en el tamaño de las tablas. Algunas tablas se duplicarán en tiempo real, otras se duplicarán cada hora. Algunas tablas tendrán actualizaciones incrementales cuando otras se reemplacen.

Además del flujo de trabajo técnico integrado **Replicate Reference Tables**, puede forzar la duplicación de datos en sus flujos de trabajo.

Puede:

* añada una actividad **Javascript code** específica con el siguiente código:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* añada una actividad específica **nlmodule** con el siguiente comando:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)

**Temas relacionados**

[!DNL :arrow_upper_right:] Obtenga información sobre cómo empezar a utilizar flujos de trabajo en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

[!DNL :bulb:] Acceso a los períodos de retención de datos en  [esta sección](../dev/datamodel-best-practices.md#data-retention)
