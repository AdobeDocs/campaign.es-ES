---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%
---
# sqlExec

Ejecuta un script SQL.

```text
sqlExec (query [, value1, ... ])
```

## Parámetros

**query** La consulta SQL.

**value1, ...** Variables de la consulta SQL.

## Valor devuelto

El número de registros actualizados o insertados en el caso de un comando UPDATE o INSERT SQL.

## Observaciones

Las variables reemplazan los parámetros del comando. El tipo de variable debe coincidir con el parámetro declarado en el comando. Estas variables están disponibles en una declaración de tipo &quot;select&quot; o &quot;update&quot;. Tenemos los siguientes tipos:

* Cadena de $(sz)
* Nota: $(m)
* $(l) long
* $(s) corto(s)
* $(b) byte
* $(d) doble
* $(f) flotante
* $(ts) marca de tiempo
* Fecha de $(dt)
* Hora de $(tm)
* $(dur) tiempo de espera en milisegundos (ms)

Los siguientes parámetros de sustitución (solo válidos para una &quot;actualización&quot;) se sustituyen automáticamente por un valor y no necesitan una variable vinculada.

* $(id) generar un identificador
* $(id:NmsTrackingLogId) generar un identificador mediante una secuencia específica
* $(curdate) fecha y hora actuales

El operador debe tener el derecho &quot;sql&quot; para utilizar esta función; de lo contrario, se genera una excepción. Ejemplo:

```javascript
      var sql4 = "INSERT INTO Reporting (sClientdesc,sClient) values ('" + client.@description.toString() + "','" + client.@clientCode.toString() +"')";
sqlExec(sql4);
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
