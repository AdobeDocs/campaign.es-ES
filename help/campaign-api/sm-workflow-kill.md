---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 3%
---
# Matar

Detiene incondicionalmente un flujo de trabajo.

```text
Kill ( String workflowId )
```

## Parámetros

**workflowId** identificador o nombre interno del flujo de trabajo.

## Valor(es) devuelto(s)

Ninguna.

## Observaciones

Este método es útil si un flujo de trabajo no se puede detener normalmente. Esto puede suceder si el flujo de trabajo o una tarea tienen una afinidad en particular o si el módulo wfserver que gestiona esta afinidad ya no se ejecuta. En este caso, el flujo de trabajo permanece marcado como &quot;Detener solicitado&quot; y solo puede detenerse mediante el comando Kill.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
