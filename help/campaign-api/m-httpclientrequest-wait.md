---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# espera

Espera hasta el final de una lista de consultas asincrónicas.

```text
wait (requests,waitAll)
```

## Parámetros

**solicitudes** Una tabla de consultas.

**waitAll** Boolean (de forma predeterminada true), esperar a que se completen todas las solicitudes de la lista de consultas. Cuando se establece en false, si se completa al menos una solicitud, la función sale del bucle de escucha.

## Valor devuelto

Ninguna.

## Observaciones

La función no se aplica a una consulta, pero es una función de la bandeja HttpClientRequest. Ejemplo:

```javascript
var req = new HttpClientRequest("http://www.adobe.com/")
req.complete = function(req, context, status) { logInfo(status) }
req.execute(false, true)

HttpClientRequest.wait( [req] )
```

Solo se puede agregar una consulta a la lista si es asincrónica y si la llamada [execute](m-httpclientrequest-execute.md) no ha producido una excepción. Una vez finalizada una consulta, esta se elimina automáticamente de la lista. Esto significa que cuando la función devuelve el control, la tabla pasada como parámetro estará vacía. La función [complete](p-httpclientrequest-complete.md) puede modificar la lista: por ejemplo, es posible iniciar una nueva consulta y agregarla a la lista.

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
