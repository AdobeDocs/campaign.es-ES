---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 25%
---
# writeln

Escribe una línea de texto en el archivo.

```text
writeln (line)
```

## Parámetros

**línea**: la línea de texto que se va a escribir.

## Valor devuelto

Ninguna.

## Observaciones

Ejemplo:

```javascript
var f = new File("c:/file.txt")
f.open("a")
f.writeln("line 1")
f.writeln("line 2")
f.close()
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
