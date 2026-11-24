---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 17%
---
# SubmitFromModel

Envía un trabajo desde una plantilla

```text
Number jobId = SubmitFromModel ( String schema, String where, String methodName, XML diff, Boolean async )
```

## Parámetros

**esquema** esquema de plantilla de trabajo

**donde** expresión de selección de plantilla

**methodName** Nombre del método al que llamar

**diff** contenido XML para agregar a la plantilla

**async** Realizar un envío asincrónico del trabajo

## Valor(es) devuelto(s)

**jobId** identificador del trabajo que se acaba de crear

## Funciones

**Esquema:** [xtk:job](s-xtk-job.md)

**Estático:**

Sí
