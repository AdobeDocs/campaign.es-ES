---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 5%
---
# SetResolved

Declara una entidad como que no tiene más conflictos.

```text
SetResolved ( String conflictId )
```

## Parámetros

**ConflictId** Identificador de conflicto.

## Valor(es) devuelto(s)

Ninguna.

## Observaciones

Cuando se resuelven todos los conflictos, este método permite volver a colocar la entidad en su lugar normal. Todos los atributos y elementos en conflicto deben resolverse antes de invocar este método.

## Funciones

**Esquema:** [xtk:conflict](s-xtk-conflict.md)

**Estático:**

Sí
