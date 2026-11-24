---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 6%
---
# getEventFromTransition

Devuelve el último evento en pasar por una transición determinada.

```text
getEventFromTransition (transitionName)
```

## Parámetros

**transitionName**: el nombre interno de la transición.

## Valor devuelto

El último evento que se ha sometido a una transición determinada o nulo. El objeto corresponde a una entidad del esquema &#39;xtk:workflowEvent&#39;.

## Funciones

**Disponible en:**

* Flujo de trabajo
