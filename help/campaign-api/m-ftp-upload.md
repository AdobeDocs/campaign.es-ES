---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%
---
# cargar

Descargar un archivo desde un archivo local a un servidor FTP.

```text
upload (URL)
```

## Parámetros

URL del servidor **URL**.

## Valor devuelto

Ninguna.

## Observaciones

La dirección URL debe comenzar con &#39;ftp:&#39; Ejemplo:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.upload("ftp://ftp.funet.fi/pub/standards/RFC")
```

## Funciones

**Método de clase:** [FTP](c-ftp.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
