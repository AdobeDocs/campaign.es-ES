---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%
---
# findNode

Devuelve una instancia de [SchemaNode](c-schemanode.md) o null si el nodo no existe y el parámetro mustExist está establecido en false.

```text
findNode (name [, strict ] [, mustExist ])
```

## Parámetros

**name** XPath representa el nombre del nodo que se va a buscar

**strict** Valor booleano que indica si (estricto a false) o no, cuando el nombre del último elemento de la ruta no existe tal cual, se debe buscar como atributo o elemento. De forma predeterminada, true.

**mustExist** Valor booleano que indica si se debe provocar una excepción si el nodo no existe. true de forma predeterminada.

## Valor devuelto

Devuelve una instancia de [SchemaNode](c-schemanode.md) si se encuentra el nodo, o bien un valor null si el parámetro mustExist está establecido en false.

## Observaciones

Ejemplo:

```javascript
var schema = application.getSchema("nms:recipient");

logInfo("netSales: " + schema.root.findNode("@netSales"));
logInfo("merchandise/@lastPurchaseDate: " + schema.root.findNode("merchandise/@lastPurchaseDate", true, false));
```

Resultado:

```javascript
netSales: [object NodeDef]
merchandise/@lastPurchaseDate: [object NodeDef]
```

## Funciones

**Método de clase:** [NodoEsquema](c-schemanode.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
