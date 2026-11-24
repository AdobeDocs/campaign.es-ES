---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 48%
---
# BuildUpdateOneSchemaDiff

Genera un documento que describe las diferencias entre una tabla de la base de datos física y la descripción lógica de esta tabla.

```text
XML sqlSchemaDiff = BuildUpdateOneSchemaDiff ( String schemaId, Boolean useNamingConventions )
```

## Parámetros

**schemaId** Identificador de esquema

**useNamingConvention** Utilice las convenciones de nomenclatura SQL para calcular las rutas de los campos nuevos.

## Valor(es) devuelto(s)

**sqlSchemaDiff** esquema generado

## Funciones

**Esquema:** [xtk:builder](s-xtk-builder.md)

**Estático:**

Sí
