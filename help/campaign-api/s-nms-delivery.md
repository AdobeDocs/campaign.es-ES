---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 77%
---
# envío

Este esquema representa una acción de envío o una plantilla.

Una plantilla es una plantilla de envío que incluye todos los parámetros necesarios. Una plantilla de envíos se puede ejecutar manualmente desde la consola del cliente o cuando se produce un evento (iniciado desde el programador o mediante programación desde una llamada de SOAP).

## Métodos

| Método | Descripción |
| --- | --- |
| [AppendDeliveryPart](sm-delivery-appenddeliverypart.md) | Agregar una parte a un envío que se está preparando. |
| [BuildForward](sm-delivery-buildforward.md) | Crea la página HTML. |
| [BuildMirror](sm-delivery-buildmirror.md) | Cree la página espejo HTML. |
| [BuildMirrorEx](sm-delivery-buildmirrorex.md) | Cree la página espejo HTML. |
| [Generar vista previa](sm-delivery-buildpreview.md) | Se ha creado la previsualización de un contenido para el envío o de una línea del archivo de salida (en modo externo). |
| [BuildPreviewFromId](sm-delivery-buildpreviewfromid.md) | Se ha creado la previsualización de un contenido para el envío o de una línea del archivo de salida (en modo externo). |
| [BuildTargetDataSchema](sm-delivery-buildtargetdataschema.md) |  |
| [Entregas de limpieza](sm-delivery-cleanupdeliveries.md) | Especifica que el servidor intermediario debe eliminar determinados envíos. |
| [CollectLogs](sm-delivery-collectlogs.md) | Crea una tabla con todos los mensajes del registro de envíos para una lista de envíos |
| [CrearModelo](sm-delivery-createfrommodel.md) | Creación de un envío a partir de una plantilla (desde su nombre interno). |
| [ImplementarMensajeActivadorÚnico](sm-delivery-deploytriggermessagesingle.md) | Publicar el mensaje transaccional en instancias de ejecución. Devuelve verdadero si la publicación se realiza correctamente y falso en caso contrario. |
| [ImplementarMensajesActivadores](sm-delivery-deploytriggermessages.md) | Publicar los mensajes transaccionales seleccionados en las instancias de ejecución |
| [DiagnosticarHTML](sm-delivery-diagnosehtml.md) | Inicia el diagnóstico del contenido HTML |
| [DispatchImages](sm-delivery-dispatchimages.md) | Indica al servidor de aplicaciones que envíe las imágenes al servidor intermediario. |
| [ComandoExec](sm-delivery-execcommand.md) | Ejecutar un comando en un envío. |
| [EjecutarTrabajo](sm-delivery-executejob.md) | Ejecuta un proceso sincrónico en un envío. |
| [FinalizeMidPreparation](sm-delivery-finalizemidpreparation.md) | Finalizar el análisis de un envío en modo intermediario. |
| [GetDeviceList](sm-delivery-getdevicelist.md) |  |
| [GetDlStatusAndLogs](sm-delivery-getdlstatusandlogs.md) | Recupere los últimos registros del historial y el estado de envío. |
| [GetFilesToDownload](sm-delivery-getfilestodownload.md) | Devuelve la lista de archivos encontrados en el servidor asociado al envío. |
| [GetMidBroadLogs](sm-delivery-getmidbroadlogs.md) | Recupera los registros de envío modificados en último lugar en el modo intermediario. |
| [GetMidDeliveries](sm-delivery-getmiddeliveries.md) | Recupera el estado de los envíos modificados en último lugar en el modo intermediario. |
| [GetMidXtkKey](sm-delivery-getmidxtkkey.md) | Devuelve la clave XTK del servidor intermediario |
| [GetMirrorURL](sm-delivery-getmirrorurl.md) | Obtiene la dirección URL de una página espejo HTML. |
| [GetSeedList](sm-delivery-getseedlist.md) |  |
| [HtmlToText](sm-delivery-htmltotext.md) | Convierte el contenido del HTML en texto sin formato |
| [Publicación de imágenes](sm-delivery-imagepublishing.md) | Realiza el posprocesamiento: mover la imagen a una carpeta especificada y ponerla a disposición en línea |
| [InstallTransactionalMessage](sm-delivery-installtransactionalmessage.md) | Instalar una plantilla de mensaje transaccional en la instancia de ejecución. |
| [InvalidateDeliveryCache](sm-delivery-invalidatedeliverycache.md) | Se debe llamar al final de la preparación del mensaje, excepto para el intermediario (método privado). |
| [LaunchFCP](sm-delivery-launchfcp.md) | Inicia una copia de prueba para un envío |
| [LoadExpandedContents](sm-delivery-loadexpandedcontents.md) | Cargue una lista de componentes para el preprocesamiento con dependencias (bloques de personalización, opciones, objetos de script adicionales, etc.). |
| [Pause](sm-delivery-pause.md) | Suspender un envío. |
| [Reproducir](sm-delivery-play.md) | Iniciar un envío. |
| [Preparar](sm-delivery-prepare.md) | Análisis de envío: segmentación y personalización |
| [PrepareAndStart](sm-delivery-prepareandstart.md) | Analiza el envío y lo ejecuta inmediatamente si no se encuentran errores |
| [PrepareFromId](sm-delivery-preparefromid.md) | Analizar un envío. |
| [PrepareMessage](sm-delivery-preparemessage.md) | Personalización de mensajes |
| [PrepareMessageImpl](sm-delivery-preparemessageimpl.md) | Personalización de mensajes |
| [PrepararMultiparteRelacionado](sm-delivery-preparemultipartrelated.md) | Guarde las imágenes que desea incluir en el correo electrónico en la base de datos |
| [PrepararNotificación](sm-delivery-preparenotification.md) | Analizar una notificación que se añade a una acción de envío existente |
| [PrepararRevisión](sm-delivery-prepareproof.md) | Análisis de envío con vistas a generar una prueba |
| [PrepareTarget](sm-delivery-preparetarget.md) | Recuento y arbitraje del público destinatario del envío |
| [PrepareTargetImpl](sm-delivery-preparetargetimpl.md) | Recuento y arbitraje del público destinatario del envío |
| [PreviewExtraction](sm-delivery-previewextraction.md) | Previsualización del archivo de extracción |
| [PrioritizeLogs](sm-delivery-prioritizelogs.md) | Priorizar el registro de envío para una lista de envíos |
| [PrioritizeTarget](sm-delivery-prioritizetarget.md) | Arbitraje del público destinatario del envío |
| [NotificaciónCola](sm-delivery-queuenotification.md) | Solicitud para poner en cola una notificación que hace referencia a una plantilla de envíos. |
| [RecomputeStats](sm-delivery-recomputestats.md) | Calcular las estadísticas de envío y seguimiento de una acción de envío. |
| [SaveUrlInfo](sm-delivery-saveurlinfo.md) | Guarde las direcciones URL de este envío como plantillas de URL. |
| [Stop](sm-delivery-stop.md) | Detener un envío en curso. |
| [StoreMirrorPageInfo](sm-delivery-storemirrorpageinfo.md) | Añade información para generar páginas espejo para un conjunto de piezas de envío. |
| [StoreMirrorPageInfoEx](sm-delivery-storemirrorpageinfoex.md) | Añade información para generar páginas espejo para un conjunto de piezas de envío. |
| [EnviarEnvío](sm-delivery-submitdelivery.md) | Creación y presentación de un envío a partir de un escenario (desde su nombre interno). |
| [SubmitDeliveryById](sm-delivery-submitdeliverybyid.md) | Crear y enviar un envío desde un escenario (identificado por su nombre interno). |
| [EnviarTrabajo](sm-delivery-submitjob.md) | Presenta un trabajo para un envío de procesamiento asincrónico |
| [SubmitMidSourcing](sm-delivery-submitmidsourcing.md) | Mandar un envío en modo intermediario. |
| [EnviarNotificación](sm-delivery-submitnotification.md) | Crear y enviar una notificación desde un escenario. |
| [UpdateBroadLogs](sm-delivery-updatebroadlogs.md) | Actualizar el estado de los registros de envío, realizar el control de errores y actualizar los contadores de envío. |
| [UpdateCachedDelivery](sm-delivery-updatecacheddelivery.md) | Se debe llamar cada vez que se modifica el envío en la memoria para que otros subprocesos tengan acceso a una versión actualizada (método privado). |
| [UpdateImageConfig](sm-delivery-updateimageconfig.md) | Modifica el nodo imageConfig para tener en cuenta las imágenes que ya están en el servidor. |
| [ValidateWavesDefinition](sm-delivery-validatewavesdefinition.md) | Comprobar la coherencia de la información utilizada en la definición de las olas. |

## Métodos genéricos

| Método | Descripción |
| --- | --- |
| [crear](f-create.md) | Crea una nueva entidad correspondiente a un esquema determinado. |
| [cargar](f-load.md) | Carga y devuelve una entidad correspondiente a un esquema y una clave determinados. |
| [guardar](m-entity-save.md) | Guarda una entidad en la base de datos. |
