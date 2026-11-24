---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 14%
---
# fromJXON

Crea un nuevo documento a partir de un objeto JSON.

```text
fromJXON (obj)
```

## Parámetros

**obj** Un objeto JSON que representa el documento XML que se va a crear.

## Valor devuelto

Ninguna.

## Observaciones

Las funciones que pasan un DOMDocument o DOMElement como parámetros también aceptan directamente un objeto JSON. No es necesario crear un objeto intermedio mediante esta función. Se genera una excepción si el objeto no es un objeto JSON válido. Esta función se aplica a la clase DOMDocument. Ejemplo:

```javascript
var doc = DOMDocument.fromJXON(
    {form : {name: "address", "namespace": "nms", colcount: 2}})
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
