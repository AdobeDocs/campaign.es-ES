---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 16%
---
# getConnection

Devuelve una nueva conexión al servidor de base de datos.

```text
getConnection ()
```

## Parámetros

Ninguna.

## Valor devuelto

Una [conexión](c-dbengine.md) al servidor de base de datos.

## Observaciones

Es posible liberar la conexión antes del final de la ejecución del script usando el método [dispose](m-dbengine-dispose.md).

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
