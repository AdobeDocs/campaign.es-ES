---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 56%
---
# fileRes

Recurso de archivo almacenado en el servidor o en la base de datos

## Métodos

| Método | Descripción |
| --- | --- |
| [PublicaciónDeArchivos](sm-fileres-filepublishing.md) | Publica los recursos públicos en los servidores frontales. |
| [GetPublicFileResURL](sm-fileres-getpublicfileresurl.md) | Obtiene la dirección URL de la carpeta |
| [GetServerFileName](sm-fileres-getserverfilename.md) | Devuelve el nombre del archivo en el servidor después de copiarlo, si es necesario, en la carpeta de carga. |
| [GetURL](sm-fileres-geturl.md) | Obtiene la dirección URL del archivo |
| [CargarPublicación](sm-fileres-postupload.md) | Procesamiento posterior a la carga en función del tipo de almacenamiento definido. |
| [Descarga previa](sm-fileres-predownload.md) | Preparar la descarga de recursos en función del tipo de almacenamiento definido. |
| [PublishIfNeeded](sm-fileres-publishifneeded.md) | Copia el archivo en los servidores de medios si es necesario |
| [PublishIfNeededFromId](sm-fileres-publishifneededfromid.md) | Copia el archivo en los servidores de recursos si es necesario utilizando el ID de recurso |
| [WebPostUpload](sm-fileres-webpostupload.md) | Finalice el almacenamiento del recurso después de la carga (desde una página web) en el servidor en función del tipo de almacenamiento utilizado. Recupera la página de códigos y el tipo de contenido. |

## Métodos genéricos

| Método | Descripción |
| --- | --- |
| [crear](f-create.md) | Crea una nueva entidad correspondiente a un esquema determinado. |
| [cargar](f-load.md) | Carga y devuelve una entidad correspondiente a un esquema y una clave determinados. |
| [guardar](m-entity-save.md) | Guarda una entidad en la base de datos. |
