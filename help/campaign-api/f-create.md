---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 11%
---
# crear

Crea una nueva entidad correspondiente a un esquema determinado.

```text
create ( [content ])
```

## Parámetros

**content** Una cadena de caracteres opcional correspondiente al XML de la entidad que se va a crear.

## Valor devuelto

Devuelve la entidad en forma de objeto JavaScript.

## Observaciones

create no es una función global, sino un método de esquema. Para invocarlo, debe añadirlo como prefijo al esquema deseado. Por ejemplo:

```javascript
var recipient = NLWS.nmsRecipient.create(
      {recipient: {
        email: "support@adobe.com", 
        lastName: "Adobe", 
        firstName: "Support"}})
recipient.save()
```

El documento no se guarda automáticamente en la base de datos. Debe usar el método ⌐⌐[save()](m-entity-save.md) en la entidad.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
