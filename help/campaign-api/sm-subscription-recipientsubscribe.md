---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 31%
---
# RecipientSubscribe

Suscribir o cancelar la suscripción de los destinatarios seleccionados a una lista de servicios de información.

```text
XML confirmationIds = RecipientSubscribe ( XML recipientList, XML serviceList, Boolean subscribe, XML sendConfirmation )
```

## Parámetros

**recipientList** Lista de destinatarios

**serviceList**: lista de servicios

**suscribir** suscribir/cancelar la suscripción de destinatarios

**sendConfirmation** Enviar un mensaje de confirmación

## Valor(es) devuelto(s)

**confirmationIds** Lista de ID de confirmación

## Funciones

**Esquema:** [nms:subscription](s-nms-subscription.md)

**Estático:**

Sí
