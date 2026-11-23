---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# Suscribirse

Crear o actualizar una suscripción de destinatario a un servicio informativo

```text
Subscribe ( String serviceName, XML recipient, Boolean create )
```

## Parámetros

**serviceName**: lista de nombres de servicios de información (separados por comas)

**destinatario** destinatario para registrar y, opcionalmente, para crear

**crear** Crear destinatario si no existe

## Valor(es) devuelto(s)

Ninguna.

## Ejemplo

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Subscribe("SVC1", recipient, false)
        
```

## Funciones

**Esquema:** [nms:subscription](s-nms-subscription.md)

**Estático:**

Sí
