---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 21%
---
# método

El método HTTP, en forma de cadena de caracteres

```text
method
```

## Observaciones

El valor de esta propiedad se cambia sistemáticamente a mayúsculas. Ejemplo:

```javascript
var http = new HttpClientRequest(url)
http.method = "SEARCH"
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
