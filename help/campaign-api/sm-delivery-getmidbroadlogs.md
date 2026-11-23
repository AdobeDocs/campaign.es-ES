---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# GetMidBroadLog

Recupera los registros de envío modificados en último lugar en el modo intermediario.

```text
[ XML result, Date nextDate ] = GetMidBroadLogs ( Date startDate, Number logCount, Date emitterDate )
```

## Parámetros

**startDate** Recuperar registros modificados desde esta fecha (en el servidor intermediario).

**logCount** número máximo de registros que se recuperarán, siempre que no se hayan actualizado en el mismo segundo.

**emitterDate** Fecha de referencia del servidor emisor. Se utiliza para ajustar las fechas del registro de envío.

## Valor(es) devuelto(s)

**resultado** Documento de salida, lista de registros de envío.

**nextDate** Fecha del primer registro recuperado (mayor que startDate).

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
