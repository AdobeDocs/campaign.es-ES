---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%
---
# GetQuarantines

Recupera las últimas cuarentenas y salidas de cuarentena.

```text
[ XML result, Date nextDate, Boolean hasMore ] = GetQuarantines ( Date startDate, String pointerName, Number quarantineCount, Date callerDate )
```

## Parámetros

**startDate** Recupere las cuarentenas modificadas desde esta fecha. Cuando está vacío, se utiliza el valor del puntero.

**pointerName** Recupere las cuarentenas modificadas desde este puntero (opcional).

**quarantineCount** Número máximo de cuarentenas para recuperar, siempre que no se actualicen durante el mismo segundo.

**callerDate** Fecha de referencia del llamador. Permite modificar la fecha de cuarentena referencial (opcional).

## Valor(es) devuelto(s)

**resultado** Documento de salida, lista de cuarentena.

**nextDate** Fecha de la primera cuarentena no recuperada (estrictamente superior a startDate).

**hasMore** Si es así, aún hay cuarentenas que recuperar.

## Funciones

**Esquema:** [nms:address](s-nms-address.md)

**Estático:**

Sí
