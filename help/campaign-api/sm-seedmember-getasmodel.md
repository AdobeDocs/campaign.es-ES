---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# getAsModel

```text
XML parentOut = getAsModel ( String refIdName, Number refIdValue, XML selection, XML parentIn )
```

## Parámetros

**refIdName** Atributo que contiene el identificador de la entidad que se va a asociar (p. ej. &#39;delivery-id&#39;)

**refIdValue** Identificador de la entidad que se va a asociar (valor de &#39;refIdName&#39;)

**selection** elemento que contiene los identificadores de plantilla seleccionados

**parentIn** elemento que contiene las direcciones semilla existentes

## Valor(es) devuelto(s)

**parentOut** Devuelve el elemento con las nuevas plantillas agregadas

## Funciones

**Esquema:** [nms:seedMember](s-nms-seedmember.md)

**Estático:**

Sí
