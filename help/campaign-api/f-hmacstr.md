---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 6%
---
# hmacStr

Calcula el hash MD5, SHA-1 o SHA-256 de una cadena de caracteres. La cadena se codifica automáticamente en UTF-8 antes del cálculo.

```text
hmacStr (string [, key ] [, algo ])
```

## Parámetros

**cadena** Cadena en la que se va a calcular el hash.

Clave **key**, en forma de cadena de caracteres. Se convierte automáticamente en UTF-8. Si falta la clave, el servidor utilizará una clave que depende de la instancia y que solo es válida en esta instancia.

**algo** tipo de hash a usar. Los valores posibles son &quot;MD5&quot;, &quot;SHA1&quot; o &quot;SHA256&quot;. Se omiten las mayúsculas y minúsculas, por lo que los valores se pueden introducir en minúsculas o mayúsculas. El valor &quot;SHA1&quot; está seleccionado de forma predeterminada si no se especifica ningún parámetro.

## Valor devuelto

El hash MD5, SHA-1 o SHA-256 (según el tipo de hash seleccionado) de la cadena pasada como parámetro.

## Observaciones

Para los tipos MD5 y SHA-1, la clave puede tener hasta 64 caracteres (512 bits) después de la conversión a UTF-8. Para el tipo SHA-256, la clave puede tener hasta 32 caracteres (256 bits) después de la conversión a UTF-8.

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
