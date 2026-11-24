---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%
---
# VPaned

Organiza varios contenedores horizontalmente.

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

Cada subelemento debe ser un contenedor. Cada subcontenedor puede especificar el porcentaje de la anchura total que desea utilizar gracias a la propiedad width-percent. Ejemplo:

```xml
<container type="vpaned">
  <container label="Group 1" width-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" width-percent="75"/>
    <input .../>
  </container>
</container>
```
