---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 23%
---
# loadString

Este comando está obsoleto, use ⌐[loadFile()](f-loadfile.md). Devuelve el contenido de un archivo de texto

```text
loadString (filename [, codePage ])
```

## Parámetros

**nombre de archivo**: nombre completo del archivo que se va a cargar.

**codePage**: este parámetro opcional permite especificar la codificación de caracteres. Ejemplo:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valor devuelto

Cadena de caracteres correspondiente al contenido del archivo de texto.

## Observaciones

Si no se especifica la codificación de caracteres, se utiliza el servidor predeterminado.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Envío del mensaje
* Regla de tipología
* Importación
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
