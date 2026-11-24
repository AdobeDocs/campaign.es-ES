---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 11%
---
# iniciar

Inicia una consulta en modo asincrónico.

```text
start (context, name, ...)
```

## Parámetros

**context** Cualquier parámetro de usuario que se reenviará a la función [complete](p-soapservice-complete.md).

**name** Nombre del método al que se va a llamar.

**...** Parámetros de función.

## Valor devuelto

La consulta creada. Este objeto no tiene propiedades ni funciones; resulta útil para la función [wait](m-soapservice-wait.md) que le permite esperar hasta el final de una operación.

## Observaciones

La conexión del servicio debe ser asincrónica. Si la conexión se está bloqueando, se genera una excepción. No se pueden ejecutar consultas si se está ejecutando otra consulta en la conexión. En este caso, se genera una excepción.

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
