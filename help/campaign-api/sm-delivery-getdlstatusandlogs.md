---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 33%
---
# GetDlStatusAndLogs

Recupere los últimos registros del historial y el estado de envío.

```text
[ Number deliveryState, XML returnLogs ] = GetDlStatusAndLogs ( Number deliveryId, Number lastLogId )
```

## Parámetros

**deliveryId** Identificador de envío

**lastLogId** Identificador de la última entrada de diario devuelta en la llamada anterior

## Valor(es) devuelto(s)

**deliveryState** Estado de entrega

**returnLogs** mensajes de registro

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
