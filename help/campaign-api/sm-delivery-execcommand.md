---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 26%
---
# ExecCommand

Ejecutar un comando en un envío.

```text
Number newState = ExecCommand ( String deliveryId, String command )
```

## Parámetros

**deliveryId** Identificador de envío

**comando** Nombre de comando (&#39;reproducir&#39;, &#39;pausa&#39; o &#39;detención&#39;)

## Valor(es) devuelto(s)

**newState** Estado de entrega después de ejecutar el comando

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
