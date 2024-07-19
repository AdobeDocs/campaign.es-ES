---
title: Perfiles de operadores
description: Creación de operadores de Administración de ofertas
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 35%

---

# Perfiles de operadores {#operator-profiles}

Dos tipos de operadores pueden usar la interacción de campaña: **Administradores de ofertas** y **Administradores de envíos**. Cada uno de ellos tiene permisos y restricciones específicos. Obtenga más información acerca de los operadores y permisos de Campaign en [esta página](../start/gs-permissions.md).

* **[!UICONTROL Offer manager]** crea y mantiene ofertas.
* **[!UICONTROL Delivery manager]** aprueba y utiliza ofertas

## Creación de un operador de Offer manager{#offer-manager}

1. Cree un operador. [Más información](../start/manage-permissions.md#add-users)
1. Vaya a la ventana **[!UICONTROL Groups and named rights]**, haga clic en **[!UICONTROL Add]** y seleccione el grupo **[!UICONTROL Offer manager]**.

Los permisos asociados a los administradores de ofertas se describen [aquí](../start/manage-permissions.md#ootb-productprofiles)

## Creación de un operador de Delivery manager {#delivery-manager}

1. Cree un operador. [Más información](../start/manage-permissions.md#add-users)
1. Vaya a la ficha **[!UICONTROL Groups and named rights]**, haga clic en **[!UICONTROL Add]** y seleccione el grupo **[!UICONTROL Delivery manager]**.

Los derechos asignados al administrador de entregas permiten realizar las siguientes tareas:

* Mostrar entornos **[!UICONTROL Live]**.
* Mostrar y modificar las categorías de oferta.
* Aprobar ofertas si son sus revisores.

  >[!NOTE]
  >
  >**Los administradores de envío** solo pueden aprobar una oferta si se han declarado como revisores en la configuración de la oferta.

## Matriz de permisos por operador de interacción {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Administrador de ofertas (entorno de diseño)</strong><br /> </td> 
   <td> <strong>Administrador de ofertas (entorno en vivo)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nivel de estructura de árbol</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Ofertas editadas/Ofertas en directo<br /> </td> 
   <td> Lectura/Escritura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatario - Entorno<br /> </td> 
   <td> Lectura/Escritura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Administración<br /> </td> 
   <td> Lectura/Escritura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Espacios<br /> </td> 
   <td> Lectura/Escritura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> filtros de oferta predefinidos<br /> </td> 
   <td> Lectura/Escritura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipología<br /> </td> 
   <td> Lectura/Escritura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Reglas de tipología<br /> </td> 
   <td> Lectura/Escritura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Catálogo de ofertas<br /> </td> 
   <td> Lectura/Escritura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoría de oferta<br /> </td> 
   <td> Lectura/Escritura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gestor de envíos (versión de diseño)</strong><br /> </td> 
   <td> <strong>Gestor de envíos (versión activa)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nivel de estructura de árbol</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Ofertas editadas/Ofertas en directo<br /> </td> 
   <td> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatario - Entorno<br /> </td> 
   <td> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Administración<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Espacios<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> filtros de oferta predefinidos<br /> </td> 
   <td> Lectura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipología<br /> </td> 
   <td> Lectura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Reglas de tipología<br /> </td> 
   <td> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Catálogo de ofertas<br /> </td> 
   <td> Lectura<br /> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoría de oferta<br /> </td> 
   <td> </td> 
   <td> Lectura<br /> </td> 
  </tr> 
 </tbody> 
</table>
