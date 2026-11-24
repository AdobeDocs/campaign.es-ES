---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 13%
---
# sqlSelect

Ejecuta una consulta SQL y devuelve el resultado como documento XML.

```text
sqlSelect (format, query [, dataSource ])
```

## Parámetros

**formato** Una cadena separada con comas que describen el formato de los datos esperados como un nombre:type\[:length\] tipo lista docName, \[fieldXPath:type,\]\*

**query** La consulta SQL.

**dataSource**: el origen de datos.

## Valor devuelto

Objeto XML que contiene una lista de elementos para cada línea del resultado de la consulta.

## Observaciones

Ejemplo:

```javascript
var res = sqlSelect("publicUrl,@sstringValue:string",
        "select sstringValue from XtkOption where sname='XtkFileRes_PublicUrl'")
logInfo(res.publicUrl.@sstringValue.toString())
```

```javascript
var xmlRes = sqlSelect("name:string,file:string:64","select relname, relfilenode from  pg_class WHERE relkind='r' AND pg_get_userbyid(relowner)<>'postgres';");
```

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
