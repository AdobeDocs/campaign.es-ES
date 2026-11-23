---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%
---
# DESencrypt

> Advertencia:
>
> Esta función está obsoleta. Use [cryptString()](f-cryptstring.md).

Digitaliza una cadena con el algoritmo DES.

```text
DESencrypt (value [, key ] [, cipher mode ] [, initialization vector ] [, padding ])
```

## Parámetros

**value** cadena que se va a digitalizar

**key** La clave representada en hexadecimal. La clave debe tener 64 bits o 16 caracteres hexadecimales. De forma predeterminada, se utiliza el identificador de la base de datos.

**modo de cifrado**: método de codificación de bloques. Una cadena de caracteres. es decir, &quot;CBC&quot;, &quot;ECB&quot; o &quot;EDE&quot;. De forma predeterminada, &quot;CBC&quot;.

**vector de inicialización**: el vector de inicialización en forma de cadena hexadecimal. Exactamente 8 octetos, es decir, 16 caracteres. Una cadena vacía de forma predeterminada.

**padding** El tipo de padding. Una cadena de caracteres, por ejemplo, &quot;PKCS5PADDING&quot; o &quot;PKCS7PADDING&quot;. De forma predeterminada, una cadena vacía, lo que significa que se agrega un &#39;\\0&#39; al final de la cadena que se va a cifrar.

## Valor devuelto

La cadena digitalizada representada en la base 64.

## Observaciones

* Una clave DES tiene 56 bits útiles y 8 bits utilizados para la paridad; estos bits se omiten.
* El valor cifrado efectivamente por el algoritmo DES será la representación de 8 bits de Windows-1252 de la cadena, terminando con un carácter ASCII 0 y relleno a varios de 64 bits con ceros binarios.
* El valor digitalizado tiene un valor de 64 bits de longitud múltiple.

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
