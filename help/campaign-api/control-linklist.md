---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 1%
---
# LinkList

Control para editar colecciones.

![control LinkList](assets/linklist.8b71bb0e.png)

## Propiedades

**addButton - booleano** Muestra el botón Agregar. Esta opción solo es efectiva si la opción hideEditButtons está activada.

**backColor - string** Color de fondo (btnshadow, blanco).

**border - string** Cambia el estilo del esquema de control (solid, double, inset, begin, none).

**dblClickAction - string** Nombre del formulario que se abrirá al hacer doble clic.

**delButton - booleano** Muestra el botón Eliminar. Esta opción sólo es efectiva si el botón hideEditButtons está activado.

**enumImage - string** Nombre de la enumeración del sistema utilizada para mostrar la imagen de cada línea.

**tamaño de fuente - entero** Cambia el tamaño de fuente.

**formulario - cadena** formulario para la edición de vínculos.

**hideEditButtons: booleano**: oculta los botones añadir, eliminar y editar.

**img - cadena** imagen.

**etiqueta - cadena** Etiqueta asociada.

**nolabel - booleano** No hay etiqueta delante del control.

**noToolbar - booleano**: oculta la barra de herramientas.

**orderBy - element** Programación de lista.

**readOnly - boolean** fuerza al control a ser de solo lectura.

**sysFilter - element** List filtering.

**toolbarAlign - string** horizontal \| vertical.

**toolbarCaption: cadena** Etiqueta mostrada en la barra de herramientas.

**xpath-link - string** Vínculo de la lista (consulte el ejemplo en grupos).

**xpathIndex - string** El índice de selección se almacenará en la ubicación especificada por esta ruta.

**xpathLinkEdit - string** Vínculo para edición (consulte el ejemplo en grupos).

**zoom - booleano** Autoriza la edición de vínculos.

## Observaciones

Ejemplos:

```xml
      <input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <sysFilter>
    <condition expr="@type=1"/>
  </sysFilter>
</input>

<input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <form label="Add operators">
  <input xpath="." type="linkListChoice" xpath-link="recipient" img="nms:group.bmp">
  <input xpath="@lastName"/>
  <input xpath="@firstName"/>
  </input>
  </form>
</input>

<input type="linklist" xpath="rcpGrpRel" zoom="true" label="Recipients" form="nms:recipient"
       xpath-link="rcpGroup"
       xpathLinkEdit="recipient">
  <input xpath="recipient/@lastName"/>
  <input xpath="recipient/@firstName"/>
  <input xpath="recipient/@email"/>
  <input xpath="recipient/@phone"/>
</input>
```
