---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 6%
---
# DeployTriggerMessageSingle

Publicar el mensaje transaccional en instancias de ejecución. Devuelve verdadero si la publicación se realiza correctamente y falso en caso contrario.

```text
Boolean isSuccess = DeployTriggerMessageSingle ( Number deliveryId, Boolean localPublish )
```

## Parámetros

**deliveryId** ID del envío que se va a implementar

**localPublish** ¿Desea publicar solo en la instancia de control?

## Valor(es) devuelto(s)

**isSuccess** publicación completa

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
