---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 3%
---
# WakeupTask

Obliga al procesamiento avanzado de una o varias tareas pendientes.

```text
WakeupTask ( String workflowId, String taskIdentifier, String activityName )
```

## Parámetros

**workflowId** identificador o nombre interno del flujo de trabajo.

**taskIdentifier**: El identificador de la tarea (campo @taskIdentifier) o una cadena vacía para forzar el procesamiento anticipado de todas las tareas pendientes asociadas a una actividad determinada.

**activityName**: nombre de la actividad para forzar el procesamiento anticipado de todas las tareas asociadas o una cadena vacía.

## Valor(es) devuelto(s)

Ninguna.

## Observaciones

Si no se especifican taskIdentifier ni activityName, se tienen en cuenta todas las tareas pendientes.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
