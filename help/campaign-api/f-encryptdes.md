---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%
---
# encryptDES

> Advertencia:
>
> Esta función está obsoleta. Use [cryptString()](f-cryptstring.md).

Codifica una cadena con el algoritmo DES.

```text
encryptDES (key, value [, cipher mode ] [, initialization vector ] [, padding ])
```

## Parámetros

**key** La clave representada en hexadecimal. La clave debe tener 64 bits, es decir, 16 caracteres hexadecimales.

**valor** Cadena que se va a cifrar

**modo de cifrado** Método para codificar bloques. Una cadena de caracteres. es decir, &quot;CBC&quot;, &quot;ECB&quot; o &quot;EDE&quot;. De forma predeterminada, &quot;CBC&quot;.

**vector de inicialización**: el vector de inicialización en forma de cadena hexadecimal. Exactamente 8 octetos, es decir, 16 caracteres. Una cadena vacía de forma predeterminada.

**relleno** Tipo de relleno. Una cadena de caracteres, por ejemplo, &quot;PKCS5PADDING&quot; o &quot;PKCS7PADDING&quot;. De forma predeterminada, una cadena vacía, lo que significa que se agrega &#39;\\0&#39; al final de la cadena que se va a cifrar.

## Valor devuelto

La cadena cifrada representada en base 64.

## Observaciones

* Una clave DES tiene 56 bits útiles y 8 bits utilizados para la paridad; estos bits se omiten.
* El valor cifrado efectivamente por el algoritmo DES será la representación de 8 bits de Windows-1252 de la cadena, terminando con un carácter ASCII 0 y relleno a varios de 64 bits con ceros binarios.
* El valor cifrado es un múltiplo de palabras de 64 bits.

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
