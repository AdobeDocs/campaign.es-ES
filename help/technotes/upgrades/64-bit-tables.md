---
title: Esquemas de 64 bits
description: Obtenga información acerca de los esquemas de 64 bits en Adobe Campaign v8 para clientes migrados de Campaign Standard
feature: Technote
role: Admin
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: ab81f6c3-9317-564f-af92-6670a8784294
    internal-label: Technote
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
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
