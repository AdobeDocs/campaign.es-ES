---
title: Flujos de trabajo técnicos y duplicación de datos
description: Flujos de trabajo técnicos y duplicación de datos
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# Flujos de trabajo técnicos y duplicación de datos {#wf-data-replication}

## Flujos de trabajo técnicos {#tech-wf}

En el contexto de una [implementación empresarial (FDAC)](enterprise-deployment.md), Adobe Campaign incluye un conjunto de flujos de trabajo técnicos integrados. Los flujos de trabajo técnicos ejecutan procesos o trabajos, programados de forma regular en el servidor.

Estos flujos de trabajo realizan operaciones de mantenimiento en la base de datos, aprovechan la información de seguimiento en los registros de envío, crean campañas recurrentes y mucho más.

La lista completa de flujos de trabajo técnicos se detalla en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}.

Además de estos flujos de trabajo técnicos, Campaign v8 se basa en flujos de trabajo técnicos específicos para administrar [la replicación de datos](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Este flujo de trabajo realiza la replicación automática de las tablas integradas que deben estar presentes en la base de datos local de Campaign (Postgres) y en la base de datos en la nube ([!DNL Snowflake]). Está programado para ejecutarse cada hora, a diario. Si existe el campo **lastModified**, la replicación se produce de forma incremental; de lo contrario, se replica toda la tabla. El orden de las tablas de la matriz siguiente es el orden utilizado por el flujo de trabajo de replicación.
* **[!UICONTROL Replicate Staging data]**
Este flujo de trabajo duplica los datos de ensayo para las llamadas unitarias. Está programado para ejecutarse cada hora, a diario.
* **[!UICONTROL Deploy FFDA immediately]**\
  Este flujo de trabajo realiza una implementación inmediata en la base de datos en la nube.
* **[!UICONTROL Replicate FFDA data immediately]**
Este flujo de trabajo duplica los datos XS de una cuenta externa determinada.

Estos flujos de trabajo técnicos están disponibles en el nodo **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** del explorador de Campaign. **No se deben modificar.**

Si es necesario, puede iniciar la sincronización de datos manualmente. Para ello, haga clic con el botón derecho en la actividad **Planificador** y seleccione **Ejecutar tareas pendientes ahora**.

## Replicación de datos {#data-replication}

Algunas tablas integradas se duplican de la base de datos local de Campaign a la base de datos en la nube [!DNL Snowflake] mediante los flujos de trabajo dedicados descritos anteriormente.

Comprenda qué bases de datos utiliza Adobe Campaign v8, por qué se replican los datos, qué datos se replican y cómo funciona el proceso de replicación.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### Políticas de replicación de datos {#data-replication-policies}

Las políticas de replicación se basan en el tamaño de las tablas. Algunas tablas se duplican en tiempo real, mientras que otras lo hacen cada hora. Algunas tablas sufrirán actualizaciones incrementales cuando otras se sustituyan.

Además del flujo de trabajo técnico integrado **Replicar tablas de referencia**, puede forzar la replicación de datos en sus flujos de trabajo.

Puede hacer lo siguiente:

* agregue una actividad **Javascript code** específica con el siguiente código:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* agregue una actividad **nlmodule** específica con el siguiente comando:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**Temas relacionados**

* [Aprenda a empezar con los flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=es){target="_blank"}

* [Períodos de retención de datos](../dev/datamodel-best-practices.md#data-retention)
