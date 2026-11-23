---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 16%
---
# getNumberValue

Devuelve el valor del nodo digital al que hace referencia el XPath dado.

```text
getNumberValue (xpath)
```

## Parámetros

Ruta de acceso **xpath**.

## Valor devuelto

El valor digital corresponde al nodo al que se hace referencia.

## Observaciones

La sintaxis de XPath solo acepta un subconjunto de lenguaje XPath. Se genera una excepción si la ruta de acceso está mal formada o si el valor no es un número válido.

## Funciones

**Método de clase:** [DOMElement](c-domelement.md)

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
