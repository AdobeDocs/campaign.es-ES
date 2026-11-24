---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%
---
# cryptString

> Advertencia:
>
> Esta función está totalmente obsoleta. Para obtener más información, consulte esta [página](https://experienceleague.adobe.com/es/docs/campaign-classic/using/technotes/gcm-functions#deprecated-functions-headding-anchor-depracated-functions).

Codifica una cadena de caracteres con la clave de la instancia o con cualquier otra clave.

```text
cryptString (str [, key ] [, useSalt ])
```

## Parámetros

**str** Cadena de caracteres que se va a cifrar.

**clave** La clave de cifrado AES se codifica en base 64: 256 bits si la longitud de la clave es 32; 192 bits si la longitud de la clave es 24; 128 bits si la longitud de la clave es 16 o si no se especifica ninguna clave.

**useSalt** Use una sal de los datos para cifrar. True de forma predeterminada.

## Valor devuelto

Devuelve la cadena de caracteres cifrada

## Observaciones

El cifrado se realiza según el método siguiente:

* La cadena de caracteres Unicode se transforma en una cadena UTF-8.
* Se agrega un carácter de verificación al final.
* Esta cadena se cifra utilizando el algoritmo AES en el modo Cipher Block Chaining (CBC) con un vector de inicialización nulo. Si no se proporciona ninguna clave como parámetro, se utiliza la clave de instancia.
* El bloque cifrado se convierte en base 64.

El descifrado se realiza mediante la función [decryptString](f-decryptstring.md).

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
