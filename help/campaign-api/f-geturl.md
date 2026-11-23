---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%
---
# getUrl

Recupera un contenido de texto de una dirección URL.

```text
getUrl (url [, timeout ])
```

## Parámetros

**url** La dirección de la página que se va a recuperar.

**tiempo de espera** Tiempo de espera de conexión. Si la conexión no se puede establecer dentro del retraso determinado, se genera un error y se interrumpe la secuencia de comandos.

## Valor devuelto

Cadena de caracteres que contiene la página de texto.

## Observaciones

La codificación de la cadena devuelta es la codificación especificada por la respuesta (Content-Type). Si se produce un error durante la descarga o si el código devuelto no es 200 (OK), se genera un error y se interrumpe la secuencia de comandos que se está ejecutando. Ejemplo:

```javascript
      var content = getUrl("http://www.google.com/index.html")
```

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Envío del mensaje
* Regla de tipología
* Importación
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
