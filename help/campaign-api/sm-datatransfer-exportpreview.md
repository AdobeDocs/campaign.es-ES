---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 16%
---
# ExportPreview

Calcular la vista previa de la columna del archivo de salida para las primeras líneas de la consulta

```text
[ XML resultColumns, XML resultXML, String resultSQLRequest ] = ExportPreview ( XML dataTransferStep, Number lineCount, Boolean countMode, String calcFieldName )
```

## Parámetros

**dataTransferStep** Paso de transferencia donde se define el campo calculado.

**lineCount** número de líneas que se devolverán

**countMode** modo de recuento de líneas

**calcFieldName** Nombre del campo calculado observado. Si está vacío, es una previsualización global del archivo de salida.

## Valor(es) devuelto(s)

**resultColumns** Devuelve los valores de las columnas del archivo de exportación (line/col/val, line/col/errors).

**resultXML** Devuelve el documento XML de salida de la consulta.

**resultSQLRequest** Devuelve la consulta SQL ejecutada.

## Funciones

**Esquema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Estático:**

Sí
