---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 14%
---
# EntityCollection (Clase)

Representa una colección de una entidad.

No se puede crear una instancia de este objeto directamente. Se deben utilizar los métodos create(), get() o load().

Los elementos de una colección se pueden enumerar con `for` o `for each`. Este ejemplo muestra una enumeración de archivos vinculados a una acción de envío.

```text
var delivery = NLWS.nmsDelivery.load("12345") for each(var attach in delivery.attachment) logInfo(attach.label)
```

## Métodos

| Método | Descripción |
| --- | --- |
| [agregar](m-entitycollection-add.md) | Agrega una nueva entidad a la colección. |
| [quitar](m-entitycollection-remove.md) | Elimina una entidad de la colección. |
| [quitar todo](m-entitycollection-removeall.md) | Elimina todas las entidades de la colección. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [length](p-entitycollection-length.md) | Devuelve el número de entidad de la colección. |

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
