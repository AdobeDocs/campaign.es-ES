---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%
---
# ofuscar

Convierte un entero en una cadena de caracteres. El valor original se puede recuperar llamando a [unobfuscate](f-unobfuscate.md).

```text
obfuscate (value [, size ] [, version ])
```

## Parámetros

**valor** El entero que se va a proteger.

**size** El tamaño de la cadena resultante de la ofuscación. Un entero entre 6 y 10. 6 de forma predeterminada.

**versión**: la versión de ofuscación que se aplicará. 0 de forma predeterminada.

## Valor devuelto

Cadena de caracteres que representa el entero ofuscado.

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
