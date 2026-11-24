---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 9%
---
# WorkflowTransition (Clase)

Representa una transición de flujo de trabajo.

Una transición es un objeto opaco que se recupera mediante métodos como o y que se utiliza para habilitar la transición de tareas.

Ejemplo:

```text
var done = task.doneTransition() task.postEvent(done) task.setCompleted() return 0
```

## Funciones

**Disponible en:**

* Flujo de trabajo
