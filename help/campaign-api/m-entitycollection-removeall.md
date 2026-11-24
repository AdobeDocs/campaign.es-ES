---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 31%
---
# removeAll

Elimina todas las entidades de la colección.

```text
removeAll ()
```

## Parámetros

Ninguna.

## Valor devuelto

Ninguna.

## Observaciones

Ejemplo:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.removeAll()
delivery.save()
```

## Funciones

**Método de clase:** [EntityCollection](c-entitycollection.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
