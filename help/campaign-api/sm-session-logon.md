---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%
---
# Iniciar sesión

Abre una sesión

```text
[ String sessionToken, sessionInfo sessionInfo, String securityToken ] = Logon ( String login, String password, XML parameters )
```

## Parámetros

Cuenta de usuario **login**

**contraseña** Contraseña asociada al inicio de sesión del usuario

**parámetros** Configuración de conexión

## Valor(es) devuelto(s)

**sessionToken** token de sesión

**sessionInfo** parámetros de sesión

**securityToken** token de seguridad

## Configuración del mecanismo de bloqueo de cuenta

Hay disponible un mecanismo de bloqueo de cuenta en la API Logon(). Evita cualquier otro intento de inicio de sesión después de un cierto número de intentos consecutivos de inicio de sesión fallidos dentro de un lapso de tiempo especificado.

Hay cuatro opciones disponibles para configurar el mecanismo de bloqueo:

* **XtkSecurity\_max\_Unsuccessul\_Attempts\_Allowed**: máximo intento incorrecto de bloquear una clave dentro de la duración especificada. El valor predeterminado es 3.
* **XtkSecurity\_Initial\_Ban\_Duration**: duración durante la cual se prohibirá la clave por primera vez. La duración predeterminada es de 5 minutos.
* **XtkSecurity\_Max\_Ban\_Duration**: duración máxima durante la cual se puede prohibir una clave.
* **XtkSecurity\_Examine\_Window**: Ventana de tiempo para rastrear el número de intentos de inicio de sesión erróneos para prohibir una clave no válida. La duración predeterminada es de 10 minutos.

Por ejemplo, si alguien intenta 3 intentos fallidos en 10 minutos, su clave se bloquea durante 5 minutos.

## Funciones

**Esquema:** [xtk:session](s-xtk-session.md)

**Estático:**

Sí
