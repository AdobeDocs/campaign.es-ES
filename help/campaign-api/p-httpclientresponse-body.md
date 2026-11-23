---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 12%
---
# cuerpo

Cuerpo de la respuesta HTTP en forma de objeto MemoryBuffer.

```text
body
```

## Observaciones

Se puede acceder a la codificación del cuerpo de respuesta a través de la propiedad [codePage](p-httpclientresponse-codepage.md). El cuerpo de la respuesta HTTP se proporciona en forma de objeto [MemoryBuffer](c-memorybuffer.md). Por lo tanto, todos los métodos aplicables a [MemoryBuffer](c-memorybuffer.md) son aplicables al cuerpo de la respuesta HTTP. Ejemplo:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
if( response.code != 200 )
  throw "HTTP request failed with " + response.message
var content = response.body.toString(response.codePage)
```

## Funciones

**Propiedad de la clase:** [HttpClientResponse](c-httpclientresponse.md)

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
