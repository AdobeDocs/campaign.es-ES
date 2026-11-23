---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 25%
---
# importNode

Crea una copia de nodo desde otro documento.

```text
importNode (importedNode, deep)
```

## Parámetros

Nodo Source **importedNode**.

**deep** true si se debe copiar el nodo completo; en caso contrario, false.

## Valor devuelto

Copia del nodo.

## Observaciones

Ejemplo:

```javascript
var result = doc.importNode(rcpResult, true);
doc.root.appendChild(result);
```

## Funciones

**Método de clase:** [DOMDocument](c-domdocument.md)

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
