---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 20%
---
# generateImgTag

Permite la generación de una etiqueta &lt;img> de HTML basada en un recurso público.

```text
generateImgTag (ID)
```

## Parámetros

**ID** ID de recurso público

## Valor devuelto

Devuelve la etiqueta HTML &lt;img> con las propiedades de la imagen incluidas en la definición del recurso público.

## Observaciones

Los recursos deben publicarse en servidores frontales. Ejemplo:

```xml
              <%= generateImgTag(content.@["banner-id"]) %>Code HTML généré :<img src="http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg" width="800" height="200" alt="My image"/>
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
