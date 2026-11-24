---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%
---
# PostEvent

Genera un evento a partir de cualquier tipo de actividad.

```text
PostEvent ( String workflowId, String activity, String transition, XML parameters, Boolean complete )
```

## Parámetros

**workflowId** identificador o nombre interno del flujo de trabajo.

**actividad** El nombre de la actividad desde la cual comienza el evento

**transición** El nombre de la transición que se va a activar. Si este nombre está vacío, el evento se emitirá en la primera transición válida (los eventos de tipo de caducidad se omiten).

**parameters**: los parámetros del evento en forma de elemento XML. El nombre del elemento debe ser variables. Si no desea pasar una variable, puede utilizar un elemento vacío &lt;variables/> o una cadena vacía &quot;&quot;.

**completado** Todas las tareas pendientes de la actividad especificada han finalizado.

## Valor(es) devuelto(s)

Ninguna.

## Observaciones

* El comando se ejecuta en modo asincrónico y no tiene un efecto inmediato después del retorno del método.
* El flujo de trabajo de destinatario debe iniciarse cuando se invoque este método. Si no se inicia, se escribe un error en el archivo de registro correspondiente.
* Si el flujo de trabajo de destinatario está suspendido cuando se llama al método, el comando se deja en la cola hasta que se reanuda el flujo de trabajo.
* No hay restricciones en la actividad: no es necesario que tenga una tarea en curso o incluso finalizada.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
