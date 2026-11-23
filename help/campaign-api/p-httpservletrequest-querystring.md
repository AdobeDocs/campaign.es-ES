---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 11%
---
# queryString

Devuelve la parte de la dirección URL de la consulta que coincide con los parámetros.

```text
queryString
```

## Observaciones

Ejemplo: queryString de la siguiente dirección URL:

```javascript
      http://adobe.com/nms/test.jst?id=1234&param=dummy#aFragment
```

devuelve la siguiente cadena:

```javascript
id=1234&param=dummy
```

## Funciones

**Propiedad de la clase:** [HttpServletRequest](c-httpservletrequest.md)

**Sólo lectura:**

Sí

**Disponible en:**

* JSSP
* WebApp
