---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 14%
---
# joinParts

Devuelve una tabla de instancias de SchemaNode para las que cada elemento representa una condición de la combinación.

```text
joinParts
```

## Observaciones

Cada elemento de la tabla tiene dos propiedades:

* source: el elemento que representa el campo de la tabla de origen.
* destination: el elemento que representa el campo de la tabla de destino.

Ejemplo:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

var link = root.children.country
for each(var join in link.joinParts)
{
  logInfo("src = " + join.source.name)
  logInfo("dst = " + join.destination.name)
}
```

## Funciones

**Propiedad de la clase:** [NodoEsquema](c-schemanode.md)

**Sólo lectura:**

Sí

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
