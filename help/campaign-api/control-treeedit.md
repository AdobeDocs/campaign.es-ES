---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%
---
# EdiciónDeÁrbol

Control para ver y editar varios valores agrupados en distintas categorías.

![Control TreeEdit](assets/treeedit.253f1374.png)

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**border - string** Cambia el estilo del esquema de control (solid, double, inset, begin, none).

**editable - string** Autoriza la modificación (verdadero de forma predeterminada).

**tamaño de fuente - entero** Cambia el tamaño de fuente.

**etiqueta - cadena** Etiqueta asociada.

**noImage - string** Oculta las imágenes de los elementos de la lista.

**nolabel - booleano**: oculta la etiqueta asociada.

**readOnly - boolean** fuerza al control a ser de solo lectura.

## Observaciones

Propiedades de los subelementos

* visibleIf: una condición XTK para mostrar u ocultar el elemento.
* label: etiqueta del elemento.
* exprLabel: etiqueta del elemento en forma de expresión.
* xpath: XPath del elemento.
* img: imagen del elemento.

Propiedades de los subelementos de entrada

* editable: Valor editable. El valor predeterminado se hereda del elemento raíz.

Propiedades de los subelementos de contenedor

* contraído: true\|false Muestra u oculta subelementos.

Ejemplo:

```xml
<input nolabel="true" type="treeEdit">
  <container label="Text fields">
    <input xpath="@text1"/>
    <input xpath="@text2"/>
    <input xpath="@text3"/>
    <input xpath="@text4"/>
    <input xpath="@text5"/>
  </container>
  <container label="Boolean fields">
    <input xpath="@boolean1"/>
    <input xpath="@boolean2"/>
    <input xpath="@boolean3"/>
  </container>
</input>
    
```
