---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 1%
---
# EdiciónDeDiagrama

Este control se utiliza para editar diagramas como flujos de trabajo o encuestas.

![Control DiagramEdit](assets/diagramedit.d750db7e.png)

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**border - string** Cambia el estilo del esquema de control (solid, double, inset, begin, none).

**etiqueta - cadena** Etiqueta asociada.

**nolabel - booleano** Muestra la etiqueta como una burbuja de ayuda.

**readOnly - boolean** fuerza al control a ser de solo lectura.

## Observaciones

La barra de herramientas se puede personalizar, cada subelemento de este control coincide con los botones adicionales de la barra de herramientas.

```xml
<input type="diagramEdit" xpath=".">
  <input type="separator"/>
  <input img="xtk:properties.png" label="Properties" resetForm="true" prebuildSubForm="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
  <input type="separator"/>
  <input img="nms:prepare.png" label="Publish" checkModify="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
</input>
```

Para obtener más información sobre los botones de la barra de herramientas, consulte la documentación del control SubFormButton.
