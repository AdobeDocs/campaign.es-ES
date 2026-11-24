---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 8%
---
# Ejecutar

Ejecuta un flujo de trabajo inmediatamente y espera a que finalice.

```text
XML workflow = Execute ( String workflowId, Boolean simulationMode, Boolean keepResult, Boolean logSQL )
```

## Parámetros

**workflowId** identificador o nombre interno del flujo de trabajo.

**simulationMode** Simulación de ejecución.

**keepResult** Mantener resultados provisionales.

**logSQL** ¿Es necesario guardar un seguimiento de los pedidos SQL?

## Valor(es) devuelto(s)

**flujo de trabajo**: el resultado de la ejecución.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
