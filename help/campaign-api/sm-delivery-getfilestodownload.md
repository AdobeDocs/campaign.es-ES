---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# GetFilesToDownload

Devuelve la lista de archivos encontrados en el servidor asociado al envío.

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number deliveryId )
```

## Parámetros

**deliveryId** Identificador de envío

## Valor(es) devuelto(s)

**filesToDownload** Devuelve la lista de archivos que se pueden descargar como elemento \[properties/filesToDownload\]

**filesNotToDownload** Devuelve la lista de archivos que no se pueden descargar como elemento \[properties/filesNotToDownload\]

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
