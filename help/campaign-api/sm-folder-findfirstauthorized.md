---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 28%
---
# FindFirstAuthorized

Busque la primera carpeta elegible para el usuario actual, que satisface la condición folderFilter.

```text
XML folderEntity = FindFirstAuthorized ( String folderFilter, Boolean writeAccess, Number orgUnit )
```

## Parámetros

**folderFilter** filtro en carpetas

**writeAccess** La carpeta devuelta debe poder escribirse

**orgUnit** La carpeta devuelta debe ser compatible con la entidad organizativa especificada

## Valor(es) devuelto(s)

**folderEntity** Devuelve la entidad de carpeta asociada (nulo no se encuentra en ninguna carpeta)

## Funciones

**Esquema:** [xtk:folder](s-xtk-folder.md)

**Estático:**

Sí
