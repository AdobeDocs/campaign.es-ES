---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 12%
---
# open

Carga un archivo existente.

```text
open ()
```

## Parámetros

Ninguna.

## Valor devuelto

Ninguna.

## Observaciones

En el caso de un archivo existente, primero debe llamar al método ⌐[fileCount](p-zipfile-filecount.md) para recuperar el número de archivos o a [getEntry()](m-zipfile-getentry.md) para extraer un archivo. El método genera una excepción si el archivo no existe o si no es un archivo válido.

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
