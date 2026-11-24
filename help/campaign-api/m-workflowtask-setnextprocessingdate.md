---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# setNextProcessingDate

Fuerza la siguiente fecha de procesamiento por la tarea.

```text
setNextProcessingDate (timestamp)
```

## Parámetros

**marca de tiempo** Siguiente fecha de procesamiento. Si está vacío, el siguiente procesamiento será inmediato.

## Valor devuelto

Ninguna.

## Observaciones

* Si se utiliza este método, se anula la siguiente fecha de procesamiento si la proporciona el planificador.
* El siguiente procesamiento siempre lo realiza la función \*\_reminder().

## Funciones

**Método de clase:** [WorkflowTask](c-workflowtask.md)

**Disponible en:**

* Flujo de trabajo
