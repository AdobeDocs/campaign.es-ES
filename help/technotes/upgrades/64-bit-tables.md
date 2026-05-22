---
title: Esquemas de 64 bits
description: Obtenga información acerca de los esquemas de 64 bits en Adobe Campaign v8 para clientes migrados de Campaign Standard
feature: Technote
role: Admin
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
source-git-commit: 25ce962e7c8b6a62fc2c1edb08a78afa839d264e
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 18%

---

# Esquemas de 64 bits {#sixty-four-bit-tables}

Para facilitar la transición de Campaign Standard a Campaign v8, se han cambiado varias tablas de 32 a 64 bits. De hecho, Campaign Standard admite PK de 64 bits en varios esquemas predeterminados, mientras que Campaign v8 admite PK de 32 bits en la mayoría de los esquemas.

## Limitaciones

* Este cambio técnico solo se aplica a los clientes que migran de Campaign Standard.
* La extensión de esquema y &quot;broadlog&quot; no es compatible con 64 bits. Permanecerá en 32 bits.
* Los registros relacionados con las entregas enviadas a los usuarios técnicos no estarán disponibles en Campaign v8.
* Solo se admite PostgreSQL.

## Esquemas modificados

Esta es la lista de esquemas cambiados a 64 bits y sus atributos modificados.

| Nombre del esquema | Nombre del atributo |
|--- |--- |
| nms:broadLogRcp | id |
| nms:trackingLogRcp | id |
| nms:excludeLogRcp | id |
| nms:broadLogVisitor | id |
| nms:trackingLogVisitor | id |
| nms:propositionRcp | interactionId |
| nms:propositionVisitor | interactionId |
| nms:webTrackingLog | id |
| nms:tmpBroadcast | message-id |
| nms:tmpMarketingPressure | message-id |
| nms:tmpBroadcastExclusion | message-id |
| nms:tmpBroadcastPaper | message-id |
| nms:broadLogAppSubRcp | id |
| nms:trackingLogAppSubRcp | id |
| nms:excludeLogAppSubRcp | id |
| nms:webEvent | broadLogSrc-id, broadLogRemkt-id |
| nms:broadLogMid | mktBroadLogId |
| nms:mirrorPageSearch | remoteMessageId |
