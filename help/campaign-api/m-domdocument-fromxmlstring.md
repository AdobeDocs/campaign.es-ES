---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 20%
---
# fromXMLString

Crea un nuevo documento a partir de una cadena de caracteres XML.

```text
fromXMLString (string)
```

## Parámetros

**cadena** Cadena de caracteres XML.

## Valor devuelto

Ninguna.

## Observaciones

Se genera una excepción si el argumento no es un documento XML válido. Esta función se aplica a la clase DOMDocument. Ejemplo:

```javascript
var doc = DOMDocument.fromXMLString(
    '<?xml version="1.0" encoding="ISO-8859-1"?>' +
    '<form name="address" namespace="nms" colcount="2"/>')
```

## Funciones

**Método de clase:** [DOMDocument](c-domdocument.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Envío del mensaje
* Regla de tipología
* Importación
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
