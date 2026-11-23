---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# SubmitMidSourcing

Mandar un envío en modo intermediario.

```text
[ Number remoteId, Number remoteMatchId ] = SubmitMidSourcing ( XML delivery, XML routingMatch, String folderName )
```

## Parámetros

**delivery** documento que representa el envío.

**routingMatch** ya no se utiliza

**folderName** Nombre de carpeta completo (en la base de datos del remitente).

## Valor(es) devuelto(s)

**remoteId** identificador del envío en la base de datos del receptor.

**remoteMatchId** ya no se usa

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
