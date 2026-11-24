---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 33%
---
# DOMocument

Crea un nuevo documento.

```text
DOMDocument (name [, namespaceURI ])
```

## Parámetros

**nombre** Nombre de documento.

**namespaceURI** URI de área de nombres de documento.

## Valor devuelto

Ninguna.

## Observaciones

Ejemplo:

```javascript
var doc = new DOMDocument("test")
var doc2 = new DOMDocument("html", "http://www.w3.org/1999/xhtml")
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
