---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# SubFormLink

Vínculo que abre un subformulario.

![Control SubFormLink](assets/urlbutton.d1cf6f42.png)

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**border - string** Cambia el estilo del esquema de control (solid, double, inset, begin, none).

**discardReadOnly - cadena** Evita la propagación de la propiedad &quot;solo lectura&quot; al subformulario.

**tamaño de fuente - entero** Cambia el tamaño de fuente.

**img - cadena** Imagen asociada.

**etiqueta - cadena** Etiqueta de botón.

**nolabel - string** Permite alinear el control con la columna de etiqueta.

**prebuildSubForm: string** Inicializa el subformulario al crear el control. Esta opción está activada de forma predeterminada, pero se puede desactivar para acelerar la visualización inicial.

## Observaciones

Ejemplo:

```xml
      <input type="subformlink" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
