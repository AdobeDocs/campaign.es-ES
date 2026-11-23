---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 6%
---
# complete

Función a la que se llama cuando finaliza una consulta asincrónica.

```text
complete
```

## Observaciones

La función debe aceptar cuatro argumentos:

* El servicio
* El resultado
* El contexto: este es el parámetro pasado a la función [start](m-soapservice-start.md)
* El estado

El estado puede tener los siguientes valores:

* &quot;success&quot; significa que se ha recibido un resultado.
* &quot;error&quot; puede significar que la comunicación se interrumpió, que la respuesta estaba mal estructurada o que se produjo un error HTTP.
* &quot;error&quot; si se devuelve un error de SOAP. En este caso, el resultado contiene un objeto que describe el error.
* &quot;timeout&quot; significa que no se ha podido establecer la conexión o que no se ha recibido ninguna respuesta en el plazo configurado.

Cuando el resultado es &quot;success&quot;, el resultado depende del número de parámetros devueltos:

* void si la consulta no devuelve ningún valor
* El valor si la consulta devuelve un solo parámetro
* una tabla si la consulta devuelve varios parámetros

Cuando el estado es &quot;error&quot;, el resultado es un objeto que contiene las siguientes propiedades:

* message: el mensaje de descripción del error.
* object: un objeto XML que contiene los detalles del error.

Ejemplo:

```javascript
http.complete = function(result, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + result[0])
}
```

## Funciones

**Propiedad de clase:** [SoapService](c-soapservice.md)

**Sólo lectura:**

No

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
