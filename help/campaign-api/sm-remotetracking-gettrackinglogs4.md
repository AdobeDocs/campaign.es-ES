---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 18%
---
# GetTrackingLogs4

Permite recuperar los registros de seguimiento generados por el servidor de redirección remota y seguimiento web, utilizando un formato de entrada de 4.00.

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs4 ( String instance, String dbId, String pointer, Number logCount )
```

## Parámetros

**instancia** Identificador corto

**dbId** Identificador de base de datos para el cliente que realiza una entrega

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
