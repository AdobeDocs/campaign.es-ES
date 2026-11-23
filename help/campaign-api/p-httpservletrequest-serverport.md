---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%
---
# serverPort

Devuelve el número de puerto utilizado para ponerse en contacto con el servidor.

```text
serverPort
```

## Observaciones

Ejemplo: ServerPort de la siguiente URL:

```javascript
http://adobe.com/es:8080/nms/test.jst
```

devuelve la siguiente cadena:

```javascript
8080
```

El serverPort de la siguiente URL:

```javascript
http://adobe.com/nms/test.jst
```

devuelve la siguiente cadena:

```javascript
80
```

## Funciones

**Propiedad de la clase:** [HttpServletRequest](c-httpservletrequest.md)

**Sólo lectura:**

Sí

**Disponible en:**

* JSSP
* WebApp
