---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 28%
---
# encabezado

Una cadena de caracteres copiada literalmente en el encabezado de SOAP.

```text
header
```

## Observaciones

Les chaînes de caractères sont recopiées in-extenso dans l&#39;en-tête SOAP sans vérification. Ejemplo:

```javascript
      var cnx = new HttpSoapConnection(result.serverURL, "utf-8", HttpSoapConnection.SOAP_11)
var service = new SoapService(cnx, "urn:partner.soap.sforce.com")
service.header = "<ns1:SessionHeader xmlns:ns1='urn:partner.soap.sforce.com'><ns1:sessionId>123456</ns1:sessionId></ns1:SessionHeader>"
```

## Funciones

**Propiedad de clase:** [SoapService](c-soapservice.md)

**Sólo lectura:**

No

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
