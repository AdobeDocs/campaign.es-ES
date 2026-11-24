---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 11%
---
# lista

Muestra el contenido de un directorio.

```text
list ( [mask ] [, sort ] [, noCase ])
```

## Parámetros

**máscara** La máscara de búsqueda (\* de forma predeterminada).

**sort** true para ordenar el resultado (false de forma predeterminada).

**noCase** true para omitir la clase al ordenar (false de forma predeterminada).

## Valor devuelto

Tabla que contiene la lista de archivos ( [Archivo](c-file.md) ) que coinciden con la ruta de acceso y la máscara especificadas.

## Observaciones

El nombre del directorio debe terminar con / en Linux y con \\ en Windows. Ejemplo:

```javascript
var dir = new File("c:\\temp\\")
var files = dir.list("*.*")
for each (var file in files)
  logInfo(file.name)
```

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
