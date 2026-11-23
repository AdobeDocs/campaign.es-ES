---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 5%
---
# Limpieza

Purga el historial de flujo de trabajo.

```text
Cleanup ( String workflowId )
```

## Parámetros

**workflowId** identificador o nombre interno del flujo de trabajo.

## Valor(es) devuelto(s)

Ninguna.

## Observaciones

Elimina todos los eventos procesados, las tareas finalizadas, las tareas fallidas y los mensajes de registro. También elimina el progreso del diagrama si el flujo de trabajo ha finalizado. Este método elimina los datos que ya no utiliza el motor de flujo de trabajo y no afecta al comportamiento del flujo de trabajo.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
