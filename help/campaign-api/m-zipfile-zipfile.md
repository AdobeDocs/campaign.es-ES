---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 17%
---
# ArchivoZip

> Advertencia:
>
> El acceso a través de las API de archivo está limitado a **var**, **sftp** y a las carpetas temporales de Adobe Campaign.

Crea un nuevo objeto Zip asociado a un archivo.

```text
ZipFile (filename)
```

## Parámetros

**nombre de archivo**: nombre del archivo que se va a cargar o crear.

## Valor devuelto

Ninguna.

## Observaciones

Ejemplo:

```javascript
var zip = new ZipFile("/tmp/archive.zip")
```

## Funciones

**Método de clase:** [ArchivoZip](c-zipfile.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
