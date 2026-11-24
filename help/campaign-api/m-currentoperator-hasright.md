---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 23%
---
# hasRight

Comprueba si el operador tiene un derecho con nombre específico.

```text
hasRight (name)
```

## Parámetros

**nombre** Nombre derecho.

## Valor devuelto

True si el operador tiene este derecho.

## Observaciones

Ejemplo:

```javascript
      var hasAdminRight = application.operator.hasRight("admin")
```

## Funciones

**Método de clase:** [CurrentOperator](c-currentoperator.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
