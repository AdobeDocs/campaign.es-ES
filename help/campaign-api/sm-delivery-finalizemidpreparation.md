---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%
---
# FinalizarPreparaciónIntermedia

Finalizar el análisis de un envío en modo intermediario.

```text
[ Number fatalError, String fatalErrorMsg ] = FinalizeMidPreparation ( Number deliveryId, Number errorCode, XML properties, Boolean retry )
```

## Parámetros

**deliveryId** Identificador de envío

**errorCode** Código de error devuelto por el análisis en la base de datos de marketing (no se usa el código de error de nivel de método para esto)

**propiedades** Propiedades de envío a actualizar

**reintentar** especifica si se trata de un reintento para la llamada al método.

## Valor(es) devuelto(s)

**fatalError** devuelve un código de error que impide que el llamador realice retiradas. De lo contrario, el error puede ser temporal.

**fatalErrorMsg** Mensaje de error asociado con el código de error &quot;fatalError&quot;.

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
