---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 22%
---
# loadFile

> Advertencia:
>
> El acceso a través de las API de archivo está limitado a **var**, **sftp** y a las carpetas temporales de Adobe Campaign.

Devuelve el contenido de un archivo de texto

```text
loadFile (filename [, codePage ])
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
