---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 8%
---
# decryptDES

> Advertencia:
>
> Esta función está obsoleta. Use [decryptString()](f-decryptstring.md).

Descifra una cadena con el algoritmo DES.

```text
decryptDES (key, value [, cipher mode ] [, initialization vector ])
```

## Parámetros

**key** La clave representada en hexadecimal. La clave debe tener 64 bits o 16 caracteres hexadecimales.

**value** Los datos que se van a cifrar representados en la base 64.

**modo de cifrado** Método para codificar bloques. Una cadena de caracteres. es decir, &quot;CBC&quot;, &quot;ECB&quot; o &quot;EDE&quot;. De forma predeterminada, &quot;CBC&quot;.

**vector de inicialización**: el vector de inicialización en forma de cadena hexadecimal. Exactamente 8 octetos, es decir, 16 caracteres. Una cadena vacía de forma predeterminada.

## Valor devuelto

La cadena de caracteres en texto no cifrado.

## Observaciones

* Una clave DES tiene 56 bits útiles y 8 bits utilizados para la paridad; estos bits se omiten.
* Los datos se descifrarán como una cadena de 8 bits en la página de códigos de Windows-1252.
* La longitud de los datos cifrados debe ser múltiplo de 64 bits.

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
