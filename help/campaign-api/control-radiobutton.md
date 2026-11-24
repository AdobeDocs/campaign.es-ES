---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 2%
---
# RadioButton

Un botón de opción le permite elegir entre varias opciones. Las etiquetas &lt;input> se utilizan para enumerar posibles opciones.

![Control RadioButton](assets/radio.11bc90a8.png)

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**border - string** Cambia el estilo de borde del control (sólido, doble, margen, inicial, ninguno).

**checkValue - string** Valor vinculado a la opción.

**tamaño de fuente - entero** Cambia el tamaño de fuente.

**etiqueta - cadena** Etiqueta asociada.

**nolabel - booleano**: oculta la etiqueta asociada.

**readOnly - boolean** fuerza al control a ser de solo lectura.

## Observaciones

Ejemplo:

```xml
      <input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```
