---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 15%
---
# batchDelete

Elimina los registros de una tabla por paquetes.

```text
batchDelete (table, pk [, where ])
```

## Parámetros

**tabla** nombre SQL de la tabla.

**pk** nombre de campo usado como clave principal.

**donde** condición de filtrado de registros SQL.

## Valor devuelto

Ninguna.

## Observaciones

Ejemplo:

```javascript
      engine.batchDelete("NmsRecipient", "iRecipientId", "sName IS NULL")
```

El operador necesita derechos &quot;sql&quot; para utilizar esta función; de lo contrario, se genera una excepción.

## Funciones

**Método de clase:** [DBEngine](c-dbengine.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
