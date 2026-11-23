---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 17%
---
# toXML

Devuelve un objeto XML JavaScript obtenido del contenido de [MemoryBuffer](c-memorybuffer.md). Esta función está obsoleta. Use [toDocument()](m-memorybuffer-todocument.md)

```text
toXML ( [codePage ])
```

## Parámetros

**codePage** Un entero que codifica la página de caracteres utilizados. De forma predeterminada, MemoryBuffer.CODEPAGE\_UTF8.

## Valor devuelto

El contenido de un sello en forma de objeto XML.

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
