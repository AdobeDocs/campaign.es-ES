---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%
---
# cuerpo

Cuerpo de la consulta HTTP.

```text
body
```

## Observaciones

El objeto asignado al cuerpo de la consulta se procesa de la siguiente manera:

* undefined, null, function: no se consideran elementos enviables, el cuerpo de la consulta HTTP está vacío.
* number, boolean, string, XML, Object: se ha cambiado a una cadena de caracteres basada en el método toString y codificada en función del encabezado HTTP Content-type.
* [MemoryBuffer](c-memorybuffer.md): el contenido se copia en el cuerpo de la consulta sin alteración.

Ejemplo:

```javascript
var query = "Select \"urn:schemas:calendar:uid\" " // etc...
var apptRequest =
  "<g:searchrequest xmlns:g="DAV:">\n" +
  "  <g:sql>\n" +
        query +
  "  </g:sql>\n" +
  "</g:searchrequest>"
http.body = apptRequest
    
```

## Funciones

**Propiedad de la clase:** [HttpClientRequest](c-httpclientrequest.md)

**Sólo lectura:**

No

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
