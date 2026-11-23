---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 11%
---
# espera

Espera el final de una lista de consultas asincrónicas de SOAP.

```text
wait (requests)
```

## Parámetros

**solicitudes** Una tabla de consultas.

## Valor devuelto

Ninguna.

## Observaciones

La función no se aplica a un servicio, pero es una función del grupo SoapService. Ejemplo:

```javascript
...
var req = service.start(1234, "GetOption", sessionToken, "XtkDatabaseId")

// Do some stuff here

// Wait until the end of the request
SoapService.wait( [req] )
```

Una vez finalizada una consulta, esta se elimina automáticamente de la lista. Esto significa que cuando la función devuelve el control, la tabla pasada como parámetro estará vacía. La función [complete](p-soapservice-complete.md) puede modificar la lista: por ejemplo, es posible iniciar una nueva consulta y agregarla a la lista.

## Funciones

**Método de clase:** [SoapService](c-soapservice.md)

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
