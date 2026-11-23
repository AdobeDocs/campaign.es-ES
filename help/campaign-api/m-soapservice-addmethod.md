---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 6%
---
# addMethod

Declara una función en el servicio.

```text
addMethod (name, action, arguments, responses, requestNodeName, responseNodeName)
```

## Parámetros

**nombre** Nombre del método. Es el nombre que se expone en JavaScript y el nombre del método SOAP.

**action** parámetro SOAP-Action.

**argumentos** Declaración de argumentos en forma de tabla que contiene una lista de cadenas agrupadas por pares. La primera cadena es el nombre del argumento y la segunda corresponde al tipo: \[&quot;name1&quot;, &quot;type1&quot;, &quot;name2&quot;, &quot;type2&quot;, ...\]

**respuestas** Declaración de valores devueltos en forma de tabla que contiene una lista de cadenas agrupadas por pares: La primera cadena es el nombre del argumento y la segunda corresponde al tipo: \[&quot;name1&quot;, &quot;type1&quot;, &quot;name2&quot;, &quot;type2&quot;, ...\]

**requestNodeName** Una cadena de caracteres que especifica el nombre del nodo XML de la consulta SOAP en lugar del nombre del método.

**responseNodeName** Una cadena de caracteres que especifica el nombre del nodo XML de la respuesta de SOAP en lugar del nombre del método seguido de Response.

## Valor devuelto

Ninguna.

## Observaciones

Se admiten los siguientes tipos:

* cadena
* booleano
* largo
* corto
* byte
* flotante
* doble
* fecha
* tiempo
* datetime
* NLDocument
* NLElement
* NLRawXML
* NLCollection

Cuando se declara un método en el servicio, este se convierte en un método del servicio y se puede invocar directamente llamando al método por su nombre. El tipo NLRawXML utilizado en un parámetro entrante copia todo el nodo XML para reemplazar el argumento. Utilizado como tipo de valor devuelto, contiene todo el primer elemento secundario de la respuesta de SOAP. Su uso implica que la respuesta de SOAP solo tiene un elemento secundario. El tipo NLCollection utilizado en un parámetro entrante copia todos los elementos secundarios para reemplazar el argumento. Esto resulta útil cuando el argumento entrante es un parámetro de variable. Utilizado como tipo de valor devuelto, contiene toda la respuesta de SOAP, ya que esta es la raíz del valor devuelto. En caso de errores, se genera una excepción. Si se trata de un error de SOAP correctamente formado, la excepción generada tiene una propiedad soapFault y contiene el nodo XML del error de SOAP. Ejemplo:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
session.addMethod("GetOption", "xtk:session#GetOption",
  ["token", "string", "name", "string"],
  ["value", "string", "type", "byte"])
try
{
var result  = session.GetOption("admin/", "NmsBroadcast_DefaultProvider")
var value   = result[0]
var type    = result[1]
logInfo("Value = " + value)
logInfo("Type = " + type)
}
catch( e )
{
  if( e.soapFault )
    logInfo("A SOAP Fault occured : " + e.soapFault.toXMLString());
  else
    logInfo("An error occured : " + e);
}
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
