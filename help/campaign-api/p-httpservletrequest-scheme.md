---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 10%
---
# confabulación

Devuelve el nombre del protocolo utilizado (HTTP, HTTPS, etc.) para acceder a esta página.

```text
scheme
```

## Observaciones

Ejemplo: El esquema de la siguiente URL:

```javascript
      http://adobe.com/es:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

devuelve la siguiente cadena:

```javascript
http
```

## Funciones

**Propiedad de la clase:** [HttpServletRequest](c-httpservletrequest.md)

**Sólo lectura:**

Sí

**Disponible en:**

* JSSP
* WebApp
