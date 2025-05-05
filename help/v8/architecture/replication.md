---
title: Replicación de datos
description: Flujos de trabajo técnicos y duplicación de datos
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: b8f774ce507cff67163064b6bd1341b31512c08f
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 2%

---


# Replicación de datos {#wf-data-replication}

## Principio

En el contexto de una implementación [Enterprise (FDAC) Deployment](enterprise-deployment.md), la replicación de datos garantiza que las dos bases de datos, la base de datos local de Campaign (PostgreSQL) y la base de datos en la nube ([!DNL Snowflake]), estén operativas en paralelo y permanezcan sincronizadas en tiempo real.

La base de datos en la nube ([!DNL Snowflake]) está optimizada para administrar lotes de datos grandes, como actualizar 1 millón de direcciones. Mientras tanto, la base de datos local de Campaign (PostgreSQL) es más adecuada para operaciones individuales o de pequeño volumen, como actualizar una sola dirección semilla. La sincronización se produce de forma automática y transparente en segundo plano, lo que garantiza que los datos de la base de datos local de Campaign (PostgreSQL) estén duplicados en la base de datos en la nube ([!DNL Snowflake]) en tiempo real, manteniendo ambas bases de datos sincronizadas. La sincronización de datos implica esquemas y tablas, y datos.

➡️ [Descubra cómo funciona la replicación de datos en el vídeo](#video)

## Modos de replicación {#modes}

La replicación de datos puede producirse en diferentes modos según el caso de uso.

* **La replicación sobre la marcha** administra casos en los que la duplicación en tiempo real es esencial. Se basa en subprocesos técnicos específicos para replicar los datos inmediatamente en casos de uso como la creación de una difusión o la actualización de una dirección semilla.
* **Se utiliza la replicación programada** cuando no se requiere la sincronización inmediata. La replicación programada usa [flujos de trabajo técnicos](#workflows) específicos que se ejecutan cada hora para sincronizar datos, como reglas de tipología.

## Políticas de replicación

Las políticas de replicación definen la cantidad de datos que se duplican desde una tabla de la base de datos local de Campaign (PostgreSQL). Estas políticas dependen del tamaño de la tabla y del caso de uso específico. Algunas tablas sufrirán actualizaciones incrementales cuando otras se repliquen por completo. Existen tres tipos principales de directivas de replicación:

* **XS**: esta directiva se usa para tablas con tamaños relativamente pequeños. Toda la tabla se replica de una sola vez. La replicación incremental evita replicar repetidamente los mismos datos utilizando un puntero de marca de tiempo para replicar solo los cambios recientes.
* **SingleRow**: esta directiva replica solamente una fila a la vez. Normalmente se utiliza para la replicación sobre la marcha que incluye objetos de Campaign actuales y objetos relacionados.
* **SomeRows**: esta directiva está diseñada para replicar un subconjunto limitado de datos mediante definiciones o filtros de consulta. Se utiliza para tablas más grandes en las que es necesaria una replicación selectiva.

## Flujos de trabajo de replicación {#workflows}

La versión 8 de Campaign se basa en flujos de trabajo técnicos específicos para administrar la duplicación de datos programada. Estos flujos de trabajo técnicos están disponibles en el nodo **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** del explorador de Campaign. **No se deben modificar.**

Los flujos de trabajo técnicos ejecutan procesos o trabajos, programados de forma regular en el servidor. La lista completa de flujos de trabajo técnicos se detalla en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=es){target="_blank"}.

Los flujos de trabajo técnicos que garantizan la duplicación de datos son los siguientes:

| Flujo de trabajo técnico | Descripción |
|------|-----------|
| **[!UICONTROL Replicate Reference tables]** (ffdaReplicateReferenceTables) | Realiza la replicación automática de tablas integradas que deben estar presentes en la base de datos local de Campaign (PostgreSQL) y en la base de datos en la nube ([!DNL Snowflake]). Está programado para ejecutarse cada hora, a diario. Si existe el campo **lastModified**, la replicación se produce de forma incremental; de lo contrario, se replica toda la tabla. |
| **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) | Replica los datos de ensayo para llamadas unitarias. Está programado para ejecutarse cada hora, a diario. |
| **[!UICONTROL Deploy FFDA immediately]** (ffdaDeploy) | Realiza una implementación inmediata en la base de datos en la nube. |
| **[!UICONTROL Replicate FFDA data immediately]** (ffdaReplicate) | Replica los datos XS de una cuenta externa determinada. |

Si es necesario, puede iniciar la sincronización de datos manualmente. Para ello, haga clic con el botón derecho en la actividad **Planificador** y seleccione **Ejecutar tareas pendientes ahora**.

Además del flujo de trabajo técnico integrado **Replicar tablas de referencia**, puede forzar la replicación de datos en los flujos de trabajo mediante uno de estos métodos

+++Cómo forzar la replicación de datos

* Agregue una actividad **Javascript code** específica con el siguiente código:

  ```
  nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
  ```

  ![](assets/jscode.png)

* Agregue una actividad **nlmodule** específica con el siguiente comando:

  ```
  nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
  ```

  ![](assets/nlmodule.png)

+++

<br/>

>[!NOTE]
>
>La replicación sobre la marcha la gestionan hilos técnicos específicos en lugar de flujos de trabajo. La configuración de este modo se administra en el archivo serverConf.xml. Puede configurar serverConf.xml para que coincida con casos de uso específicos, como solicitar que las tablas XS se repliquen de forma incremental en lugar de por completo. Para obtener más información, póngase en contacto con su representante Adobe.

## API

Las API permiten la replicación de datos personalizados y predeterminados de la base de datos local de Campaign (PostgreSQL) a la base de datos en la nube ([!DNL Snowflake]). Estas API permiten evitar flujos de trabajo predefinidos y personalizar la replicación para requisitos específicos, como la replicación de tablas personalizadas.

Ejemplo:

```
var dataSource = "nms:extAccount:ffda";
var xml = xtk.builder.CopyXxlData(
    <params dataSource={dataSource} policy="xs">
        <srcSchema name="cus:recipient"/>
    </params>
);
```

## Colas de replicación

Cuando se producen volúmenes altos de solicitudes de replicación simultáneamente, pueden surgir problemas de rendimiento en la base de datos en la nube ([!DNL Snowflake]) debido a bloqueos de nivel de tabla durante las operaciones de COMBINACIÓN. Para mitigar esto, los flujos de trabajo de replicación centralizados agrupan las solicitudes en colas.

Cada cola se administra mediante un flujo de trabajo técnico, que administra la replicación de una tabla específica, ejecutando las solicitudes pendientes como una sola operación MERGE. Estos flujos de trabajo se activan cada 20 segundos para procesar nuevas solicitudes de replicación:

| Flujo de trabajo técnico | Descripción |
|------|-----------|
| **Replicar cola de nmsDelivery** (ffdaReplicateQueueDelivery) | Cola para la tabla `nms:delivery`. |
| **Replicar cola nmsDlvExclusion** (ffdaReplicateQueueDlvExclusion) | Cola para la tabla `nms:dlvExclusion`. |
| **Replicar cola nmsDlvMidRemoteIdRel** (ffdaReplicateQueueDlvMidRemoteIdRel) | Cola para la tabla `nms:dlvRemoteIdRel`. |
| **Replicar cola nmsTrackingUrl** (ffdaReplicateQueueTrackingUrl)<br/>**Replicar cola nmsTrackingUrl en simultaneidad** (ffdaReplicateQueueTrackingUrl_2) | Colas en simultaneidad para la tabla `nms:trackingUrl`, que utilizan dos flujos de trabajo para mejorar la eficacia al procesar solicitudes basadas en prioridades diferentes. |

## Tutorial {#video}

Este vídeo presenta los conceptos clave de las bases de datos que utiliza Adobe Campaign v8, por qué se replican los datos, qué datos se replican y cómo funciona el proceso de replicación.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)

Hay disponibles [tutoriales adicionales de la consola del cliente de Campaign v8 aquí](https://experienceleague.adobe.com/es/docs/campaign-learn/tutorials/overview).
