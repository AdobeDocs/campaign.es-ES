---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%
---
# GetReportData

```text
XML result = GetReportData ( Number cubeId, String queryDef, Boolean selectAll, Boolean useAggregates, XML cube )
```

## Parámetros

**cubeId** Identificador de cubo. Se puede establecer en 0 si el cubo se pasa como parámetro.

**queryDef** QueryDef definido en el informe

**selectAll** Seleccionar todo

**useAggregates** Habilitar el uso agregado

**cubo** XML que describe el cubo.

## Valor(es) devuelto(s)

**resultado** resultado

## Funciones

**Esquema:** [xtk:olapCube](s-xtk-olapcube.md)

**Estático:**

Sí
