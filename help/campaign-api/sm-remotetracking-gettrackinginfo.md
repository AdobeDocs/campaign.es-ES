---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 33%
---
# GetTrackingInfo

Permite a un servidor de redirección remota descargar información sobre una acción de envío.

```text
XML document = GetTrackingInfo ( String instance, String dbId, String deliveryId )
```

## Parámetros

**instancia** Nombre de instancia

**dbId** Identificador de base de datos para el cliente que realiza una entrega

**deliveryId** ID de entrega.

## Valor(es) devuelto(s)

**documento** que contiene la información de seguimiento de este envío

## Funciones

**Esquema:** [nms:remoteTracking](s-nms-remotetracking.md)

**Estático:**

Sí
