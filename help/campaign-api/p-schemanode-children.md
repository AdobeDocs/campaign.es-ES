---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 25%
---
# children

Devuelve un objeto para el cual cada propiedad es un nodo secundario indizado por su nombre.

```text
children
```

## Observaciones

Ejemplo:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

logInfo(root.children["@firstName"].label)
logInfo(root.children.country.label)

// root.children is a map which :
//   each key is the name of the child
//   each value the corresponding SchemaNode instance
for each(var node in root.children)
{
  logInfo(node.label + " (" + node.type + ")")
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
