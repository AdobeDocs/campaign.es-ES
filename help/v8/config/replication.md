---
title: Flujos de trabajo técnicos y duplicación de datos
description: Flujos de trabajo técnicos y duplicación de datos
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: e55a60ae1628e534e32e86d347457b6c208db75b
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 3%

---

# Flujos de trabajo técnicos y duplicación de datos

## Flujos de trabajo técnicos{#tech-wf}

Adobe Campaign incluye un conjunto de flujos de trabajo técnicos integrados. Los flujos de trabajo técnicos ejecutan procesos o trabajos programados de forma regular en el servidor.

Estos flujos de trabajo realizan operaciones de mantenimiento en la base de datos, aprovechan la información de seguimiento en los registros de envío, crean campañas recurrentes y mucho más.

![](../assets/do-not-localize/book.png) La lista completa de flujos de trabajo técnicos se detalla en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;}


Además de estos flujos de trabajo técnicos, Campaign v8 depende de flujos de trabajo técnicos específicos para administrar [replicación de datos](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Este flujo de trabajo realiza la duplicación automática de las tablas integradas que deben estar presentes en la base de datos local de Campaign (Postgres) y en la base de datos de Cloud ([!DNL Snowflake]). Está programado para ejecutarse cada hora, diariamente. If **lastModified** existe, la replicación se produce gradualmente, de lo contrario toda la tabla se duplica. El orden de las tablas de la matriz siguiente es el orden utilizado por el flujo de trabajo de replicación.
* **[!UICONTROL Replicate Staging data]**
Este flujo de trabajo duplica los datos de ensayo para las llamadas unitarias. Está programado para ejecutarse cada hora, diariamente.
* **[!UICONTROL Deploy FFDA immediately]**\
   Este flujo de trabajo realiza una implementación inmediata en la base de datos de Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Este flujo de trabajo duplica los datos XS de una cuenta externa determinada.

Estos flujos de trabajo técnicos están disponibles en la **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** del explorador de Campaign. **No deben modificarse.**

Si es necesario, puede iniciar la sincronización de datos manualmente. Para ello, haga clic con el botón derecho en el **Planificador** actividad y seleccione **Ejecutar ahora las tareas pendientes**.

## Replicación de datos{#data-replication}

Algunas tablas integradas se replican de la base de datos local de Campaign a [!DNL Snowflake] Base de datos en la nube con flujos de trabajo dedicados descritos anteriormente.

Comprender qué bases de datos utiliza Adobe Campaign v8, por qué se replican los datos, qué datos se replican y cómo funciona el proceso de replicación.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### Políticas de replicación de datos

Las políticas de replicación se basan en el tamaño de las tablas. Algunas tablas se duplicarán en tiempo real, otras se duplicarán cada hora. Algunas tablas tendrán actualizaciones incrementales cuando otras se reemplacen.

Además del **Replicar tablas de referencia** flujo de trabajo técnico , puede forzar la duplicación de datos en los flujos de trabajo.

Puede hacer lo siguiente:

* añadir un **Código JavaScript** actividad con el siguiente código:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* añadir un **nlmodule** actividad con el siguiente comando:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)



**Temas relacionados**

![](../assets/do-not-localize/book.png) Obtenga información sobre cómo empezar a utilizar flujos de trabajo en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}

![](../assets/do-not-localize/glass.png) Acceso a los períodos de retención de datos en [esta sección](../dev/datamodel-best-practices.md#data-retention)
