---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# generateRegisterHookScript

Genera el script de extensión que se llamará durante el evento “register” de “appSubscriptionRcp”.

```text
String JSScriptStr = generateRegisterHookScript ( XML additionalXmlNodes )
```

## Parámetros

**additionalXmlNodes** nodos XML que contienen el vínculo entre parámetros adicionales y el campo de asignación de destino.

## Valor(es) devuelto(s)

**JSScriptStr**: script JS que permite vincular parámetros adicionales a los campos en la asignación de destino.

## Funciones

**Esquema:** [nms:mobileApp](s-nms-mobileapp.md)

**Estático:**

Sí
