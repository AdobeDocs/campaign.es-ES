---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 10%
---
# getEntry

Extrae un archivo del archivo.

```text
getEntry (filename)
```

## Parámetros

**nombre de archivo** Nombre del archivo en el archivo.

## Valor devuelto

⌐ [MemoryBuffer](c-memorybuffer.md) que contiene el contenido del archivo.

## Observaciones

El archivo debe haberse abierto con el método ⌐[open()](m-zipfile-open.md) para poder usar este método. De lo contrario, se genera una excepción. Ejemplo: El siguiente ejemplo extrae el archivo dir/content.xml de un archivo y lo guarda en la carpeta /tmp/.

```javascript
var zip = new ZipFile("/tmp/archive.zip")
zip.open()

var content = zip.getEntry("dir/content.xml")
content.save("/tmp/content.xml")

zip.dispose()
content.dispose()
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
