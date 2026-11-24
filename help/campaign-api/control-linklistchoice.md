---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 2%
---
# LinkListChoice

Elección de una o más entidades.

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**border - string** Cambia el estilo del esquema de control (solid, double, inset, begin, none).

**dblClickAction - string** Nombre del formulario que se abrirá al hacer doble clic.

**tamaño de fuente - entero** Cambia el tamaño de fuente.

**etiqueta - cadena** Etiqueta asociada.

**multiSelection - booleana** Autoriza la selección múltiple

**nolabel - booleano**: oculta la etiqueta asociada.

**readOnly - boolean** fuerza al control a ser de solo lectura.

**serializar - booleano** Guarda la última selección en el archivo configuration.wu del usuario

**xpath-link - string** Vínculo de la lista.

## Observaciones

Ejemplos:

```xml
      <input xpath="." type="linkListChoice" xpath-link="operator">
  <input xpath="[/]"  label="Operator or named right "/>
  <input xpath="@type"/>
  <input xpath="comment"/>
  <sysFilter>
    <condition expr="@type <> 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@type"/>
  </orderBy>
</input>
```
