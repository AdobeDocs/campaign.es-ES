---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 15%
---
# exec

Alias del comando execute. Esta función está obsoleta, use [execute()](m-dbengine-execute.md)

```text
exec (command [, value1, ... ])
```

## Parámetros

**comando** comando SQL.

**value1, ...** Variables del comando.

## Valor devuelto

El número de grabaciones actualizadas o insertadas si se aplica al comando ejecutado, si no es cero.

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
