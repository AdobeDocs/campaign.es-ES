---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 12%
---
# isEqualNode

Compara dos nodos.

```text
isEqualNode (arg)
```

## Parámetros

**arg**: el segundo nodo.

## Valor devuelto

true si los dos nodos son iguales; en caso contrario, false.

## Observaciones

Dos nodos son iguales si se verifican las siguientes condiciones:

* Los dos nodos son del tipo.
* Las propiedades nodeName, localName, namespaceURI, prefix y nodeValue deben ser idénticas.
* Los dos nodos son del tipo.
* Los atributos deben ser iguales.
* Los nodos deben ser iguales.

Como la normalización puede afectar a la igualdad, le recomendamos que normalice antes de comparar.

## Funciones

**Método de clase:** [DOMNode](c-domnode.md)

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
