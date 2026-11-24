---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# getElementsByTagNameNS

Devuelve la lista de todos los elementos secundarios con el nombre especificado.

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## Parámetros

**namespaceURI**: URI del área de nombres de los elementos buscados.

**localName** Nombre de los elementos buscados.

## Valor devuelto

Tabla que contiene la lista de elementos.

## Observaciones

Este método crea una nueva tabla para cada llamada a. Por lo tanto, es mejor mantener la tabla en una variable local en lugar de realizar varias llamadas.

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
