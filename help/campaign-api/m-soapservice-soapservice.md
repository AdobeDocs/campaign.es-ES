---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 26%
---
# SoapService

Crea un servicio para llamar a las funciones de un servicio Web.

```text
SoapService (cnx, namespace)
```

## Parámetros

**cnx**: la conexión HTTP ([HttpSoapConnection](c-httpsoapconnection.md)).

**área de nombres** del servicio.

## Valor devuelto

Ninguna.

## Observaciones

Ejemplo:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
```

## Funciones

**Método de clase:** [SoapService](c-soapservice.md)

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
