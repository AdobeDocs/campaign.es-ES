---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# escapeUrl

Convierte una cadena de caracteres para insertarla en una dirección URL.

```text
escapeUrl (value)
```

## Parámetros

**valor** Cadena de caracteres para convertir.

## Valor devuelto

La cadena de caracteres después de la conversión.

## Observaciones

La función transforma caracteres no alfanuméricos distintos de $-\_.\!\*&#39;(),?/:@&amp;= en el valor hexadecimal correspondiente. La función cumple con la especificación RFC1738 y solo le permite codificar caracteres ISO-latinos. Para codificar caracteres UTF-8, utilice la función JavaScript encodeURIComponent(). Ejemplo:

```javascript
escapeUrl("a#value!")               // "a%23value!"
escapeUrl("Système d'exploitation") // "Syst%E8me%20d'exploitation"
```

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
