---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 23%
---
# hasPackage

Comprueba si hay un paquete instalado.

```text
hasPackage (name)
```

## Parámetros

**nombre** Nombre completo del paquete.

## Valor devuelto

True si el paquete está instalado.

## Observaciones

Ejemplo:

```javascript
var hasMRM = application.hasPackage("nms:mrm")
```

## Funciones

**Método de clase:** [Aplicación](c-application.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
