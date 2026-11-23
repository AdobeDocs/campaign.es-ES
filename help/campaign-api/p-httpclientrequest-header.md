---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 14%
---
# encabezado

Un objeto JavaScript que contiene los encabezados HTTP del encabezado.

```text
header
```

## Observaciones

Todas las propiedades del objeto header son accesibles en modo de lectura y escritura y se pueden enumerar. Cada propietario del objeto header es una entrada del encabezado HTTP de la consulta. Los nombres de propiedad no distinguen entre mayúsculas y minúsculas (como en los encabezados HTTP). Ejemplo:

```javascript
var http = new HttpClientRequest(url)

var buffer = new MemoryBuffer()
buffer.fromString(userName + ':' + password, "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"
http.header["Date"] = (new Date()).toGMTString()
//Note: http.header.Date == http.header.date

for( var i in http.header )
logInfo("header[" + i + "] => " + http.header[i])
```

## Funciones

**Propiedad de la clase:** [HttpClientRequest](c-httpclientrequest.md)

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
