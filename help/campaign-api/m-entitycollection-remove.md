---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 23%
---
# quitar

Elimina una entidad de la colección.

```text
remove (index|object)
```

## Parámetros

**index\|object**: índice de la entidad que se va a eliminar o de la propia entidad.

## Valor devuelto

Ninguna.

## Observaciones

Ejemplos:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.remove(1)
delivery.save()
```

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
var attach = delivery.attachment[1]
delivery.attachment.remove(attach)
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
