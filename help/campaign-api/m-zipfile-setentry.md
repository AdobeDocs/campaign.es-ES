---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# setEntry

Agrega o actualiza un archivo en el archivo.

```text
setEntry (filename, buffer)
```

## Parámetros

**nombre de archivo** Nombre del archivo de origen.

**búfer** MemoryBuffer que contiene el archivo.

## Valor devuelto

Ninguna.

## Observaciones

El archivo no se modificará correctamente en el disco hasta que se llame al método [save()](m-zipfile-save.md).

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
