---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 3%
---
# generateTrackingTag

Genera automáticamente una etiqueta de JavaScript para el seguimiento web.

```text
generateTrackingTag (request [, tagid ] [, folder ])
```

## Parámetros

**solicitud**: objeto HttpServletRequest

**tagid** Una cadena de caracteres que representan el nombre del tagid personalizado. Si está vacía, la función genera la etiqueta en función del nombre de la ruta.

**carpeta** Una cadena de caracteres que representan el nombre interno de una carpeta. Si está vacía, la etiqueta se crea en el directorio predeterminado, es decir, &quot;etiquetas de seguimiento web&quot;.

## Valor devuelto

Una cadena de caracteres que contiene el código JavaScript que se va a incluir.

## Observaciones

La etiqueta generada se basa en el nombre de la aplicación web, la página html, el controlador o, más en general, el nombre de la ruta si no se introduce el tagid. El último parámetro especifica la carpeta de destino de la etiqueta. Para invocar la función, pase el objeto de solicitud como argumento. Tenga en cuenta el uso de &lt;%==, ya que la función genera código html. Ejemplo:

```xml
              <%== generateTrackingTag(request, request.getParameter('art'), request.getParameter('cat')) %>
```

## Funciones

**Disponible en:**

* JSSP
* WebApp
