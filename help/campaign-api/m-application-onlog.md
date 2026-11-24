---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 6%
---
# onLog

Agrega o elimina una función de interceptación para los mensajes escritos en el historial

```text
onLog ( [function ])
```

## Parámetros

**función** Función de interceptación que se va a agregar. Si se omite este parámetro, se elimina la función agregada más recientemente.

## Valor devuelto

Ninguna.

## Observaciones

Primero se llama a la función agregada más recientemente. La función toma un objeto con las siguientes propiedades como argumento:

* type (Number) - El tipo de mensaje (0=error, 1=advertencia, 2=información, 3=estado, 4=detallado)
* code (Number) - El código de error (0 si no es un error)
* object (String): objeto vinculado al mensaje (sin usar)
* message (String): El mensaje

La función debe devolver un valor booleano. El valor true impide que las siguientes funciones de interceptación reciban el mensaje. La función está protegida contra la reentrada: no interceptará los mensajes que escribió a la propia revista. Ejemplo:

```javascript
var file = new File("c:/temp/log.txt")
file.open("w")

// Add a new log handler
application.onLog(function(log) {
  file.writeln(log.type.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the log handler
application.onLog()

// This message won't be caught
logInfo("Finished.")

file.close()
```

## Funciones

**Método de clase:** [Aplicación](c-application.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
