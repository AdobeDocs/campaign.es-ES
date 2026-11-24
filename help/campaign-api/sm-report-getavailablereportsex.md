---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 25%
---
# GetAvailableReportsEx

Recupera la lista de informes sin su historial, teniendo en cuenta las condiciones de ordenación de datos y la numeración de páginas

```text
XML reports = GetAvailableReportsEx ( String activeContext, String schema, String selection, XML where, XML orderBy, Number editionMode, Number lineCount, Number startLine, String locationName )
```

## Parámetros

**activeContext** Contexto activo (selección, global)

Esquema **schema** involucrado

**selección** ID de las entidades seleccionadas, separadas por &#39;,&#39;

**donde** está filtrando el nodo &#39;donde&#39;

**orderBy** está ordenando el nodo &#39;orderBy&#39;

**editionMode** Durante la edición, los informes no publicados también están visibles

**lineCount** número de informes que recopilar

Desplazamiento **startLine** que se aplicará a la numeración de páginas

**locationName**

## Valor(es) devuelto(s)

**informes** Lista de informes elegibles

## Funciones

**Esquema:** [xtk:report](s-xtk-report.md)

**Estático:**

Sí
