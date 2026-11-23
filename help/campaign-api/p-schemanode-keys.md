---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '35'
ht-degree: 28%
---
# teclas

Devuelve una tabla con definiciones de las claves [SchemaKey](c-schemakey.md) del nodo actual.

```text
keys
```

## Observaciones

Ejemplo:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
  logInfo("Key: " + key.name + "\t is-internal: " + key.isInternal)
    
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
