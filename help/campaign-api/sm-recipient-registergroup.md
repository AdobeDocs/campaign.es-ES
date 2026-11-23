---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 37%
---
# RegisterGroup

Agregar los destinatarios seleccionados a una lista

```text
RegisterGroup ( XML groupList, XML recipientList, Boolean register )
```

## Parámetros

Listas de **groupList**

**recipientList** Lista de destinatarios

**registrar** destinatarios de suscripción/cancelación de suscripción

## Valor(es) devuelto(s)

Ninguna.

## Ejemplo

```javascript
//List
var entity = <entityList><key value="24447964"/>
              <where>
                <condition enabledIf="" expr="@id = 24447964"/>
              </where>
            </entityList>
 
//Recipient
var choice = <choiceList><key value="18995462"/>
              <where>
                <condition enabledIf="" expr="@id = 18995462"/>
              </where>
            </choiceList>
nms.recipient.RegisterGroup(entity,choice,true)
        
```

## Funciones

**Esquema:** [nms:recipient](s-nms-recipient.md)

**Estático:**

Sí
