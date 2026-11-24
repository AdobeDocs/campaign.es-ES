---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 14%
---
# toBase64

Convierte el búfer o parte de la cadena de caracteres codificada en base 64.

```text
toBase64 ( [start ] [, length ])
```

## Parámetros

**start**: número de bytes que se omitirán al principio del búfer. El primer byte corresponde al valor 0 (valor predeterminado).

**length** número de bytes para convertir. De forma predeterminada, se tienen en cuenta todos los bytes restantes.

## Valor devuelto

El contenido del búfer codificado en base 64.

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
