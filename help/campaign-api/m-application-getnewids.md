---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 12%
---
# getNewIds

Devuelve una lista de los ID de las claves internas de la base de datos.

```text
getNewIds (count [, sequence ])
```

## Parámetros

**count** número de identificadores que el método debe devolver.

**sequence** Nombre de la secuencia que se va a usar.

## Valor devuelto

Tabla que contiene la lista de ID:

## Observaciones

Este método es equivalente a los métodos SOAP NLWS.xtkSession.GetNewIds() y NLWS.xtkSession.GetNewIdsEx() a la vez que es más eficiente.

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
