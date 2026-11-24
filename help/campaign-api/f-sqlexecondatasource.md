---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%
---
# sqlExecOnDataSource

Ejecuta un script SQL en un origen de datos.

```text
sqlExecOnDataSource (query, dataSource [, value1, ... ])
```

## Parámetros

**query** La consulta SQL.

**dataSource**: el origen de datos.

**value1, ...** Variables de la consulta SQL.

## Valor devuelto

Número de registros actualizados o insertados en un comando UPDATE o INSERT SQL.

## Observaciones

Los valores autorizados para la fuente de datos pueden ser:

* &quot;&quot; o &quot;predeterminado&quot; señala a la base de datos de Adobe Campaign

* &quot;nms:extAccount:InternalName&quot; señala a un origen de datos definido en las cuentas externas de Adobe Campaign (FDA)

* &quot;name&quot; (nombre de la fuente de datos) apunta a una fuente de datos definida en el archivo de configuración de instancia (config-instance.xml) en el siguiente formulario:

  ```xml
                   <dataStore hosts="*" lang="">
        <dataSource name="datasourcename">
          <dbcnx encrypted="" login="" password=""
                 provider="" server=""/>
        </dataSource>
      </dataStore>
  ```

Ejemplo:

```javascript
sqlExecOnDataSource("UPDATE XtkOption SET sStringValue = $(sz) WHERE sName = $(sz)", oracleExternalDB, 'WdbcOptions_TableSpaceWork_nms:extAccount:' + sExtAccount)
```

Las variables opcionales establecidas como parámetros de esta función se definen en [sqlGetString(query, value1, ...)](f-sqlgetstring.md)

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
