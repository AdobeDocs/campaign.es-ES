---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 23%
---
# StoreMirrorPageInfo

Añade información para generar páginas espejo para un conjunto de piezas de envío.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfo ( Number deliveryId, Number partsCount, Number firstPartId, Number lastPartId )
```

## Parámetros

**deliveryId** Identificador de envío

**partsCount** Número de partes

**firstPartId** Identificador de la primera parte

**lastPartId** Identificador de la última parte

## Valor(es) devuelto(s)

**fatalError** devuelve un código de error que impide que el llamador realice retiradas. De lo contrario, el error puede ser temporal.

**fatalErrorMsg** Mensaje de error asociado con el código de error &quot;fatalError&quot;.

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
