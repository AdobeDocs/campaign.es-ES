---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 3%
---
# EvaluateContent

Evalúa el contenido de un envío vinculado a un pedido. Esta evaluación se realizará al realizar pedidos con derechos de operador y antes de crear la campaña local.

```text
XML result = EvaluateContent ( XML order, Number deliveryId, String contentType, Number seedMemberId )
```

## Parámetros

Elemento **order** que contiene información de pedido.

**deliveryId** ID del envío que se va a evaluar.

**contentType** Tipo de contenido que se va a devolver (html o texto para un correo electrónico; cadena vacía para otros canales).

**seedMemberId**: ID de la dirección semilla utilizada para la personalización del contenido.

## Valor(es) devuelto(s)

**resultado** contenido evaluado.

## Funciones

**Esquema:** [nms:localOrder](s-nms-localorder.md)

**Estático:**

Sí
