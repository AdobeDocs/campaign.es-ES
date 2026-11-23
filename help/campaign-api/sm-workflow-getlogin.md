---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 2%
---
# GetLogin

Devuelve información de la cuenta de ejecución.

```text
[ Number id, String login, String cs ] = GetLogin ( String workflowId )
```

## Parámetros

**workflowId** identificador o nombre interno del flujo de trabajo.

## Valor(es) devuelto(s)

**id** identificador del operador o 0 si no hay ningún operador asociado a este flujo de trabajo.

**login** Inicio de sesión del operador o cadena vacía si no hay ningún operador asociado a este flujo de trabajo.

**cs**: cadena de descripción del operador o cadena vacía si no hay ningún operador asociado a este flujo de trabajo.

## Observaciones

La cuenta de ejecución asociada a un flujo de trabajo permite forzar los derechos de ejecución a un operador específico en lugar del operador que inició el flujo de trabajo. La cuenta de ejecución no se propaga cuando se duplica un flujo de trabajo.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
