---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '30'
ht-degree: 16%
---
# getHeader

Devuelve un atributo definido en el encabezado de la consulta.

```text
getHeader (name)
```

## Parámetros

**nombre** Nombre del atributo del encabezado.

## Valor devuelto

Ninguna.

## Observaciones

Ejemplo:

```javascript
Host: <%= request.getHeader("host") %>
```

## Funciones

**Método de clase:** [HttpServletRequest](c-httpservletrequest.md)

**Disponible en:**

* JSSP
* WebApp
