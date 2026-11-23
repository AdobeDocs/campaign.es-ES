---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 41%
---
# BuildUpdateSchemaDiff

Genera un documento que describe las diferencias entre la estructura real de la base de datos y su descripción lógica.

```text
XML sqlSchemaDiff = BuildUpdateSchemaDiff ( XML parameters, Boolean useNamingConventions )
```

## Parámetros

**parámetros** Parámetros de actualización

**useNamingConvention** Utilice las convenciones de nomenclatura SQL para calcular las rutas de los campos nuevos.

## Valor(es) devuelto(s)

**sqlSchemaDiff** esquema generado

## Funciones

**Esquema:** [xtk:builder](s-xtk-builder.md)

**Estático:**

Sí
