---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%
---
# Responder

Responde a una tarea de tipo de validación en curso.

```text
Reply ( String workflowId, String taskIdentifier, String response, String choice )
```

## Parámetros

**workflowId** identificador o nombre interno del flujo de trabajo.

**taskIdentifier**: El identificador de la tarea de tipo de aprobación (campo @taskIdentifier).

**respuesta** El comentario asociado con la respuesta.

**elección** La elección de la respuesta. Esta opción debe coincidir con el nombre de la transición que se va a activar.

## Valor(es) devuelto(s)

Ninguna.

## Observaciones

El operador actual debe estar en el grupo asignado a la tarea.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
