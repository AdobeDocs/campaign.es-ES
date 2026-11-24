---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 12%
---
# conexión

Cambia el contexto de ejecución del script al inicio de sesión actual.

```text
logon (sessionToken)
```

```text
logon (login, password)
```

```text
logon (context)
```

## Parámetros

**sessionToken**: El token de sesión que se va a usar.

**inicio de sesión**: se usará el inicio de sesión del operador.

**contraseña** La contraseña del operador. La contraseña puede ser una cadena vacía si el inicio de sesión actual tiene derechos de administrador.

**contexto** Objeto que representa un inicio de sesión, devuelto por una llamada anterior al inicio de sesión.

## Valor devuelto

Devuelve un objeto que coincide con el inicio de sesión anterior. Esto permite restaurar el inicio de sesión anterior pasando este parámetro a la función de inicio de sesión.

## Observaciones

Ejemplo:

```javascript
var oldContext = logon("jdoe", "")

// ...

logon(oldContext)
```

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
