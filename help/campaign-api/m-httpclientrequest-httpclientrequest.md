---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%
---
# HttpClientRequest

Crea un nuevo objeto para ejecutar una consulta de cliente HTTP.

```text
HttpClientRequest ( [URL ])
```

## Parámetros

**URL** URL del destinatario de la consulta.

## Valor devuelto

Ninguna.

## Observaciones

Si el comando FTP falla, se genera una excepción. Ejemplo:

```javascript
var http = new HttpClientRequest("http://www.somewhere.com/login")

var buffer = new MemoryBuffer()
buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"

http.method = "SEARCH"
http.body = "<xml>any content</xml>"

http.execute()
       
```

## Funciones

**Método de clase:** [HttpClientRequest](c-httpclientrequest.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
