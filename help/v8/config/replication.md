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
source-git-commit: 54837c7da2382696718ace7ec0ebde956efd33f4
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---

# Flujos de trabajo técnicos y duplicación de datos

## Flujos de trabajo técnicos

Adobe Campaign incluye un conjunto de flujos de trabajo técnicos integrados. Los flujos de trabajo técnicos ejecutan procesos o trabajos programados de forma regular en el servidor.

Estos flujos de trabajo realizan operaciones de mantenimiento en la base de datos, aprovechan la información de seguimiento en los registros de envío, crean campañas recurrentes y mucho más.

:arrow_upper_right: La lista completa de flujos de trabajo técnicos se detalla en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

Además de estos flujos de trabajo técnicos, Campaign v8 depende de flujos de trabajo técnicos específicos para administrar [replicación de datos](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Este flujo de trabajo realiza la duplicación automática de las tablas de referencia que deben estar presentes en la base de datos local de Campaign (Postgres) y en la base de datos de Cloud ([!DNL Snowflake]). Está programado para ejecutarse cada hora, diariamente. Si existe el campo **lastModified**, la replicación se produce de forma incremental; de lo contrario, se replica toda la tabla. El orden de las tablas de la matriz siguiente es el orden utilizado por el flujo de trabajo de replicación.
* **[!UICONTROL Replicate Staging data]**
Este flujo de trabajo duplica los datos de ensayo para las llamadas unitarias. Está programado para ejecutarse cada hora, diariamente.
* **[!UICONTROL Deploy FFDA immediately]**\
   Este flujo de trabajo realiza una implementación inmediata en la base de datos de Cloud.
* **[!UICONTROL Replicate FFDA data immediately]**
Este flujo de trabajo duplica los datos XS de una cuenta externa determinada.

Estos flujos de trabajo técnicos están disponibles en el nodo **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** del explorador de Campaign.


**Temas relacionados**

:arrow_upper_right: Obtenga información sobre cómo empezar a usar flujos de trabajo en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

:bulb: Acceda a los períodos de retención de datos en [esta sección](../dev/datamodel-best-practices.md#data-retention)


## Duplicación de datos{#data-replication}

Las tablas se replican desde la base de datos de Campaign a la [!DNL Snowflake] base de datos de Cloud mediante flujos de trabajo dedicados descritos anteriormente.

Las políticas de replicación se basan en el tamaño de la tabla. Se replicarán algunas tablas. Algunas tablas se replicarán en tiempo real, mientras que otras se duplicarán cada hora. Algunas tablas tendrán actualizaciones incrementales cuando otras se reemplacen.

| Área de nombres | Tabla | replicación de flujo de trabajo | Replicación en tiempo real |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | --------------------- |
| **XTK** | xtk:enum<br>xtk:enumValue<br>xtk:enumAlias<br>xtk:folder<br>xtk:formRendering<br>xtk:operator<br>xtk:group<br>xtk:report<br>xtk:olapCube&lt;a<br>xtk8/>xtk:olapDimension<br>xtk:olapMeasure<br>xtk:dictionaryString<br> | Sí (incremental) | Sí |
| **XTK** | xtk:opsecurity<br>xtk:rights<br>xtk:operatorGroup<br>xtk:reportHistory<br>xtk:reportRights | Sí (completo) | Sí |
| **NMS** | nms:budget<br>nms:program<br>nms:operation<br>nms:plan<br>nms:typologyRule<br>nms:typology<br>nms:extAccount<br>nms:deliveryMapping<br>nms:delivery (replicación inmediata<br>nms:delivery) seedMember<br>nms:webApp<br>nms:trackingUrl (replicación inmediata)<br>nms:service<br>nms:offerEnv<br>nms:offerCategory<br>nms:offerSpace<br>nms:offer<br>nms:offerView<br>nms:recipient (incremental)<br>nms:<br>groupnms:<br>dlvExclusionnms:stock | Sí (incremental) | Sí |
| **NMS** | nms:country<br>nms:localOrgUnit<br>nms:state<br>nms:suppressionAddress<br>nms:suppressionDomain<br>nms:category<br>nms:trackingUrlInfo<br>nms:webTrackingLog<br>nms:mobileApp<br>nms:budgetCategory<br>nms:costType<br>nms:costCenter<br>nms:costStructure<br>nms:stockLine<br>nms:costLine<br>nms:costLine | Sí (completo) | Sí |
| **NMS** | nms:address<br>nms:userAgent<br>nms:userAgentReject<br>nms:userAgentStats<br>nms:broadLogMsg<br>nms:broadLog<br>nms:trackingLog<br>nms:deliveryLogStats<br>nms ms:appSubscription<br>nms:proposition<br>nms:rcpGrpRel<br>nms:broadLogRcp<br>nms:excludeLogRcp<br>nms:trackingLogRcp<br>nms:propositionRcp&lt;a 14/>nms:localValidationRcp<br>nms:visitor<br>nms:broadLogVisitor<br>nms:trackingLogVisitor<br>nms:propositionVisitor<br>nms:webAppLogRcp&lt;aRcp 20/>nms:appSubscriptionRcp<br>nms:broadLogAppSubRcp<br>nms:excludeLogAppSubRcp<br>nms:trackingLogAppSubRcp<br>nms:eventHisto&lt;a25/ nms:broadLogEventHisto<br>nms:trackingLogEventHisto<br>nms:subscription<br>nms:subHisto<br>nms:trackingStats (solo uso de Snowflake)<br>nms:tmpBroadcast (solo uso de Snowflake)<br>nms:tmpBroadcastExclusion (solo uso del Snowflake)<br>nms:tmpBroadcastPaper (solo uso del Snowflake)<br><br><br> | No | No |

