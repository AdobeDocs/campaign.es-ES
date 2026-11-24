---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 35%
---
# Ejecutar

Ejecuta un trabajo de forma sincrónica (en este modo, la información de progreso y la cancelación no están disponibles).

```text
String id = job.Execute ( String methodName ) const
```

## Parámetros

**methodName** Nombre del método al que llamar en la entidad

## Valor(es) devuelto(s)

**id** identificador del trabajo creado (el evento devuelto del trabajo ha fallado si se crea en la base de datos)

## Funciones

**Esquema:** [xtk:job](s-xtk-job.md)

**Estático:**

No

**Const:**

Sí

**Solo clave:**

No
