---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 19%
---
# encabezado

Un objeto que contiene todos los encabezados HTTP.

```text
header
```

## Observaciones

El nombre de las propiedades no distingue entre mayúsculas y minúsculas. Ejemplo:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
for(var i in response.header)
  logInfo("header[" + i + "] => " + response.header[i])
    
```

Para recuperar varios encabezados con el mismo nombre, use la propiedad [headers](p-httpclientresponse-headers.md) en lugar de la propiedad header.

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
