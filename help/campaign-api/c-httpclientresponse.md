---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 9%
---
# HttpClientResponse (clase)

Un objeto que representa la respuesta a una consulta HTTP.

Solo se puede obtener después de que la propiedad `response` ejecute una consulta HTTP.

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [cuerpo](p-httpclientresponse-body.md) | Cuerpo de la respuesta HTTP en forma de objeto MemoryBuffer. |
| [código](p-httpclientresponse-code.md) | El código devuelto de la respuesta HTTP en forma de entero JavaScript. |
| [páginaDeCódigos](p-httpclientresponse-codepage.md) | El valor de codePage de la respuesta. Se utiliza para descodificar el cuerpo de la respuesta HTTP. |
| [encabezado](p-httpclientresponse-header.md) | Un objeto que contiene todos los encabezados HTTP. |
| [encabezados](p-httpclientresponse-headers.md) | La lista de encabezados para la respuesta HTTP agrupada por nombre. |
| [mensaje](p-httpclientresponse-message.md) | El mensaje transportado por la respuesta HTTP. |

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
