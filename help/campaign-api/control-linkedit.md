---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# LinkEdit

Control para editar vínculos.

![Control LinkEdit](assets/linkedit.7cb7bf14.png)

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**border - string** Cambia el estilo del esquema de control (solid, double, inset, begin, none).

**choiceButton - booleano**: oculta o muestra el botón de opción (oculto de forma predeterminada).

**computeStringExpr - cadena** Expresión de campo calculado.

**computestringKey - string** Actualiza la cadena calculada en lugar de la clave externa.

**computeStringAlias - cadena** Alias de cadena calculado.

**createMode - string** Crea el vínculo si no existe (ninguno, en línea), con el modo de edición predeterminado.

**externalKey - boolean** utiliza la clave externa.

**tamaño de fuente - entero** Cambia el tamaño de fuente.

**formulario - cadena**: fuerza el formulario de edición de vínculos.

**etiqueta - cadena** Etiqueta asociada.

**loadEntityOnChange - boolean** Vuelve a cargar la entidad cuando cambia el vínculo.

**obligatorio - booleano** Deniega valores vacíos.

**noAutoComplete - booleano** Deshabilita el modo de finalización automática.

**noEdition - booleano** El vínculo no se puede modificar.

**nolabel - booleano**: oculta la etiqueta asociada.

**notifyPathList - string** Lista de XPath separados de los elementos vinculados por comas para cargar en el contexto.

**noTransaction - boolean** Deshabilita el modo transaccional.

**noZoom - booleano**: no hay formulario de edición de vínculos.

**orderBy - element** Programación de opciones.

**readOnly - boolean** fuerza al control a ser de solo lectura.

**obligatorio - booleano** El campo es obligatorio.

**schema - string** Esquema del vínculo.

**serializar - booleano** Guarda la última selección en la configuración del usuario.

**sysFilter - element**: limitación de opciones.

**xpathMandatory - string** Ruta a una propiedad booleana que indica si el vínculo puede estar vacío o no.

## Observaciones

Ejemplos:

```xml
<input xpath="operator">
  <sysFilter>
    <condition expr="@type= 1/>
  </sysFilter>
  <orderBy>
    <node expr="@name"/>
  </orderBy>
</input>

<input xpath="/tmp/recipient" type="linkEdit" label="Recipient"
       schema="nms:recipient">
```
