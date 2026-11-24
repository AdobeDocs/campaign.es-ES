---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 3%
---
# CodeEdit

Control para editar el código fuente.

![Control CodeEdit](assets/codeedit.8a744c8b.png)

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**border - string** Cambia el estilo del esquema de control (solid, double, inset, begin, none).

**contentType - string** Idioma del código fuente, utilizado para el color sintáctico y otras opciones vinculadas al idioma. Se admiten los siguientes idiomas:

* predeterminado
* xml
* dtd
* xsl
* html
* txt
* JavaScript
* sql

También se pueden agregar otros lenguajes editando el archivo editor.cfg ubicado en el mismo directorio que nlclient.exe.

**tamaño de fuente - entero** Cambia el tamaño de fuente.

**etiqueta - cadena** Etiqueta asociada.

**nolabel - booleano**: oculta la etiqueta asociada.

**readOnly - boolean** fuerza al control a ser de solo lectura.

**barra de herramientas - booleana** Muestra u oculta la barra de herramientas.

**toolbarAlign - string** Posición de la barra de herramientas: horizontal o vertical.

## Observaciones

Ejemplo:

```xml
<input xpath="code" nolabel="true" type="CodeEdit"
       contentType="JavaScript" toolbar="true" toolbarAlign="horizontal"/>
```
