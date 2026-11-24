---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 9%
---
# CurrentOperator (Clase)

Objeto que contiene información sobre el operador actual (nombre, identificadores, derechos, etc.).

Esta clase tiene una sola instancia que proporciona acceso a determinadas propiedades del servidor aplicativo. Se puede acceder a este singleton a través de la propiedad de la variable global `application`.

Ejemplo:

```text
var operator = application.operator logInfo("login: " + operator.login) logInfo("id: " + operator.id) logInfo("description: " + operator.computeString) logInfo("=== Groups ===") for each(var id in operator.groups) logInfo(id) logInfo("=== Rights ===") for each(var right in operator.rights) logInfo(right)
```

## Métodos

| Método | Descripción |
| --- | --- |
| [hasRight](m-currentoperator-hasright.md) | Comprueba si el operador tiene un derecho con nombre específico. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [iniciar sesión](p-currentoperator-login.md) | Devuelve el inicio de sesión del operador actual. |
| [id](p-currentoperator-id.md) | Devuelve el identificador interno del operador actual. |
| [computeString](p-currentoperator-computestring.md) | Devuelve la cadena de descripción del operador actual. De forma predeterminada, es el nombre del operador seguido de su nombre de inicio de sesión. |
| [grupos](p-currentoperator-groups.md) | Devuelve la lista de identificadores en los grupos de operadores actuales. |
| [derechos](p-currentoperator-rights.md) | Devuelve la lista de derechos del operador actual. |
| [zona horaria](p-currentoperator-timezone.md) | Devuelve el nombre de la zona horaria utilizada por el operador actual. |
| [hogar](p-currentoperator-home.md) | Devuelve el nombre de la carpeta raíz del operador actual. |

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
