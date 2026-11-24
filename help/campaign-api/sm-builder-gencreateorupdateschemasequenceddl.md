---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 44%
---
# GenCreateOrUpdateSchemaSequenceDDL

Genera el script SQL utilizado para crear o actualizar la secuencia de esquema autoPk

```text
String sqlDDL = GenCreateOrUpdateSchemaSequenceDDL ( String schemaId, String newSequence, String oldSequence )
```

## Parámetros

**schemaId** Identificador de esquema

**nuevaSecuencia** Nueva secuencia

**oldSequence** secuencia antigua

## Valor(es) devuelto(s)

**sqlDDL** script SQL

## Funciones

**Esquema:** [xtk:builder](s-xtk-builder.md)

**Estático:**

Sí
