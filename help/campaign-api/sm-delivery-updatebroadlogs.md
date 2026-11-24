---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 31%
---
# UpdateBroadLogs

Actualizar el estado de los registros de envío, realizar el control de errores y actualizar los contadores de envío.

```text
UpdateBroadLogs ( Number deliveryId, XML logs, Boolean deliveryMustExist )
```

## Parámetros

**deliveryId** Identificador de envío

**logs** colección que contiene los registros nms:broadLog que se van a actualizar (se deben especificar @id, @status, @eventDate y @lastModified)

**deliveryMustExist** especifica si se genera un error para un identificador de envío no válido.

## Valor(es) devuelto(s)

Ninguna.

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
