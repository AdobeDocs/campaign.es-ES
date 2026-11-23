---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 9%
---
# complete

Función a la que se llama cuando finaliza una consulta asincrónica.

```text
complete
```

## Observaciones

La función debe aceptar tres argumentos:

* La consulta
* El contexto
* El estado: &quot;success&quot;, &quot;error&quot; o &quot;timeout&quot;

El estado &quot;correcto&quot; significa que se ha recibido una respuesta, pero la respuesta puede tener cualquier código (200, 404, 503, etc.). El estado &quot;error&quot; puede indicar una interrupción de la comunicación de una respuesta mal estructurada. El estado &quot;tiempo de espera&quot; significa que no se pudo establecer la conexión o que no se recibió respuesta alguna dentro del plazo configurado. Ejemplo:

```javascript
http.complete = function(req, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + req.response.code)
}
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
