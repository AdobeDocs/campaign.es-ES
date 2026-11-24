---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 13%
---
# cargar

> Advertencia:
>
> El acceso a través de las API de archivo está limitado a **var**, **sftp** y a las carpetas temporales de Adobe Campaign.

Crea un nuevo documento a partir de un archivo XML.

```text
load (filename [, allowEmpty ])
```

## Parámetros

**nombre de archivo** Nombre del archivo que se va a cargar.

**allowEmpty** Si es true, no genera una excepción si el archivo está vacío (default=false).

## Valor devuelto

Ninguna.

## Observaciones

Se genera una excepción si el archivo no se puede cargar o si el contenido del archivo no es un documento XML válido. Esta función se aplica a la clase DOMDocument. Ejemplo:

```javascript
var doc = DOMDocument.load("data/test.xml")
```

## Funciones

**Método de clase:** [DOMDocument](c-domdocument.md)

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
