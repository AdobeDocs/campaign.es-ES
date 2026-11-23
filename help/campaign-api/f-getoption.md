---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 13%
---
# getOption

Devuelve el valor de una opción de la tabla de opciones.

```text
getOption (name [, useCache ])
```

## Parámetros

**nombre** Nombre de la opción.

**useCache** Use la memoria caché de valores de opciones (de forma predeterminada, no se usa).

## Valor devuelto

El valor de la opción si existe; en caso contrario, es undefined. El tipo del valor depende del tipo de la opción.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
