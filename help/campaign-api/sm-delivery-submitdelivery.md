---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%
---
# SubmitDelivery

Creación y presentación de un envío a partir de un escenario (desde su nombre interno).

```text
Number deliveryId = SubmitDelivery ( String scenarioName, XML content )
```

## Parámetros

**scenarioName** nombre interno de la plantilla de envíos

**contenido** contenido XML para agregar a la plantilla

## Valor(es) devuelto(s)

**deliveryId** Identificador del nuevo envío (devuelto aunque falle el análisis)

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
