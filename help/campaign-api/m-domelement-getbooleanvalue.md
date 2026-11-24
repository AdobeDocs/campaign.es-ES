---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 12%
---
# getBooleanValue

Devuelve el valor del nodo booleano al que hace referencia el XPath dado.

```text
getBooleanValue (xpath)
```

## Parámetros

Ruta de acceso **xpath**.

## Valor devuelto

true si el valor de texto del nodo al que se hace referencia es &quot;true&quot; o &quot;1&quot;, false es &quot;false&quot; o &quot;0&quot;.

## Observaciones

La sintaxis de XPath solo acepta un subconjunto de lenguaje XPath. La prueba de valor no distingue entre mayúsculas y minúsculas. Se genera una excepción si la ruta está mal formada o si el valor no es un booleano válido.

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
