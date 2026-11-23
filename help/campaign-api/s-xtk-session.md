---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 74%
---
# sesión

Sesiones en el servidor de aplicaciones

## Métodos

| Método | Descripción |
| --- | --- |
| [AplicarReglasDuplicadas](sm-session-applyduplicaterules.md) | Aplica la configuración de la duplicación (incluidos los valores predeterminados) al documento especificado |
| [BearerTokenLogon](sm-session-bearertokenlogon.md) | token de conexión |
| [Cambiar contraseña](sm-session-changepassword.md) | Cambiar la contraseña actual |
| [DeleteCollection](sm-session-deletecollection.md) | Eliminar una lista de entidades basada en una condición |
| [Diferencias](sm-session-diff.md) | Devuelve la versión actual y la versión original de un documento. |
| [Duplicado](sm-session-duplicate.md) | Crea un documento nuevo a partir de un documento de origen |
| [DuplicateTo](sm-session-duplicateto.md) | Duplica un nuevo documento desde un documento de origen en una carpeta determinada |
| [DuplicateWithMappingId](sm-session-duplicatewithmappingid.md) | Duplica un nuevo documento del documento de origen con la asignación de ID |
| [Cifrar](sm-session-encrypt.md) | Cifra la cadena de caracteres con la clave de instancia. |
| [EncryptServerPassword](sm-session-encryptserverpassword.md) | Cifra la cadena de caracteres con la clave del servidor. |
| [FormatDataPolicy](sm-session-formatdatapolicy.md) | Aplica una transformación a la cadena de caracteres según la directiva de datos pasada como parámetro. Deja la cadena sin cambios en caso de error. |
| [MenúsGetActiveApplication](sm-session-getactiveapplicationmenus.md) | Devuelve un documento que contiene los menús de las aplicaciones habilitadas para el inicio de sesión actual |
| [GetCnxInfo](sm-session-getcnxinfo.md) | Recupera información de las conexiones actuales. |
| [GetDefaultEntity](sm-session-getdefaultentity.md) | Devuelve un documento que contiene una entidad vacía con sus valores predeterminados |
| [GetDirtyCacheEntities](sm-session-getdirtycacheentities.md) | Devolver entidades en caché con modificaciones |
| [GetEntityIfMoreRecent](sm-session-getentityifmorerecent.md) | Cargue una entidad si su clave MD5 es diferente de la especificada como parámetro |
| [GetImages](sm-session-getimages.md) | Cargar una lista de imágenes |
| [GetNewIds](sm-session-getnewids.md) | Recopila una lista de identificadores de claves internas para la base de datos. |
| [GetNewIdsEx](sm-session-getnewidsex.md) | Obtener una lista de identificadores únicos de la base de datos, con un nombre de secuencia. |
| [GetOption](sm-session-getoption.md) | Devuelve el valor de una opción almacenada en la base de datos. |
| [GetPkList](sm-session-getpklist.md) | Obtener la lista de identificadores de instancia |
| [GetServerTime](sm-session-getservertime.md) | Devuelve la fecha y la hora del servidor |
| [GetUserInfo](sm-session-getuserinfo.md) | Información sobre el operador actual |
| [HashPassword](sm-session-hashpassword.md) | Hash de una contraseña con la clave del servidor. |
| [Importar colección](sm-session-importcollection.md) | Actualizar una lista de entidades mediante una importación |
| [KillSession](sm-session-killsession.md) | Cierra la sesión especificada |
| [Cargar](sm-session-load.md) | Cargar la entidad |
| [CargarComoTexto](sm-session-loadastext.md) | Recuperar el contenido de la entidad como texto |
| [LoadIfExists](sm-session-loadifexists.md) | Cargue la entidad si existe |
| [Cerrar sesión](sm-session-logoff.md) | Cerrar la sesión actual |
| [Inicio de sesión](sm-session-logon.md) | Abre una sesión |
| [NuevaInstancia](sm-session-newinstance.md) | Creación de un nuevo documento, preinicializado pero no guardado |
| [Quitar](sm-session-remove.md) | Eliminar entidad |
| [ServerShutdown](sm-session-servershutdown.md) | Solicita el cierre del servidor |
| [SetDefaultValues](sm-session-setdefaultvalues.md) | Valores fijos de forma predeterminada en función de xpath |
| [Valores predeterminados](sm-session-setdefaults.md) | Establecer valores predeterminados |
| [TestCnx](sm-session-testcnx.md) | Compruebe la conexión. |
| [Write](sm-session-write.md) | Actualizar una entidad |
| [WriteCollection](sm-session-writecollection.md) | Actualizar una lista de entidades |

## Métodos genéricos

| Método | Descripción |
| --- | --- |
| [crear](f-create.md) | Crea una nueva entidad correspondiente a un esquema determinado. |
| [cargar](f-load.md) | Carga y devuelve una entidad correspondiente a un esquema y una clave determinados. |
| [guardar](m-entity-save.md) | Guarda una entidad en la base de datos. |
