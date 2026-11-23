---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 11%
---
# hmac

Calcula el hash MD5, SHA-1 o SHA-256 del búfer.

```text
hmac (key [, algo ])
```

## Parámetros

Clave **key**, en forma de búfer.

**algo** Tipo de hash a usar. Los valores posibles son &quot;MD5&quot;, &quot;SHA1&quot; o &quot;SHA256. No distinguen entre mayúsculas y minúsculas, por lo que los valores se pueden introducir en minúsculas o mayúsculas. De forma predeterminada, el valor &quot;SHA1&quot; está seleccionado si no se especifica el parámetro.

## Valor devuelto

El hash MD5, SHA-1 o SHA-256 (según el tipo de hash elegido) del búfer.

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
