---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%
---
# Provocar

Crea una instancia de flujo de trabajo a partir de una plantilla, aplica un parche e inicia este flujo de trabajo.

```text
Number instanceId = Spawn ( String workflowId, XML patch )
```

## Parámetros

**workflowId** identificador o nombre interno de la plantilla de flujo de trabajo.

**patch**: elemento XML que debe combinarse con el modelo para obtener la instancia antes de ejecutarla. Ejemplo:

```xml
    <workflow>
      <activities>
        <extern name="notepad">
          <additionnalArgs><![CDATA[c:\xxx.txt]]>
          </additionnalArgs>
        </extern>
      </activities>
    </workflow>
    
```

Este ejemplo reemplaza los argumentos de la actividad &quot;bloc de notas&quot;. Si no desea aplicar este parche, utilice un elemento &lt;workflow/> vacío o una cadena vacía.

## Valor(es) devuelto(s)

**instanceId** identificador de la instancia creada a partir de la plantilla.

## Observaciones

El comando se ejecuta en modo asincrónico y no tiene un efecto inmediato después del retorno del método. El flujo de trabajo se inicia con la cuenta del operador que realiza la llamada.

## Funciones

**Esquema:** [xtk:workflow](s-xtk-workflow.md)

**Estático:**

Sí
