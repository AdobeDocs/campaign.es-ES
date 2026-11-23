---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 25%
---
# copyTo

Copia un archivo.

```text
copyTo (fileName)
```

## Parámetros

**fileName** Nombre del archivo o carpeta de destino (debe ser la ruta completa).

## Valor devuelto

Ninguna.

## Observaciones

Ejemplos:

```javascript
var f = new File("c:/file.txt")
f.copyTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.copyTo("c:/dir/")
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
