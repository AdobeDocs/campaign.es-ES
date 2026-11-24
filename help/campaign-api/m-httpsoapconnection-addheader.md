---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 19%
---
# addHeader

Agrega un encabezado HTTP

```text
addHeader (headerName, headerValue)
```

## Parámetros

**headerName** cadena de caracteres que es el nombre del encabezado HTTP.

**headerValue** cadena de caracteres que es el contenido del encabezado HTTP.

## Valor devuelto

Ninguna.

## Observaciones

Los encabezados especificados de esta manera prevalecen sobre los encabezados predeterminados durante las llamadas de SOAP. Ejemplo:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.addHeader("Authorization","Basic " + memBuf.toBase64());
```

## Funciones

**Método de clase:** [HttpSoapConnection](c-httpsoapconnection.md)

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
