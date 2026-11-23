---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 3%
---
# Cuaderno

Lista de pestañas para mostrar varias páginas.

![Control de Notebook](assets/notebook.3b531a46.png)

## Propiedades

**backColor - string** Color de fondo (btnshadow, blanco).

**nombre - cadena** ID de contenedor.

**padding-left - integer** espacio en píxeles a la izquierda del contenedor.

**padding-right - integer** espacio en píxeles a la derecha del contenedor.

**padding-top - integer** espacio en píxeles por encima del contenedor.

**padding-bottom - integer** espacio en píxeles debajo del contenedor.

**relleno - entero** Espacio en píxeles alrededor del contenedor.

**readOnly - boolean** fuerza al control y a todos sus descendientes a leer solamente.

**style - cadena** sin formato \| abajo \| arriba (predeterminado).

## Observaciones

Cada subelemento representa una página. Ejemplos:

```xml
      <container colspan="2" style="down" type="notebook">
   <container label="Products">
     ...
   </container>

   <container colcount="3" xpath="link">
     ...
   </container>

   <container xpath="linkCollection">
     ...
   </container>
 </container>
```
