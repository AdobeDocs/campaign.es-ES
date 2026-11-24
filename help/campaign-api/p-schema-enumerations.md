---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 27%
---
# enumeraciones

Devuelve la tabla que contiene la lista de [enumeraciones](c-enumeration.md) definidas en este esquema.

```text
enumerations
```

## Observaciones

Ejemplo:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var e in schema.enumerations)
{
  logInfo(e.name)
}
```

## Funciones

**Propiedad de la clase:** [Esquema](c-schema.md)

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
