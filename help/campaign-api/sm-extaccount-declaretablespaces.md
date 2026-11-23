---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 39%
---
# DeclareTableSpaces

Declara las opciones, necesarias para utilizar tablespaces específicos en la base de datos remota a la que se puede acceder a través de la cuenta externa, en la base de datos Adobe Campaign.

```text
DeclareTableSpaces ( String extAccountId, String tableSpace, String tableSpaceIndex )
```

## Parámetros

**extAccountId** Nombre interno o clave principal de la cuenta externa

**tableSpace** Nombre del tablespace a utilizar para las tablas de trabajo remoto

**tableSpaceIndex** Nombre del tablespace a utilizar para los índices

## Valor(es) devuelto(s)

Ninguna.

## Funciones

**Esquema:** [nms:extAccount](s-nms-extaccount.md)

**Estático:**

Sí
