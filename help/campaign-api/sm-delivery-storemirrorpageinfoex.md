---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 22%
---
# StoreMirrorPageInfoEx

Añade información para generar páginas espejo para un conjunto de piezas de envío.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfoEx ( Number deliveryId, Boolean notification, Number partsCount, Number firstPartId, Number notificationId )
```

## Parámetros

**deliveryId** Identificador de envío

**notificación** ¿Es una notificación?

**partsCount** Número de partes

**firstPartId** Identificador de la primera parte

**notificationId** Identificador de notificación

## Valor(es) devuelto(s)

**fatalError** devuelve un código de error que impide que el llamador realice retiradas. De lo contrario, el error puede ser temporal.

**fatalErrorMsg** Mensaje de error asociado con el código de error &quot;fatalError&quot;.

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
