---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 33%
---
# BuildPreviewFromId

Se ha creado la previsualización de un contenido para el envío o de una línea del archivo de salida (en modo externo).

```text
[ XML preview, XML queryResult ] = BuildPreviewFromId ( Number deliveryId, XML params ) const
```

## Parámetros

**deliveryId** ID de entrega.

**params** Condición de filtrado de destinatario (@filter = &#39;@id = 5673&#39;), identificador de contenido (@content = &#39;html&#39;, &#39;text&#39;, &#39;sms&#39;, &#39;webContent1&#39;, &#39;outputFile&#39;...), @targetPart = 1345686...

## Valor(es) devuelto(s)

**preview** Devuelve todos los parámetros de la vista previa generada.

**queryResult** Devuelve los datos cargados para calcular la vista previa.

## Ejemplo

```javascript
var res = nms.delivery.BuildPreviewFromId(
                           deliveryId,
                           {params: {content: "html", filter: "@id=1234"}})
var preview     = res[0]
var queryResult = res[1]
```

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
