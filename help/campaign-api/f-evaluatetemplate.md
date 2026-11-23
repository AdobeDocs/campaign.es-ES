---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 14%
---
# evaluateTemplate

Evalúa una plantilla de JavaScript (&lt;%= ... %>).

```text
evaluateTemplate (template)
```

## Parámetros

**plantilla**: la plantilla que se va a evaluar.

## Valor devuelto

La cadena después de sustituir las expresiones entre &lt;% y %>.

## Observaciones

Ejemplo:

```javascript
      vars.filename = evaluateTemplate(activity.filename)
```

## Funciones

**Disponible en:**

* Flujo de trabajo
