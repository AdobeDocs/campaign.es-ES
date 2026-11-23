---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# conectar

Abre la conexión HTTP y pasa el objeto al modo &quot;keepalive&quot;

```text
connect ( [hasProxy ] [, async ])
```

## Parámetros

**hasProxy** de tipo booleano a verdadero si necesita usar un HTTP proxy. De forma predeterminada, se establece en false.

**async** Boolean establecido en true si la conexión está destinada a ejecutar una consulta asincrónica. De forma predeterminada, se establece en false.

## Valor devuelto

Ninguna.

## Observaciones

Si la conexión HTTP falla, se genera una excepción. La propiedad response solo se vuelve válida después de una llamada correcta a la función execute. No olvide llamar a desconectar() una vez que haya terminado de utilizar la conexión. Ejemplo:

```javascript
// Mistake with the hostname gogle instead of google
var badHttp = new HttpClientRequest("www.gogle.fr");
try {
  badHttp.connect();
} catch (e) {
  // Here an exception has been raised
}

var goodHttp = new HttpClientRequest("www.google.fr");
try {
  goodHttp.connect();
} catch (e) {
  // No exeception raised
}
...
goodHttp.disconnect();
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
