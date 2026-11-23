---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 13%
---
# Exportar

Generación y exportación de un informe

```text
Export ( String reportName, XML context, String exportFormat, String fileName, Boolean isAdHoc )
```

## Parámetros

**reportName** Nombre interno del informe

**contexto** de ejecución.

**exportFormat** Los valores posibles son: XLS, OOXML\_SS, ODF\_SS, PDF

XLS genera un documento de Excel 94-2003\
 OOXML\_SS genera un documento de Excel 2007\
 ODF\_SS genera un documento abierto

**fileName** Nombre del archivo de salida

**isAdHoc** especifica si la exportación se refiere a un informe ad hoc

## Valor(es) devuelto(s)

Ninguna.

## Funciones

**Esquema:** [xtk:report](s-xtk-report.md)

**Estático:**

Sí
