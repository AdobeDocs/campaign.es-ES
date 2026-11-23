---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 21%
---
# QueueNotification

Solicitud para poner en cola una notificación que hace referencia a una plantilla de envíos.

```text
QueueNotification ( String scenarioName, XML target )
```

## Parámetros

**scenarioName** nombre interno de la plantilla

**destino** Población de destinatarios de envío

## Valor(es) devuelto(s)

Ninguna.

## Observaciones

Esta API solo se puede utilizar en el contexto de aplicaciones web o encuestas en línea. A diferencia de SubmitNotification, QueueNotification usa un subproceso dedicado para las notificaciones en cola.

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
