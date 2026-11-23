---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 4%
---
# HttpClientRequest, clase

Un objeto HttpClientRequest permite realizar determinadas operaciones como cliente HTTP.

Ejemplo :

```text
var req = new HttpClientRequest("http://www.somewhere.com/login") var buffer = new MemoryBuffer() buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1") req.header["Authorization"] = "Basic " + buffer.toBase64() req.header["Content-Type"] = "text/xml; charset=utf-8" req.method = "SEARCH" req.body = "<xml>any content</xml>" req.execute()
```

## &quot;Keep Alive&quot;

El objeto se puede utilizar en dos modos diferentes: estándar o mantener activo. El modo Estándar permite enviar una sola consulta, el modo Mantener activa permite enviar varias consultas mientras mantiene la conexión abierta. El estado del objeto depende de la secuencia de uso del método. Si se llama al método connect(), el objeto cambia al modo &quot;keep alive&quot;. Ejemplo

```text
var req = new HttpClientRequest("http://evc-cit.info/cgi-bin/cit042/timeofday.cgi") req.connect() // Now the object is in keep-alive mode, we can sand many requests using // the same connection // Request ten times the time of the cgi var i = 0 while ( i < 10 ) { req.execute() var response = req.reponse i++ } req.disconnect()
```

## Consultas asincrónicas

Las consultas se ejecutan en modo de bloqueo de forma predeterminada, lo que significa que la variable

[ejecutar](m-httpclientrequest-execute.md)

La función solo devuelve el control una vez que se envía la consulta y se recibe la respuesta. También es posible ejecutar consultas en modo asincrónico. En este caso, la variable

[ejecutar](m-httpclientrequest-execute.md)

La función devuelve el control inmediatamente y se llama a una función una vez recibida la respuesta. Esto permite la ejecución simultánea de varias consultas. El siguiente programa es un ejemplo completo que muestra cómo ejecutar una serie de cargas HTTP abriendo 3 conexiones al mismo tiempo, donde cada carga se inicia una vez que ha finalizado la última.

```text
var list = [ "http://www.adobe.com/", "http://www.google.com/", "http://www.mozilla.org/", "http://www.linux.org/", "http://www.postgresql.org/"] var requests = [] var complete = function(req, context, status) { if( status == "success" ) logInfo("Receiving " + context + ": " + req.url + ": code = " + req.response.code) else logWarning("Error " + context + ": " + req.url + ": " + status) sendNext(context) } function sendNext(context) { // Repeat until the first execute() passes while( list.length != 0 ) { // Pick one URL from the list var url = list.shift() var req = new HttpClientRequest(url) req.complete = complete try { req.execute(false, true, context, 5000) logInfo("Sending " + url) requests.push(req) return } catch(e) { // Log a message and pick up next item from list logWarning("Failed to send " + url) } } } // Start 3 requests sendNext(1) sendNext(2) sendNext(3) // Wait until all requests are completed HttpClientRequest.wait(requests) logInfo("Finished.")
```

## Métodos

| Método | Descripción |
| --- | --- |
| [HttpClientRequest](m-httpclientrequest-httpclientrequest.md) | Crea un nuevo objeto para ejecutar una consulta de cliente HTTP. |
| [conectar](m-httpclientrequest-connect.md) | Abre la conexión HTTP y pasa el objeto al modo &quot;keepalive&quot; |
| [desconectar](m-httpclientrequest-disconnect.md) | Cierra la conexión HTTP de un objeto en modo &quot;keepalive&quot;. |
| [ejecutar](m-httpclientrequest-execute.md) | Ejecuta la consulta HTTP. |
| [espera](m-httpclientrequest-wait.md) | Espera hasta el final de una lista de consultas asincrónicas. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [cuerpo](p-httpclientrequest-body.md) | Cuerpo de la consulta HTTP. |
| [completado](p-httpclientrequest-complete.md) | Función a la que se llama cuando finaliza una consulta asincrónica. |
| [encabezado](p-httpclientrequest-header.md) | Un objeto JavaScript que contiene los encabezados HTTP del encabezado. |
| [método](p-httpclientrequest-method.md) | El método HTTP, en forma de cadena de caracteres |
| [respuesta](p-httpclientrequest-response.md) | La respuesta de la consulta HTTP. Objeto de tipo HttpClientResponse |
| [url](p-httpclientrequest-url.md) | La dirección del servidor remoto. |

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
