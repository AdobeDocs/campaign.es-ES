---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 4%
---
# workflow

Definiciones de flujos de trabajo

## Métodos

| Método | Descripción |
| --- | --- |
| [Limpieza](sm-workflow-cleanup.md) | Purga el historial de flujo de trabajo. |
| [EliminarResultado](sm-workflow-deleteresult.md) | Borra los resultados de una o más actividades. |
| [Ejecutar](sm-workflow-execute.md) | Ejecuta un flujo de trabajo inmediatamente y espera a que finalice. |
| [EjecutarInstancia](sm-workflow-executeinstance.md) | Ejecuta un flujo de trabajo inmediatamente y espera a que finalice. |
| [GetLogin](sm-workflow-getlogin.md) | Devuelve información de la cuenta de ejecución. |
| [GetValidationParameters](sm-workflow-getvalidationparameters.md) | Devuelve los parámetros de una tarea de flujo de trabajo en curso. |
| [Matar](sm-workflow-kill.md) | Detiene incondicionalmente un flujo de trabajo. |
| [Pause](sm-workflow-pause.md) | Suspende la ejecución de un flujo de trabajo en curso. |
| [PostEvent](sm-workflow-postevent.md) | Genera un evento a partir de cualquier tipo de actividad. |
| [Responder](sm-workflow-reply.md) | Responde a una tarea de tipo de validación en curso. |
| [Restart](sm-workflow-restart.md) | Vincula una parada y un inicio de flujo de trabajo. |
| [ReiniciarTarea](sm-workflow-restarttask.md) | Obliga a reiniciar una o más tareas finalizadas. |
| [SetLogin](sm-workflow-setlogin.md) | Cambia la cuenta de ejecución. |
| [Simular](sm-workflow-simulate.md) | Inicia un flujo de trabajo en modo de simulación. |
| [SimularConParámetros](sm-workflow-simulatewithparameters.md) | Inicia un flujo de trabajo en modo de simulación y le proporciona parámetros. |
| [Provocar](sm-workflow-spawn.md) | Crea una instancia de flujo de trabajo a partir de una plantilla, aplica un parche e inicia este flujo de trabajo. |
| [SpawnWithParameters](sm-workflow-spawnwithparameters.md) | Crea una instancia de flujo de trabajo a partir de una plantilla y, a continuación, invoca el método [StartWithParameters](sm-workflow-startwithparameters.md) en esta instancia. |
| [SpawnWithParametersEx](sm-workflow-spawnwithparametersex.md) | Crea una instancia de flujo de trabajo a partir de un modelo e invoca el método [StartWithParameters](sm-workflow-startwithparameters.md) o [SimulateWithParameters](sm-workflow-simulatewithparameters.md) en esta instancia. |
| [Start](sm-workflow-start.md) | Inicia o reanuda la ejecución de un flujo de trabajo. |
| [StartWithParameters](sm-workflow-startwithparameters.md) | Inicia un flujo de trabajo y le proporciona parámetros. |
| [Stop](sm-workflow-stop.md) | Detiene un flujo de trabajo en curso. |
| [Reactivación](sm-workflow-wakeup.md) | Obliga al procesamiento avanzado de todas las tareas pendientes. |
| [WakeupTask](sm-workflow-wakeuptask.md) | Obliga al procesamiento avanzado de una o varias tareas pendientes. |

## Métodos genéricos

| Método | Descripción |
| --- | --- |
| [crear](f-create.md) | Crea una nueva entidad correspondiente a un esquema determinado. |
| [cargar](f-load.md) | Carga y devuelve una entidad correspondiente a un esquema y una clave determinados. |
| [guardar](m-entity-save.md) | Guarda una entidad en la base de datos. |
