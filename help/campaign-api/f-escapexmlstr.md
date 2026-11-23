---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 27%
---
# escapeXmlStr

Convierte una cadena de caracteres al formato XML.

```text
escapeXmlStr (value)
```

## Parámetros

**valor** Cadena de caracteres para convertir.

## Valor devuelto

La cadena de caracteres después de la conversión.

## Observaciones

La función transforma los caracteres &amp;, &lt;, > y \\&quot; en las secuencias de escape correspondientes:

* &amp; &amp;
* &lt; &lt;
* > >
* &quot; &amp;quot;

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
