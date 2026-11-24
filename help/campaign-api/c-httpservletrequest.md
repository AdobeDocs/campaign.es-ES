---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%
---
# HttpServletRequest (clase)

Representa la consulta de un cliente reenviado a un servlet.

Solo hay una instancia de esta dirección accesible a través de `request`. variable.

## Métodos

| Método | Descripción |
| --- | --- |
| [getHeader](m-httpservletrequest-getheader.md) | Devuelve un atributo definido en el encabezado de la consulta. |
| [getParameter](m-httpservletrequest-getparameter.md) | Devuelve el valor de un parámetro de consulta. |
| [getRemoteAddress](m-httpservletrequest-getremoteaddr.md) | Devuelve la dirección IP del cliente o el último proxy que envió una solicitud. |
| [getUTF8Parameter](m-httpservletrequest-getutf8parameter.md) | Devuelve el valor (codificado en UTF-8) de un parámetro de la consulta. |
| [getBodyAsString](m-httpservletrequest-getbodyasstring.md) | Devuelve el cuerpo de la consulta en forma de cadena de caracteres mediante la codificación de la consulta. |
| [avanzar](m-httpservletrequest-forward.md) | Redirige la consulta a otra página sin pasar por el cliente. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [parámetros](p-httpservletrequest-parameters.md) | Devuelve los parámetros de consulta. |
| [cookies](p-httpservletrequest-cookies.md) | Devuelve las cookies de la consulta. |
| [requestURI](p-httpservletrequest-requesturi.md) | Devuelve la dirección URL de la consulta. |
| [queryString](p-httpservletrequest-querystring.md) | Devuelve la parte de la dirección URL de la consulta que coincide con los parámetros. |
| [esquema](p-httpservletrequest-scheme.md) | Devuelve el nombre del protocolo utilizado (HTTP, HTTPS, etc.) para acceder a esta página. |
| [nombreDeServidor](p-httpservletrequest-servername.md) | Devuelve el nombre del servidor de consultas. |
| [puertoServidor](p-httpservletrequest-serverport.md) | Devuelve el número de puerto utilizado para ponerse en contacto con el servidor. |
| [serverURL](p-httpservletrequest-serverurl.md) | Devuelve la dirección URL para obtener acceso al servidor. |
| [rutaDeAccesoDeServlet](p-httpservletrequest-servletpath.md) | Devuelve la sección de la URL de la consulta que coincide con el servlet. |
| [contextPath](p-httpservletrequest-contextpath.md) | Devuelve la sección de la dirección URL de la consulta que coincide con el contexto. |
| [pathInfo](p-httpservletrequest-pathinfo.md) | Devuelve la información adicional de la dirección URL de la consulta. |
| [método](p-httpservletrequest-method.md) | Devuelve una cadena de caracteres que contiene el método HTTP utilizado para llamar a esta consulta (GET, HEAD, POST, etc.). |

## Funciones

**Disponible en:**

* JSSP
* WebApp
