---
title: Notas de la versión de Campaign v8 anticipadas
description: Versión anterior de Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---

# Notas de las versiones anteriores {#e-new-release}

Esta página describe las mejoras y correcciones incluidas en la próxima versión de Campaign v8. Este contenido está sujeto a cambios sin previo aviso hasta la fecha de lanzamiento. Las notas de la versión oficiales están disponibles en [página](../start/release-notes.md).

## Versión 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> La actualización de la consola de cliente es obligatoria. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#download-ac-console).

_7 de octubre de 2022_

**Mejoras**

* Se ha corregido un problema que afectaba a las actualizaciones de estado del registro de entrega en la instancia MID, cuando la opción FeatureFlag_GZIP_Compression estaba activada. (NEO-49183)
* La variable **Database cleanup** el flujo de trabajo técnico ahora también gestiona los esquemas de ensayo personalizados. (NEO-48974)
* Se ha corregido un problema que podía hacer que los envíos permanecieran en **Pendiente** aunque se alcance la fecha de contacto. (NEO-48079, NEO-48251)
* Se ha mejorado la estabilidad al gestionar cadenas XML no válidas durante las llamadas SOAP. (NEO-48027)
* Se ha corregido un problema que podía ralentizar el análisis de envío, durante el paso de exclusión de destinatarios incluida en la lista de bloqueados, al dirigirse a grandes volúmenes de destinatarios. (NEO-48019)
* Para evitar la lentitud al enviar la prueba a las direcciones semilla, todas las réplicas consecutivas de los miembros semilla ahora se agrupan en una solicitud de replicación. (NEO-44844)
* Se ha corregido un problema que provocaba problemas de personalización al enviar mensajes SMS mediante un modo de envío externo. (NEO-46415)
* Se ha corregido un problema que mostraba un error al intentar previsualizar un envío en cualquier evento archivado del Centro de mensajes. (NEO-43620)
* Se ha corregido un problema en los flujos de trabajo que podía impedir que los archivos se actualizaran en el servidor al usar la variable **Carga de datos (archivos)** actividad. El proceso se detuvo al 100% pero nunca terminó. (NEO-47269)
* Se ha corregido un problema que provocaba la creación de elementos DeliveryParts innecesarios cuando el envío utilizaba modos de calendario y división. (NEO-48634)
* Se ha corregido un problema de rendimiento al usar olas basadas en calendario. (NEO-48451)
* Se ha corregido un problema que podría provocar un mensaje de error en la pantalla de la lista de envíos después de crear una nueva asignación de destino en un esquema personalizado. (NEO-49237)
* Se ha corregido un problema que se podía producir si un envío alcanzaba un tamaño específico durante el proceso de MTA. (NEO-46097)
* Se ha corregido un problema que impedía que los registros de seguimiento devolvieran datos relacionados con el explorador del destinatario. (NEO-46612)
* Se ha corregido un problema durante la posactualización en entornos japoneses. (NEO-46640)
* Se ha corregido un problema que se producía al usar la variable **Consulta** actividad y filtrado de una tabla. Cuando un nombre de columna contenía la palabra &quot;Actualización&quot;, se producía un error de compilación con un identificador no válido y el siguiente mensaje: &quot;número de filas actualizadas&quot;. (NEO-46485)
* Se ha corregido un problema que impedía que la variable **[!UICONTROL Replicate Staging data]** El flujo de trabajo técnico (ffdaReplicateStagingData) no se detiene aunque se produzca un error durante su ejecución. (NEO-46280)
* Se ha corregido un problema que podía causar pérdida de datos si el flujo de trabajo de ensayo estaba en error y el período de retención había pasado completamente. (NEO-48975)
* Se ha corregido un problema que se producía al insertar datos en la base de datos de nube de Snowflake con una campaña **Consulta** actividad y **Cambiar fuente de datos** actividad: el proceso fallaba cuando había un carácter de barra invertida presente en los datos. La cadena de origen no se escapó y los datos no se procesaron correctamente en el Snowflake. (NEO-45549)
