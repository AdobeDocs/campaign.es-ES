---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 38%
---
# LoadExpandedContents

Cargue una lista de componentes para el preprocesamiento con dependencias (bloques de personalización, opciones, objetos de script adicionales, etc.).

```text
XML material = delivery.LoadExpandedContents ( String ids ) const
```

## Parámetros

**ids**: lista de identificadores de componentes separados por comas (p. ej. &#39;option\|NmsServer\_URL\|text,includeView\|UnsubscriptionLink\|html&#39;).

## Valor(es) devuelto(s)

**material** Devuelve el contenido como un elemento &#39;material&#39;.

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

No

**Const:**

Sí

**Solo clave:**

No
