---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 12%
---
# serverName

Devuelve el nombre del servidor de consultas.

```text
serverName
```

## Observaciones

Ejemplo: ServerName de la siguiente URL:

```javascript
      http://adobe.com:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

devuelve la siguiente cadena:

```javascript
adobe.com
```

## Funciones

**Propiedad de la clase:** [HttpServletRequest](c-httpservletrequest.md)

**Sólo lectura:**

Sí

**Disponible en:**

* JSSP
* WebApp
