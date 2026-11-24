---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 4%
---
# DBEngine (Clase)

Representa una conexión de base de datos.

Este objeto permite consultar la base de datos y realizar operaciones relacionadas.

La mayoría de los métodos de esta clase requieren derechos &quot;sql&quot;. Si el operador invoca un método y no tiene los derechos adecuados, se genera una excepción. En términos generales, todos los métodos que cambian la base de datos requieren derechos &quot;sql&quot;, mientras que los métodos que simplemente ven información no lo hacen. Consulte la documentación de cada método para averiguar si se requieren o no los derechos.

## Métodos

| Método | Descripción |
| --- | --- |
| [batchDelete](m-dbengine-batchdelete.md) | Elimina los registros de una tabla por paquetes. |
| [eliminar](m-dbengine-dispose.md) | Libera la conexión de todos los recursos vinculados a ella. |
| [ejecutar](m-dbengine-execute.md) | Ejecuta un comando SQL. |
| [exec](m-dbengine-exec.md) | Alias del comando execute. Esta función está obsoleta, use [execute()](m-dbengine-execute.md) |
| [consulta](m-dbengine-query.md) | Ejecuta una consulta SQL de tipo SELECT. |
| [queryWithTypes](m-dbengine-querywithtypes.md) | Ejecuta una consulta SQL de tipo SELECT con especificación de tipo de columna. |
| [comenzar](m-dbengine-begin.md) | Inicia una nueva transacción en la conexión. |
| [confirmar](m-dbengine-commit.md) | Aprueba la transacción en curso en la conexión. |
| [reversión](m-dbengine-rollback.md) | Cancela la transacción en curso en la conexión. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [isOracle](p-dbengine-isoracle.md) | Devuelve true si la base de datos es Oracle. |
| [isDB2](p-dbengine-isdb2.md) | Devuelve verdadero si la base de datos es de tipo DB2. |
| [isMySQL](p-dbengine-ismysql.md) | Devuelve true si la base de datos es del tipo MySQL. |
| [isMSSQL](p-dbengine-ismssql.md) | Devuelve true si la base de datos es SQL Server. |
| [isPostgreSQL](p-dbengine-ispostgresql.md) | Devuelve true si la base de datos es PostgreSQL. |
| [isSybase](p-dbengine-issybase.md) | Devuelve true si la base de datos es Sybase. |
| [isSybaseIQ](p-dbengine-issybaseiq.md) | Devuelve true si la base de datos es Sybase IQ. |
| [isFDA](p-dbengine-isfda.md) | Devuelve true si se tiene acceso a la base de datos a través de FDA. |
| [está roto](p-dbengine-isbroken.md) | Devuelve true si ya no se puede utilizar la conexión. |
| [useUnicodeData](p-dbengine-useunicodedata.md) | Devuelve true si la base de datos contiene datos Unicode. |
| [useNChar](p-dbengine-usenchar.md) | Devuelve true si Adobe Campaign utiliza los campos de tipo NCHAR, NVARCHAR, NCLOB y NTEXT. |

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
