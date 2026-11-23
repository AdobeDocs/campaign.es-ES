---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 7%
---
# get

Carga y devuelve una entidad correspondiente a un esquema y una clave determinados.

```text
get ( [key or content ])
```

## Parámetros

**clave o contenido** Una cadena de caracteres correspondiente a la clave de la entidad de contenido XML para crear o iniciar una nueva entidad.

## Valor devuelto

Devuelve la entidad en forma de objeto JavaScript.

## Observaciones

get no es una función global, sino un método de esquema. Para invocarlo, debe añadirlo como prefijo al esquema deseado. Por ejemplo:

```javascript
var delivery = NLWS.nmsDelivery.get("12435")
```

Las propiedades y subpropiedades de este objeto se pueden modificar a voluntad. El documento se guarda automáticamente en la base de datos cuando la secuencia de comandos termina de ejecutarse si se modifica. Si no es una creación y la entidad no está ya en la base de datos, se trata de un error y la secuencia de comandos se interrumpe.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
