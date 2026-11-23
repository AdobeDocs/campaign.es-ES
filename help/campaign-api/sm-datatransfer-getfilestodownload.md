---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 28%
---
# GetFilesToDownload

Devuelve la lista de archivos utilizados por esta transferencia y encontrados en el servidor

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number jobId )
```

## Parámetros

**jobId** Identificador de transferencia

## Valor(es) devuelto(s)

**filesToDownload** Devuelve la lista de archivos que se pueden descargar como elemento \[dataTransfer/properties/filesToDownload\]

**filesNotToDownload** Devuelve la lista de archivos que no se pueden descargar como elemento \[dataTransfer/properties/filesNotToDownload\]

## Funciones

**Esquema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Estático:**

Sí
