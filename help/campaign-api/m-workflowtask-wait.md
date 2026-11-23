---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 2%
---
# espera

Espera una señal.

```text
wait (timeout)
```

## Parámetros

**tiempo de espera** Tiempo de espera en milisegundos.

## Valor devuelto

Un valor booleano a true si se recibe una señal antes del vencimiento del tiempo de espera.

## Observaciones

La señal es emitida por los métodos SOAP [Wakeup](sm-workflow-wakeup.md) y [WakeupTask](sm-workflow-wakeuptask.md). El protocolo utilizado (UDP) no garantiza la recepción del mensaje. Esta señal solo es útil para ejecutar una operación más rápido. Advertencia: Esta señal nunca se recibirá en un subflujo de trabajo. Ejemplo: Este es un ejemplo típico de uso: un bucle procesa operaciones procedentes de una cola (poll()) y luego espera una determinada cantidad de tiempo entre cada operación. Se agrega un retraso adicional para forzar la pasivación del flujo de trabajo.

```javascript
var lifetime = 30 * 60 * 1000 // 30 minutes
var frequency = 30 * 1000 // 30 seconds
var start = new Date().getTime()
while( new Date().getTime() - start < lifetime )
{
  poll()
  task.wait(frequency)
}
 
```

## Funciones

**Método de clase:** [WorkflowTask](c-workflowtask.md)

**Disponible en:**

* Flujo de trabajo
