---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%
---
# sha1

Calcula la firma SHA-1 del contenido MemoryBuffer.

```text
sha1 ()
```

## Parámetros

Ninguna.

## Valor devuelto

Una cadena de caracteres que es la representación hexadecimal de la firma SHA-1.

## Observaciones

Ejemplo:

```javascript
var memBuf = new MemoryBuffer();
memBuf.fromString("Hello world", "utf-8");
logInfo(memBuf.sha1()); // Writes down  => 7b502c3a1f48c8609ae212cdfb639dee39673f5e
```

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
