---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 8%
---
# cargar

> Advertencia:
>
> El acceso a través de las API de archivo está limitado a **var**, **sftp** y a las carpetas temporales de Adobe Campaign.

Carga y devuelve una entidad correspondiente a un esquema y una clave determinados.

```text
load (key)
```

## Parámetros

**key** Una cadena de caracteres que corresponde a la clave de la entidad.

## Valor devuelto

Devuelve la entidad en forma de objeto JavaScript.

## Observaciones

la carga no es una función global sino un método de esquema. Para invocarlo, debe añadirlo como prefijo al esquema deseado. Por ejemplo:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

Las propiedades y subpropiedades de este objeto se pueden modificar a voluntad. A diferencia del método [get()](f-get.md), el documento no se guarda automáticamente en la base de datos; debe invocar el método [save()](m-entity-save.md) en el objeto. Si la entidad no se encuentra en la base de datos, se trata de un error y la secuencia de comandos se interrumpe.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
