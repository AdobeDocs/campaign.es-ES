---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 31%
---
# guardar

Guarda una entidad en la base de datos.

```text
save ()
```

## Parámetros

Ninguna.

## Valor devuelto

Ninguna.

## Observaciones

Ejemplo:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.label = "Diffusion 12345"
delivery.save()
```

## Funciones

**Método de clase:** [Entidad](c-entity.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
