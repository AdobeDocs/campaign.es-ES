---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 6%
---
# MemoryBuffer (Clase)

Representa un contenido binario almacenado en memoria.

Un es un objeto intermedio para manipular datos desde y hacia un archivo.

## Métodos

| Método | Descripción |
| --- | --- |
| [eliminar](m-memorybuffer-dispose.md) | Libera los recursos utilizados por el objeto. |
| [cargar](m-memorybuffer-load.md) | Carga el contenido de un archivo en el búfer. |
| [guardar](m-memorybuffer-save.md) | Guarda el contenido del búfer en un archivo. |
| [toXML](m-memorybuffer-toxml.md) | Devuelve un objeto XML JavaScript obtenido del contenido de [MemoryBuffer](c-memorybuffer.md) Esta función está obsoleta. Use [toDocument()](m-memorybuffer-todocument.md) |
| [toDocument](m-memorybuffer-todocument.md) | Devuelve un documento XML a partir del contenido de texto de este búfer. |
| [toString](m-memorybuffer-tostring.md) | Devuelve el contenido de [MemoryBuffer](c-memorybuffer.md) en forma de cadena de caracteres. |
| [fromString](m-memorybuffer-fromstring.md) | Carga el contenido de una cadena de caracteres en el búfer. |
| [toBase64](m-memorybuffer-tobase64.md) | Convierte el búfer o parte de la cadena de caracteres codificada en base 64. |
| [appendBase64](m-memorybuffer-appendbase64.md) | Anexa datos de una cadena de caracteres codificada en base 64 al final del búfer. |
| [quitar todo](m-memorybuffer-removeall.md) | Vacía el búfer. |
| [sha1](m-memorybuffer-sha1.md) | Calcula la firma SHA-1 del contenido MemoryBuffer. |
| [sha224](m-memorybuffer-sha224.md) | Calcula la firma SHA-2 de 224 bits del contenido MemoryBuffer. |
| [sha256](m-memorybuffer-sha256.md) | Calcula la firma SHA-2 de 256 bits del contenido MemoryBuffer. |
| [sha384](m-memorybuffer-sha384.md) | Calcula la firma SHA-2 de 384 bits del contenido MemoryBuffer. |
| [sha512](m-memorybuffer-sha512.md) | Calcula la firma SHA-2 de 512 bits del contenido MemoryBuffer. |
| [fromHexString](m-memorybuffer-fromhexstring.md) | Carga el contenido de una cadena hexadecimal en el búfer. |
| [toHexString](m-memorybuffer-tohexstring.md) | Convierte el búfer en una cadena de caracteres hexadecimales. |
| [hmac](m-memorybuffer-hmac.md) | Calcula el hash MD5, SHA-1 o SHA-256 del búfer. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [tamaño](p-memorybuffer-size.md) | Devuelve el tamaño del búfer en bytes. |
| [isEmpty](p-memorybuffer-isempty.md) | Devuelve verdadero si el búfer está vacío. |

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
