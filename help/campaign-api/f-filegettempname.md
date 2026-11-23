---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# fileGetTempName

Genera un nombre de archivo temporal.

```text
fileGetTempName ( [directory ] [, prefix ] [, extension ])
```

## Parámetros

**directorio** Directorio del archivo temporal. Si está vacío, utilice el directorio temporal definido por el sistema.

**prefijo** Prefijo con 4 caracteres como máximo. Si está vacío, se utiliza el prefijo tmp.

**extensión** Extensión de archivo.

## Valor devuelto

Nombre completo del archivo.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
