---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 15%
---
# queryWithTypes

Ejecuta una consulta SQL de tipo SELECT con especificación de tipo de columna.

```text
queryWithTypes (command, types [, value1, ... ])
```

## Parámetros

**comando** comando SQL.

**types** tabla que contiene el tipo de columna.

**value1, ...** Variables de comando.

## Valor devuelto

Cursor que permite iterar en el resultado de la consulta.

## Observaciones

Advertencia: a diferencia de lo que se indica en la sección Características, la función queryWithTypes no está disponible en WebApp. La función es idéntica a [query](m-dbengine-query.md), con el tipo de columnas agregado. En la mayoría de los casos, no se utiliza el tipo de columna, ya que se puede inferir automáticamente. Por este motivo, se debe preferir [query](m-dbengine-query.md). Sin embargo, en algunos casos, especialmente con las columnas de tipo de fecha y Oracle, puede ser necesario explicitar el tipo. Los tipos de columna son cadenas de caracteres de la siguiente lista:

* cadena
* datetime
* fecha
* tiempo
* intervalo de tiempo
* doble
* flotante
* booleano
* byte
* corto
* largo
* int64
* nota
* mancha
* vínculo
* clase

Ejemplo:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)",
                     ["long", "string", "datetime"],
                     1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

El operador debe tener derechos de tipo &quot;sql&quot; para utilizar esta función; de lo contrario, se genera una excepción.

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
