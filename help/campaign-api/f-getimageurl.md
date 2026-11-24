---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 22%
---
# getImageUrl

Permite la generación de la URL de acceso al recurso público

```text
getImageUrl (ID|internal name)
```

## Parámetros

**ID\|nombre interno** ID del recurso público o nombre interno del recurso.

## Valor devuelto

Devuelve la URL de acceso al recurso público.

## Observaciones

Los recursos deben publicarse en servidores frontales. Ejemplo:

```xml
              <%= getImageUrl(content.@["banner-id"]) %>Code HTML généré :http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg
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
