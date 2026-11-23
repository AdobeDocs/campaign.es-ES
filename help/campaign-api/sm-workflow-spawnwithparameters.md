---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%
---
# SpawnWithParameters

Crea una instancia de flujo de trabajo a partir de una plantilla y, a continuación, invoca el método [StartWithParameters](sm-workflow-startwithparameters.md) en esta instancia.

```text
Number instanceId = SpawnWithParameters ( String workflowId, XML parameters )
```

## Parámetros

**workflowId** identificador o nombre interno de la plantilla de flujo de trabajo.

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

**instanceId** identificador de la instancia creada a partir de la plantilla.

## Observaciones

El comando se ejecuta en modo asincrónico y no tiene un efecto inmediato después del retorno del método. El flujo de trabajo se inicia con la cuenta de los operadores de llamada, excepto si un inicio de sesión específico está vinculado a la plantilla de la tabla de inicio de sesión del flujo de trabajo, en cuyo caso se utiliza este inicio de sesión.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
