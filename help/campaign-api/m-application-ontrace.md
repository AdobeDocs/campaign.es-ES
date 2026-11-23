---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 9%
---
# onTrace

Agrega o elimina una función de interceptación de mensajes de seguimiento.

```text
onTrace ( [function ])
```

## Parámetros

**función** Función de interceptación que se va a agregar. Si se omite este parámetro, se elimina la función agregada más recientemente.

## Valor devuelto

Ninguna.

## Observaciones

La función toma un objeto con las siguientes propiedades como argumento:

* gravity (String): La gravedad del mensaje (&quot;error&quot;, &quot;advertencia&quot;, &quot;información&quot;, &quot;estado&quot;, &quot;detallado&quot;)
* type (String): El tipo de mensaje (&quot;log&quot;, &quot;wdbc&quot;, etc.)
* message (String): El mensaje

La función está protegida contra la reentrada: no interceptará los mensajes de seguimiento que haya creado. Ejemplo:

```javascript
var file = new File("c:/temp/trace.txt")
file.open("w")

// Add a new trace handler
application.onTrace(function(log) {
  file.writeln(log.gravity.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the trace handler
application.onTrace()

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
