---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%
---
# EvaluateTargetFromId

Evalúa la segmentación de la campaña para cada envío de campaña vinculado a un pedido. Esta evaluación se realizará al realizar pedidos con derechos de operador y antes de crear la campaña local.

```text
XML result = EvaluateTargetFromId ( Number orderId )
```

## Parámetros

ID de pedido **orderId**.

## Valor(es) devuelto(s)

**result** Resultado de los recuentos de cada una de las entregas de la campaña.

## Funciones

**Esquema:** [nms:localOrder](s-nms-localorder.md)

**Estático:**

Sí
