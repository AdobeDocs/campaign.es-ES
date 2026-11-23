---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 10%
---
# lista

Devuelve la lista de archivos del servidor en un directorio especificado.

```text
list (URL, pattern [, max ])
```

## Parámetros

**Dirección URL** del servidor FTP como dirección URL.

**pattern** Archivo y máscara de la lista de archivos que se van a recuperar.

**máximo** número máximo de archivos que se devolverán. Si falta este parámetro, el método devolverá la lista completa de archivos.

## Valor devuelto

Tabla que contiene los nombres de archivo correspondientes a la ruta y máscara especificadas.

## Observaciones

Si el comando FTP falla y se genera una excepción. Ejemplo:

```javascript
var ftp = new FTP
var files = ftp.list("ftp://ftp.funet.fi/", "pub/standards/RFC/rfc*.txt", 10)
for(var i in files)
  logInfo(files[i])
ftp.dispose()
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
