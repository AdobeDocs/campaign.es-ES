---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 16%
---
# saveXmlString

Este comando está obsoleto, use [saveXmlFile()](f-savexmlfile.md). Guarda una cadena de caracteres correspondiente a un documento XML en un archivo.

```text
saveXmlString (text, filename [, codePage ])
```

## Parámetros

**texto** Documento XML en forma de cadena de caracteres para guardar.

**nombre de archivo**: nombre completo del archivo que se va a guardar.

**codePage**: este parámetro opcional permite especificar la codificación de caracteres. Ejemplo:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valor devuelto

Ninguna.

## Observaciones

Esta función inserta un prólogo XML en el archivo, si es necesario, y especifica la codificación del documento. Si no se especifica la codificación de caracteres, se utiliza el servidor predeterminado.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
