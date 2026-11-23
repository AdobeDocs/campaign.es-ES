---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# encabezados

La lista de encabezados para la respuesta HTTP agrupada por nombre.

```text
headers
```

## Observaciones

Cada propiedad headers llevaba el nombre del encabezado y el valor de la tabla que coincide con cada encabezado con este nombre. Esta función es diferente de [header](p-httpclientresponse-header.md) porque devuelve una tabla de valores en lugar de un valor único para un nombre determinado. Esto resulta útil para encabezados que pueden aparecer varias veces, como Accept-Language o Set-Cookie. La función devuelve una tabla vacía si la respuesta HTTP no tiene un encabezado con este nombre. Ejemplo:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = response
var cookies = response.headers["set-cookie"]
for each(var c in cookies)
{
  logInfo("Set-Cookie: " + c)
}
```

las propiedades de los encabezados no se pueden desglosar. Los nombres de propiedad no distinguen entre mayúsculas y minúsculas.

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
