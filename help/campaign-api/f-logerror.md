---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# logError

Agrega un mensaje de error al registro de la instancia de flujo de trabajo y suspende la ejecución del script.

```text
logError (message)
```

## Parámetros

**message** Mensaje que se agregará al registro.

## Valor devuelto

Ninguna.

## Observaciones

La tarea en curso se comporta como si se hubiera producido un error: se marca un error y el flujo de trabajo se suspende. Por lo tanto, esta función es útil para provocar explícitamente un error en un flujo de trabajo y suspenderlo.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Envío del mensaje
* Regla de tipología
* Importación
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
