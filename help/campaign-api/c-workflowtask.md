---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 4%
---
# WorkflowTask (Clase)

Estado de una tarea de flujo de trabajo.

Una ⌐`WorkflowTask` es una clase de la que no se pueden crear instancias y para la que sólo hay una instancia accesible en las actividades de flujo de trabajo denominadas `task`.

## Métodos

| Método | Descripción |
| --- | --- |
| [setCompleted](m-workflowtask-setcompleted.md) | Marca la tarea como finalizada. |
| [postEvent](m-workflowtask-postevent.md) | Activa una transición. |
| [setNextProcessingDate](m-workflowtask-setnextprocessingdate.md) | Fuerza la siguiente fecha de procesamiento por la tarea. |
| [doneTransition](m-workflowtask-donetransition.md) | Devuelve la transición &quot;terminada&quot; de la actividad. |
| [errorTransition](m-workflowtask-errortransition.md) | Devuelve la transición de &quot;error&quot; de la actividad. |
| [transitionByType](m-workflowtask-transitionbytype.md) | Devuelve la transición correspondiente al tipo determinado. |
| [transitionByName](m-workflowtask-transitionbyname.md) | Devuelve las transiciones correspondientes al nombre dado. |
| [transiciones](m-workflowtask-transitions.md) | Devuelve la lista de transiciones de la actividad. |
| [espera](m-workflowtask-wait.md) | Espera una señal. |

## Funciones

**Disponible en:**

* Flujo de trabajo
