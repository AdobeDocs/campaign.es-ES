---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 4%
---
# GetStatus

Obtener información del progreso del procesamiento del trabajo. Advertencia: Esta API no garantiza que se devuelva una lista de entradas de registro únicas (el llamador debe deduplicarlas con su ID ).

```text
[ Number status, XML returnLogs, XML properties ] = GetStatus ( String id, Number lastLogId, Number maxLogCount )
```

## Parámetros

**id** Identificador de trabajo

**lastLogId** Identificador de la última entrada de registro devuelta en la llamada anterior

**maxLogCount** Número máximo de entradas de registro a enviar

## Valor(es) devuelto(s)

**estado** Estado del trabajo

**returnLogs** mensajes de registro

**propiedades** Propiedades (en curso...)

## Funciones

**Esquema:** [xtk:job](s-xtk-job.md)

**Estático:**

Sí
