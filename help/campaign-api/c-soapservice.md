---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%
---
# SoapService (Clase)

Permite realizar llamadas de SOAP en un servicio web.

## Bloqueo de llamadas

El siguiente es un ejemplo típico de uso: primero debe crear una conexión y luego un servicio que utilice esta conexión y, finalmente, declarar los métodos SOAP para este servicio. El método SOAP se expone en forma de método JavaScript del objeto de servicio.

```text
var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0) var session = new SoapService(cnx, "xtk:session") session.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) var result = session.GetOption("admin/", "NmsBroadcast_DefaultProvider") var value = result[0] var type = result[1] logInfo("Value = " + value) logInfo("Type = " + type)
```

## Llamadas sin bloqueo

Es posible realizar llamadas no bloqueantes (asincrónicas), es decir, ejecutar una consulta de SOAP en un servidor y continuar ejecutando el script sin esperar el resultado. Las principales diferencias con el modo de bloqueo son las siguientes:

* La conexión debe crearse en modo asincrónico

* Utilice los botones

  [iniciar](m-soapservice-start.md)

  función.

* Defina un

  [complete](p-soapservice-complete.md)

  función en el servicio, a la que se llamará cuando se reciba la respuesta.

* La

  [SoapService.wait](m-soapservice-wait.md)

  se utiliza para esperar al final del procesamiento de un conjunto de consultas.

El siguiente script de ejemplo realiza una serie de llamadas de SOAP &quot;GetOption&quot; a un servidor de Adobe Campaign abriendo 3 conexiones simultáneamente.

```text
var list = [ "XtkDatabaseId", "XtkKey", "WdbcTimeZone", "NmsServer_URL", "NmsBroadcast_DefaultProvider"] var requests = [] function complete(service, result, context, status) { if( status == "success" ) logInfo("option " + context + ": value = " + result[0]) else if( status == "fault" ) logInfo("option " + context + ": fault = " + result.message) else logInfo("option " + context + ": " + status) sendNext(service) } function createService() { // Create the connection var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0, true) // Create the service var service = new SoapService(cnx, "xtk:session") service.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) // Change the timeout to 5 seconds service.timeout = 5000 // Setup the callback function service.complete = complete return service } function sendNext(service) { if( list.length == 0) return // Pick an item from the list var name = list.shift() // Use the name as context var context = name // Send the request var req = service.start(context, "GetOption", "admin/", name) // Add the request to the wait queue requests.push(req) } // Open 3 connections and start a request on each one sendNext(createService()) sendNext(createService()) sendNext(createService()) SoapService.wait(requests) logInfo("Done.")
```

## Métodos

| Método | Descripción |
| --- | --- |
| [ServicioSoap](m-soapservice-soapservice.md) | Crea un servicio para llamar a las funciones de un servicio Web. |
| [addMethod](m-soapservice-addmethod.md) | Declara una función en el servicio. |
| [eliminar](m-soapservice-dispose.md) | Libera los recursos utilizados por el objeto. |
| [iniciar](m-soapservice-start.md) | Inicia una consulta en modo asincrónico. |
| [espera](m-soapservice-wait.md) | Espera el final de una lista de consultas asincrónicas de SOAP. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [completado](p-soapservice-complete.md) | Función a la que se llama cuando finaliza una consulta asincrónica. |
| [encabezado](p-soapservice-header.md) | Una cadena de caracteres copiada literalmente en el encabezado de SOAP. |
| [tiempo de espera](p-soapservice-timeout.md) | Tiempo de espera máximo en milisegundos en caso de una consulta asincrónica. Si no se define este parámetro, el tiempo de espera es de 5 minutos. |

## Funciones

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
