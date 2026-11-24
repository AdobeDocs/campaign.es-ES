---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 15%
---
# nodeValue

Valor del nodo. El valor depende del tipo de nodo.

```text
nodeValue
```

## Observaciones

Se puede tener acceso a esta propiedad con permisos de lectura y escritura. Ejemplo para recuperar una línea de asunto y añadirla a los datos adicionales de una actividad de consulta en un flujo de trabajo:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',data), 1, 255)
```

Ejemplo para recuperar una línea de asunto de una actividad de enriquecimiento en un flujo de trabajo:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',[target/data]), 1, 255)
```

## Funciones

**Propiedad de clase:** [DOMNode](c-domnode.md)

**Sólo lectura:**

Sí

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
