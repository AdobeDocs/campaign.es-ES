---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 4%
---
# consulta

Ejecuta una consulta SQL de tipo SELECT.

```text
query (command [, value1, ... ])
```

## Parámetros

**comando** comando SQL.

**value1, ...** Variables del comando.

## Valor devuelto

Un cursor que le permite iterar en el resultado de la consulta.

## Observaciones

Advertencia: a diferencia de lo que se indica en la sección Características, la función de consulta no está disponible en WebApp. Las variables reemplazan los parámetros del comando. El tipo de variable debe coincidir con el parámetro declarado en el comando. Están disponibles los siguientes tipos:

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
* $(dur) intervalo de tiempo

Los siguientes parámetros de sustitución se sustituyen automáticamente por un valor y no necesitan una variable vinculada.

* $(id) genera un identificador
* $(id:NmsTrackingLogId) genera un identificador gracias a una secuencia específica
* $(curdate) Fecha y hora actuales

La iteración en el cursor se realiza mediante un &quot;para cada uno&quot; y devuelve una tabla para cada línea recuperada. Cada elemento de la tabla coincide con un campo de la consulta y el tipo de elemento depende del tipo de campo. Ejemplo:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)", 1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

En este ejemplo, la fila\[0\] es un número que coincide con iOperatorId, la fila\[1\] es una cadena de caracteres que coincide con sName y la fila\[2\] es una fecha que coincide con tsLastModified. El operador necesita derechos &quot;sql&quot; para utilizar esta función; de lo contrario, se genera una excepción.

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
