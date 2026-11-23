---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 9%
---
# descargar

Descarga un archivo desde el servidor a un archivo local o a la memoria.

```text
download (URL [, append ])
```

## Parámetros

**URL** URL del archivo a descargar.

**anexar** De forma predeterminada, si el archivo descargado ya existe en el disco local, el nuevo archivo recibido lo sobrescribirá. Si el booleano está activado, Adobe Campaign escribirá el contenido descargado en el archivo con el mismo nombre junto con el contenido existente.

## Valor devuelto

Ninguna.

## Observaciones

Para recuperar el archivo en un archivo local, comience por el método setFile. Ejemplo:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.download("ftp://ftp.funet.fi/pub/standards/RFC/rfc2068.txt")
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
