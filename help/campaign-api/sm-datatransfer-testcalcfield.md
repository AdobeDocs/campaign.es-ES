---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 27%
---
# TestCalcField

Pruebe el campo calculado utilizando las líneas de ejemplo almacenadas en el script.

```text
XML calcFieldValues = TestCalcField ( XML dataTransferStep, String calcFieldName )
```

## Parámetros

**dataTransferStep**: paso de transferencia de datos donde se define el campo calculado

**calcFieldName** Campo calculado para probar

## Valor(es) devuelto(s)

**calcFieldValues** Devuelve la lista de valores para cada línea de muestra (calcFieldValues/línea) y el nombre de campo (calcFieldValues/@name)

## Funciones

**Esquema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Estático:**

Sí
