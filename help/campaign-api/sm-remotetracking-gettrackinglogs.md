---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 15%
---
# GetTrackingLogs

Permite recopilar los registros de seguimiento generados por el servicio de redirección y seguimiento web.

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs ( String instance, String dbId, Number version, String pointer, Number logCount )
```

## Parámetros

**instancia** Identificador corto

**dbId** Identificador de base de datos para el cliente que realiza una entrega

**version** versión del registro de seguimiento

**puntero** Identificador (int64 serializado) del registro desde el cual se deben recuperar los registros.

**logCount** Número de registros que se recuperarán para la solicitud (0 significa valor predeterminado), número de registros devueltos por la respuesta.

## Valor(es) devuelto(s)

**puntero** Identificador (int64 serializado) del registro desde el cual se deben recuperar los registros.

**logCount** Número de registros que se recuperarán para la solicitud (0 significa valor predeterminado), número de registros devueltos por la respuesta.

**registros** registros recuperados

**srvDate** hora GMT del servidor en el momento de la solicitud de recuperación del registro

## Funciones

**Esquema:** [nms:remoteTracking](s-nms-remotetracking.md)

**Estático:**

Sí
