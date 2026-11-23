---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%
---
# SubFormButton

Botón que abre un subformulario.

![Control SubFormButton](assets/button.f0aea09a.png)

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**border - string** Cambia el estilo del esquema de control (solid, double, inset, begin, none).

**discardReadOnly - cadena** Evita la propagación de la propiedad &quot;solo lectura&quot; al subformulario.

**tamaño de fuente - entero** Cambia el tamaño de fuente.

**img - cadena** Imagen asociada.

**etiqueta - cadena** Etiqueta del botón.

**nolabel - string** Permite alinear el control en la columna de etiqueta.

**prebuildSubForm: string** Inicializa el subformulario en la creación de controles. Esta opción está habilitada de forma predeterminada, pero se puede deshabilitar para acelerar la visualización inicial.

**obligatorio - booleano** El campo es obligatorio.

## Observaciones

Ejemplo:

```xml
      <input type="subformbutton" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
