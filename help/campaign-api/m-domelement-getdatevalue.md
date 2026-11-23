---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 14%
---
# getDateValue

Devuelve el valor de tipo fecha+hora de la referencia de nodo por el XPath dado.

```text
getDateValue (xpath)
```

## Parámetros

Ruta de acceso **xpath**.

## Valor devuelto

Un objeto de tipo Fecha que coincide con el valor del nodo al que se hace referencia.

## Observaciones

La sintaxis de XPath solo acepta un subconjunto de lenguaje XPath. Se genera una excepción si la ruta está mal formada o si el valor no es una fecha válida.

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
