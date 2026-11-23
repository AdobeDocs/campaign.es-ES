---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 2%
---
# GetValidationParameters

Devuelve los parámetros de una tarea de flujo de trabajo en curso.

```text
XML content = GetValidationParameters ( String workflowId, String taskIdentifier )
```

## Parámetros

**workflowId** identificador o nombre interno del flujo de trabajo.

**taskIdentifier**: El identificador de la tarea de tipo de aprobación (campo @taskIdentifier).

## Valor(es) devuelto(s)

**content**: documento XML que contiene los parámetros.

## Observaciones

El documento devuelto contiene toda la información relativa a la validación, quién respondió y quién puede responder.

* Los atributos title, creationDate, processingDate, timeout, status, abortReason y completionDate corresponden a los atributos de la tarea de validación.
* isAssignee: el operador actual está en el grupo asignado a esta tarea.
* hasResponded: el operador actual ya ha respondido.
* canReply: el operador actual puede responder (nadie ha respondido todavía) o se autorizan varias respuestas.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
