---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 3%
---
# SetLogin

Cambia la cuenta de ejecución.

```text
SetLogin ( String workflowId, String login )
```

## Parámetros

**workflowId** identificador o nombre interno del flujo de trabajo.

**login** Inicio de sesión del operador o cadena vacía si no hay ningún operador asociado a este flujo de trabajo.

## Valor(es) devuelto(s)

Ninguna.

## Observaciones

La cuenta de ejecución asociada a un flujo de trabajo permite forzar los derechos de ejecución a un operador específico en lugar del operador que inició el flujo de trabajo. La cuenta de ejecución no se propaga cuando se duplica un flujo de trabajo.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
