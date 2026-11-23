---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%
---
# readln

Lee una línea del archivo de texto.

```text
readln ()
```

## Parámetros

Ninguna.

## Valor devuelto

Cadena que contiene la línea siguiente del archivo o ⌐null si se llega al final del archivo.

## Observaciones

Ejemplo:

```javascript
var f = new File("c:/dummy.xml")
f.open("r", File.CODEPAGE_UTF8)
var line
while( line = f.readln() )
  logInfo(line)
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
