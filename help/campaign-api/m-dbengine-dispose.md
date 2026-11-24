---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 14%
---
# disponer

Libera la conexión de todos los recursos vinculados a ella.

```text
dispose ()
```

## Parámetros

Ninguna.

## Valor devuelto

Ninguna.

## Observaciones

Una conexión creada con el método [application.getConnection()](m-application-getconnection.md) se libera automáticamente al final del script. Llamar a este método es útil para scripts que pueden tener una larga vida útil.

## Funciones

**Método de clase:** [DBEngine](c-dbengine.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
