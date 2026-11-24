---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# adelante

Redirige la consulta a otra página sin pasar por el cliente.

```text
forward (location)
```

## Parámetros

**ubicación** La dirección URL de redirección.

## Valor devuelto

Ninguna.

## Observaciones

reenviar permite realizar un proceso preliminar antes de transferir la consulta a otro recurso, que genera el contenido de la respuesta. No se debe haber devuelto ningún dato al cliente como respuesta antes de una llamada de reenvío; de lo contrario, se generará un error.

## Funciones

**Método de clase:** [HttpServletRequest](c-httpservletrequest.md)

**Disponible en:**

* JSSP
* WebApp
