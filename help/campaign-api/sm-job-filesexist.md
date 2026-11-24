---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 33%
---
# FilesExist

Comprueba si los archivos ya existen en el servidor (como archivos o en la tabla de recursos).

```text
XML exist = FilesExist ( XML files )
```

## Parámetros

**archivos** Lista de archivos (@name) y sus claves MD5 (@md5) y Boolean que indica si puede ser un recurso (@checkResource).

## Valor(es) devuelto(s)

**existe** Lista de resultados (@md5 y @exists)

## Funciones

**Esquema:** [xtk:job](s-xtk-job.md)

**Estático:**

Sí
