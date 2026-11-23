---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 4%
---
# SimulateWithParameters

Inicia un flujo de trabajo en modo de simulación y le proporciona parámetros.

```text
SimulateWithParameters ( String workflowId, XML parameters )
```

## Parámetros

**workflowId** identificador o nombre interno del flujo de trabajo.

**parameters** parámetros para pasar a la instancia. Estos parámetros se convertirán en las variables de instancia del flujo de trabajo. Este argumento es un elemento XML cuyo nombre debe ser variables y solo puede incluir atributos. Ejemplo:

```xml
<variables foo="abc" bar="def">
```

Los scripts de JavaScript dentro del flujo de trabajo pueden acceder a estas variables desde el objeto instance.vars:

```javascript
    var foo = instance.vars.foo   // "abc"
    var bar = instance.vars.bar   // "def"
            
```

## Valor(es) devuelto(s)

Ninguna.

## Observaciones

El comando se ejecuta de forma asincrónica, no tiene efecto inmediato después del retorno del método.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
