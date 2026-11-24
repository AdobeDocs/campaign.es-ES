---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 27%
---
# enameTo

Cambia el nombre de un archivo.

```text
renameTo (fileName)
```

## Parámetros

**fileName** Nuevo nombre de archivo (debe ser una ruta de acceso completa).

## Valor devuelto

Ninguna.

## Observaciones

Ejemplos:

```javascript
var f = new File("c:/file.txt")
f.renameTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.renameTo("c:/dir/")
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
