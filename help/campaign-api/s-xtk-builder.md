---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 73%
---
# constructor

Servicios de generación del servidor de aplicaciones

## Métodos

| Método | Descripción |
| --- | --- |
| [ÁrbolDeNavegaciónDeSalidaDeCompilación](sm-builder-buildoutputnavtree.md) | Combine las definiciones de árbol de navegación que se encuentran en la base de datos con la que se proporciona en el parámetro. |
| [BuildOutputSchema](sm-builder-buildoutputschema.md) | Genera un esquema a partir de un esquema de origen. |
| [EsquemaDeCompilación](sm-builder-buildschema.md) | Genera un esquema a partir de un esquema de origen. |
| [BuildSchemaFromId](sm-builder-buildschemafromid.md) | Genera un esquema a partir de un identificador de esquema de origen. |
| [BuildSqlSchemaDiff](sm-builder-buildsqlschemadiff.md) | Genera un documento que describe las diferencias entre la estructura real de la base de datos y su descripción lógica. |
| [BuildUpdateOneSchemaDiff](sm-builder-buildupdateoneschemadiff.md) | Genera un documento que describe las diferencias entre una tabla de la base de datos física y la descripción lógica de esta tabla. |
| [BuildUpdateSchemaDiff](sm-builder-buildupdateschemadiff.md) | Genera un documento que describe las diferencias entre la estructura real de la base de datos y su descripción lógica. |
| [CheckTableExists](sm-builder-checktableexists.md) | Verifica si existe una tabla en la base de datos |
| [Crear](sm-builder-createdb.md) | Crear base de datos |
| [EvaluarJavaScript](sm-builder-evaluatejavascript.md) | Evaluación del código JavaScript. |
| [EvaluarPlantillaJavaScript](sm-builder-evaluatejavascripttemplate.md) | Evaluación de plantillas JavaScript (JST). |
| [ExecSql](sm-builder-execsql.md) | Ejecutar una instrucción SQL |
| [ExecSqlScript](sm-builder-execsqlscript.md) | Ejecutar una secuencia de comandos SQL |
| [GenCreateDbDDL](sm-builder-gencreatedbddl.md) | Genera el script SQL utilizado para crear la estructura de la base de datos. |
| [GenCreateOrUpdateSchemaSequenceDDL](sm-builder-gencreateorupdateschemasequenceddl.md) | Genera el script SQL utilizado para crear o actualizar la secuencia de esquema autoPk |
| [GenerateNavTree](sm-builder-generatenavtree.md) | Combine todas las definiciones del árbol de navegación y guarde el resultado como &#39;xtk:merged&#39;. |
| [GenerateSchema](sm-builder-generateschema.md) | Genere el código de esquema utilizando parámetros de alto nivel. |
| [GetDbParams](sm-builder-getdbparams.md) | Recupera los parámetros actuales de la fuente de datos. |
| [GetDefaultNamespace](sm-builder-getdefaultnamespace.md) | Recuperar el espacio de nombres predeterminado. |
| [InstallPackage](sm-builder-installpackage.md) | Instale un paquete. |
| [InstallPackageImpl](sm-builder-installpackageimpl.md) | Instalación de un paquete (método interno, no utilizar). |
| [InstallVendorPackages](sm-builder-installvendorpackages.md) | Instale uno o más paquetes estándar. |
| [RemoveSchemaLinkRef](sm-builder-removeschemalinkref.md) | Elimina el esquema y los vínculos inversos que hacen referencia. |
| [ResolvePackageReferences](sm-builder-resolvepackagereferences.md) | Resuelve dependencias en el paquete |
| [UpdateDb](sm-builder-updatedb.md) | Actualización de la estructura de la base de datos. |
| [ActualizarEsquemaDeBaseDeDatos](sm-builder-updateschemafromdatabase.md) | Actualice el esquema en función de su representación física en la base de datos. |
| [UpdateTempSchemasFromDatabase](sm-builder-updatetempschemasfromdatabase.md) | Actualiza una colección de esquemas en función de su representación física en la base de datos. |

## Métodos genéricos

| Método | Descripción |
| --- | --- |
| [crear](f-create.md) | Crea una nueva entidad correspondiente a un esquema determinado. |
| [cargar](f-load.md) | Carga y devuelve una entidad correspondiente a un esquema y una clave determinados. |
| [guardar](m-entity-save.md) | Guarda una entidad en la base de datos. |
