---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 13%
---
# loadXmlFile

> Advertencia:
>
> El acceso a través de las API de archivo está limitado a **var**, **sftp** y a las carpetas temporales de Adobe Campaign.

Esta función está obsoleta; use [DOMDocument.load()](m-domdocument-load.md). Carga un archivo en forma de objeto de documento XML

```text
loadXmlFile (filename [, noErr ])
```

## Parámetros

**nombre de archivo**: nombre completo del archivo que se va a cargar.

**noErr** Si es true, no hay error si el archivo está vacío (default=false).

## Valor devuelto

Un documento XML.

## Observaciones

Esta función permite detectar la página de códigos del archivo gracias a la detección de BOM y el prólogo XML.

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
