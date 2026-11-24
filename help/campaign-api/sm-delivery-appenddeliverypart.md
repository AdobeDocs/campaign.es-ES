---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 13%
---
# AppendDeliveryPart

Agregar una parte a un envío que se está preparando.

```text
[ Number deliveryPartId, Number fatalError, String fatalErrorMsg ] = AppendDeliveryPart ( XML deliveryPart, Boolean retry )
```

## Parámetros

**deliveryPart** documento que representa la parte del envío (o una colección de partes del envío).

**reintentar** especifica si se trata de un nuevo intento de enviar esta parte del envío.

## Valor(es) devuelto(s)

**deliveryPartId** Identificador de la parte del envío en la base de datos (cuando no es una colección).

**fatalError** devuelve un código de error que impide que el llamador realice retiradas. De lo contrario, el error puede ser temporal.

**fatalErrorMsg** Mensaje de error asociado con el código de error &quot;fatalError&quot;.

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
