---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 58%
---
# trabajo

Trabajos por lotes ejecutados en el servidor de aplicaciones

## Métodos

| Método | Descripción |
| --- | --- |
| [Cancelar](sm-job-cancel.md) | Cancelar un trabajo |
| [CheckIfJobInProcess](sm-job-checkifjobinprocess.md) | Compruebe si el trabajo aún se está ejecutando |
| [Ejecutar](sm-job-execute.md) | Ejecuta un trabajo de forma sincrónica (en este modo, la información de progreso y la cancelación no están disponibles). |
| [Archivos existentes](sm-job-filesexist.md) | Comprueba si los archivos ya existen en el servidor (como archivos o en la tabla de recursos). |
| [GetJobsInProcess](sm-job-getjobsinprocess.md) | Devuelve los trabajos no externos que se están ejecutando |
| [GetStatus](sm-job-getstatus.md) | Obtener información del progreso del procesamiento del trabajo. Advertencia: Esta API no garantiza que se devuelva una lista de entradas de registro únicas (el llamador debe deduplicarlas con su ID ). |
| [TieneAdvertencia](sm-job-haswarning.md) | Consulta si se han generado advertencias o errores para este trabajo |
| [Pause](sm-job-pause.md) | Pausar un trabajo |
| [Enviar](sm-job-submit.md) | Envía un trabajo para un procesamiento asincrónico |
| [SubmitFromModel](sm-job-submitfrommodel.md) | Envía un trabajo desde una plantilla |
| [SubmitSoapCall](sm-job-submitsoapcall.md) | Envía un trabajo para un procesamiento asincrónico |
| [WaitJobCanceled](sm-job-waitjobcancelled.md) | Esperando a que se cancele el trabajo |

## Métodos genéricos

| Método | Descripción |
| --- | --- |
| [crear](f-create.md) | Crea una nueva entidad correspondiente a un esquema determinado. |
| [cargar](f-load.md) | Carga y devuelve una entidad correspondiente a un esquema y una clave determinados. |
| [guardar](m-entity-save.md) | Guarda una entidad en la base de datos. |
