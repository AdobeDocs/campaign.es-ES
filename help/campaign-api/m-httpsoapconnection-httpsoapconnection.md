---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 13%
---
# HttpSoapConnection

Crea una conexión HTTP a un servidor de SOAP.

```text
HttpSoapConnection (url [, codepage ] [, protocol ] [, async ])
```

## Parámetros

**url** URL del servidor que incluye la ruta.

**página de códigos** Codificación para la serialización de la llamada de SOAP. Este parámetro opcional permite especificar la codificación de caracteres. De forma predeterminada, la codificación es UTF-8. Ejemplo:

* iso-8859-1
* utf-8
* utf-16

**protocolo** Tipo de protocolo SOAP utilizado. Este parámetro opcional le permite especificar el protocolo de SOAP utilizado, que es SOAP\_11 de forma predeterminada Valores posibles:

* SOAP\_11: SOAP protocol 1.1.
* SOAP\_12: protocolo SOAP 1.2.
* 0: Protocolo de SOAP interno de Adobe Campaign.

**async** Boolean establecido en true si la conexión está destinada a ejecutar una consulta asincrónica. De forma predeterminada, se establece en false.

## Valor devuelto

Ninguna.

## Observaciones

Ejemplos:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp")
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-16", HttpSoapConnection.SOAP_11)
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-8", 0)
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
