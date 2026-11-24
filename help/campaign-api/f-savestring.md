---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 22%
---
# saveString

Este comando está obsoleto, use [saveFile()](f-savefile.md). Guarda una cadena de caracteres en un archivo.

```text
saveString (text, filename [, codePage ])
```

## Parámetros

**texto** La cadena de texto que se va a guardar.

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

Si no se especifica la codificación de caracteres, se utiliza el servidor predeterminado.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
