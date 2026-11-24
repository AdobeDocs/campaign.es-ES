---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 11%
---
# sqlGetMemoOnDataSource

Devuelve el campo Memo resultante de una consulta SQL en un origen de datos.

```text
sqlGetMemoOnDataSource (query, dataSource [, value1, ... ])
```

## Parámetros

**query** La consulta SQL.

**dataSource**: el origen de datos.

**value1, ...** Variables de la consulta SQL.

## Valor devuelto

El campo Memo que coincide con la consulta.

## Observaciones

El parámetro &quot;origen de datos&quot; se define en [sqlExecOnDataSource(query, dataSource, value1, ...)](f-sqlexecondatasource.md) función Las variables opcionales establecidas como parámetros de esta función se definen en [sqlGetString(query, value1, ...)](f-sqlgetstring.md)

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
