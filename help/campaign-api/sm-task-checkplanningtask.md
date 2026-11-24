---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 6%
---
# CheckPlanningTask

Función interna utilizada para comprobar sobrecargas dentro de las programaciones de los operadores de tareas (devuelve &quot;true&quot; en caso de sobrecarga). Esta función también comprueba la coherencia de las programaciones de tareas relacionadas y las actualiza si es necesario.

```text
Boolean workloadAlert = CheckPlanningTask ( Number taskId )
```

## Parámetros

**taskId** Identificador de tarea.

## Valor(es) devuelto(s)

**workloadAlert** Advertencia de sobrecarga de recursos

## Funciones

**Esquema:** [nms:task](s-nms-task.md)

**Estático:**

Sí
