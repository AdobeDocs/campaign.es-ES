---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 5%
---
# decryptPassword

> Advertencia:
>
> Esta documentación se ha actualizado. Para obtener más información, consulte esta [página](https://experienceleague.adobe.com/es/docs/campaign-classic/using/technotes/gcm-functions#decryptpassword-headding-anchor-decryptpassword-javascript).

Descifra una contraseña almacenada en una cuenta externa.

```text
decryptPassword (str)
```

## Parámetros

**str** La cadena de caracteres cifrada.

## Valor devuelto

Devuelve la contraseña de texto sin formato.

## Observaciones

Esta función no se puede invocar en flujos de trabajo, aplicaciones web, informes o envíos. Se puede llamar en implementaciones de llamadas JSSP o SOAP. Ejemplo:

```javascript
          function nms_extAccount_LogonToRemoteInstance(remoteInstanceUrl, login, encryptedPassword) {
          var cnx = null, sessionService = null;
          try
              {
                  var cnx = new HttpSoapConnection(remoteInstanceUrl + '/nl/jsp/soaprouter.jsp', 'utf-8', 0);
                  sessionService = new SoapService(cnx, 'xtk:session');
                  sessionService.addMethod("Logon", "xtk:session#Logon",
                      ["token", "string", "login", "string", "password", "string", "parameters", "NLElement"],
                      ["sessionToken", "string", "sessionInfo", "NLElement", "securityToken", "string"]);
                  return sessionService.Logon("", login, decryptPassword(encryptedPassword), <parameters/>);
              }
          catch( e ) {
          logError(e);
          }
          finally {
          if( sessionService ) sessionService.dispose();
          if( cnx ) cnx.dispose();
          }
          })
      
```

## Funciones

**Disponible en:**

* Método SOAP
