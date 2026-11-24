---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 16%
---
# saveXmlFile

> Advertencia:
>
> El acceso a través de las API de archivo está limitado a **var**, **sftp** y a las carpetas temporales de Adobe Campaign.

Guarda una cadena de caracteres correspondiente a un documento XML en un archivo.

```text
saveXmlFile (text, filename [, codePage ])
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
