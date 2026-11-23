---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 31%
---
# fromString

Carga el contenido de una cadena de caracteres en el búfer.

```text
fromString (string [, codepage ])
```

## Parámetros

**cadena** La cadena de caracteres.

**página de códigos**: página de códigos utilizada para serializar la cadena en el búfer. Este parámetro opcional permite especificar la codificación de caracteres. Por ejemplo:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valor devuelto

Ninguna.

## Funciones

**Método de clase:** [MemoryBuffer](c-memorybuffer.md)

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
