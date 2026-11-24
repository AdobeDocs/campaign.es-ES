---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 5%
---
# open

Abre el archivo en modo de lectura o escritura.

```text
open ( [mode ] [, codepage ])
```

## Parámetros

**modo** Modo de apertura de archivos. El modo puede tener uno de varios valores:

* &quot;r&quot;: abre el archivo en modo de solo lectura. Este modo es el predeterminado.
* &quot;w&quot;: abre el archivo en modo de escritura.
* &quot;a&quot;: abre el archivo en modo &quot;anexar&quot;, los datos escritos en el archivo se anexan al final.

**página de códigos** Codificación del archivo. La codificación puede tener uno de los siguientes valores:

* File.CODEPAGE\_CURRENT: esta es la página de códigos predeterminada.
* File.CODEPAGE\_OEM
* File.CODEPAGE\_MAC
* File.CODEPAGE\_THREAD
* Archivo.CODEPAGE\_LATIN1
* Archivo.CODEPAGE\_LATIN2
* Archivo.CODEPAGE\_ISOLATIN1
* File.CODEPAGE\_ISOLATIN2
* Archivo.CODEPAGE\_OEMLATIN1
* Archivo.CODEPAGE\_OEMLATIN2
* File.CODEPAGE\_UTF7
* File.CODEPAGE\_UTF8
* File.CODEPAGE\_ISOLATIN9
* Archivo.CODEPAGE\_OEMUS
* File.CODEPAGE\_SHIFTJIS
* Archivo.CODEPAGE\_BIG5
* File.CODEPAGE\_CHINESE
* File.CODEPAGE\_EUCKOREAN
* File.CODEPAGE\_UTF16LE
* File.CODEPAGE\_UTF16BE

## Valor devuelto

Ninguna.

## Observaciones

Si no se puede abrir el archivo, se produce una excepción.

## Funciones

**Método de clase:** [Archivo](c-file.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
