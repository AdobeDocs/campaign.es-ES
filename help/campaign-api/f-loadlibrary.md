---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 11%
---
# loadLibrary

Carga una biblioteca de JavaScript.

```text
loadLibrary (filename [, boolean ])
```

## Parámetros

**nombre de archivo**: nombre de la biblioteca JavaScript que se va a cargar.

**boolean**: habilita o deshabilita la caché de carga. El valor predeterminado es True.

> Nota: Cuando el parámetro se establece en false, debe utilizar la función logon() antes de que la llamada loadLibrary se autentique como operador.

## Valor devuelto

Ninguna.

## Observaciones

La caché de está habilitada de forma predeterminada. Si la caché está deshabilitada, se consulta la base de datos para cada llamada. Esta consulta le permite cargar la última versión de la biblioteca. Ejemplo: loadLibrary(&#39;xtk:shared/nl.js&#39;)

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
