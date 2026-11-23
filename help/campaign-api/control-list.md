---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 1%
---
# Lista

Lista de memoria.

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**border - string** Cambia el estilo del esquema de control (solid, double, inset, begin, none).

**editable - booleano**: autoriza la edición de listas.

**tamaño de fuente - entero** Cambia el tamaño de fuente.

**formulario - cadena** El formulario en edición.

**img - cadena** Imagen para cada línea.

**etiqueta - cadena** Etiqueta asociada.

**nolabel - booleano** Sin etiqueta.

**notitle - booleano** No muestra títulos de columnas.

**noToolbar - booleano**: oculta la barra de herramientas.

**ordenado - booleano** Autoriza la programación de listas.

**readOnly - boolean** fuerza al control a ser de solo lectura.

**toolbarAlign - string** horizontal \| vertical.

**toolbarCaption: cadena** Etiqueta mostrada en la barra de herramientas.

**zoom - booleano** Muestra el formulario de edición.

**zoomOnAdd - booleano** Abre un formulario cuando se agrega una línea.

**xpathIndex - xpath** El índice de la selección se almacenará en la ubicación especificada por esta ruta.

**xpathSelection - xpath** El nodo donde se almacenará la ruta XPATH para llegar al elemento seleccionado.

## Observaciones

Ejemplo 1:

```xml
      <input type="list" xpath="dataTransferStep" nolabel="true" editable="false"
       zoom="true" form="xtk:exportSource" zoomOnAdd="true" img="xtk:script.bmp">
  <input xpath="@name" colSize="15"/>
  <input xpath="@active" editable="true" colSize="15"/>
</input>
```

Ejemplo 2:

```xml
<input type="list" xpath="operator" zoom="true">
  <input xpath="@name" colSize="15"/>
  <form>
    <input xpath="@name"/>
  </form>
</input>
```
