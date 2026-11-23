---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 41%
---
# Cancelar la suscripción

Cancelar la suscripción de un destinatario de un servicio informativo.

```text
Unsubscribe ( String serviceName, XML recipient )
```

## Parámetros

**serviceName**: lista de nombres de servicios de información (separados por comas)

Destinatario **recipient**

## Valor(es) devuelto(s)

Ninguna.

## Ejemplo

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Unsubscribe("SVC1", recipient)
        
```

## Funciones

**Esquema:** [nms:subscription](s-nms-subscription.md)

**Estático:**

Sí
