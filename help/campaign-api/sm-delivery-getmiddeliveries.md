---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 19%
---
# GetMidDeliveries

Recupera el estado de los envíos modificados en último lugar en el modo intermediario.

```text
[ XML result, Date nextDate ] = GetMidDeliveries ( Date startDate, Number maxCount, Date emitterDate )
```

## Parámetros

**startDate** Recuperar modificaciones desde esta fecha (en el servidor intermediario).

**maxCount** Número máximo de envíos que se recuperarán, siempre que no se actualicen durante el mismo segundo.

**emitterDate** Fecha de referencia del servidor emisor. Se utiliza para ajustar las fechas de los envíos.

## Valor(es) devuelto(s)

**resultado** Documento de salida, lista de envíos actualizada.

**nextDate** Fecha de inicio de la siguiente llamada.

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
