---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 13%
---
# galletas

Devuelve las cookies de la consulta.

```text
cookies
```

## Observaciones

La propiedad cookies devuelve un objeto, con una cookie coincidente para cada una de sus propiedades. Ejemplo:

```javascript
var cookies = request.cookies
for(var name in cookies)
{
var value = cookies[name].value
document.write(name + " : " + value + "<br>")
}
```

## Funciones

**Propiedad de la clase:** [HttpServletRequest](c-httpservletrequest.md)

**Sólo lectura:**

Sí

**Disponible en:**

* JSSP
* WebApp
