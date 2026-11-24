---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 1%
---
# de HP

Organiza varios contenedores verticalmente.

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**nombre - cadena** ID de contenedor.

**padding-left - integer** espacio en píxeles a la izquierda del contenedor.

**padding-right - integer** espacio en píxeles a la derecha del contenedor.

**padding-top - integer** espacio en píxeles por encima del contenedor.

**padding-bottom - integer** espacio en píxeles debajo del contenedor.

**relleno - entero** Espacio en píxeles alrededor del contenedor.

**readOnly - boolean** fuerza al control y a todos sus descendientes a leer solamente.

## Observaciones

Cada subelemento debe ser un contenedor. Cada uno de sus subcontenedores puede especificar el porcentaje de la altura total que desea utilizar gracias a la propiedad height-percent. Ejemplo:

```xml
<container type="hpaned">
  <container label="Group 1" height-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" height-percent="75"/>
    <input .../>
  </container>
</container>
```
