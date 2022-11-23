---
title: Perfiles de operador
description: Creación de operadores de administración de ofertas
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: eed3396584940f99a865eef2358887b6bf5c4936
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 37%

---

# Perfiles de operador {#operator-profiles}

Dos tipos de operadores pueden utilizar Campaign Interaction: **Administradores de ofertas** y **Administradores de envío**. Cada uno de ellos tiene permisos y restricciones específicos. Obtenga más información sobre los operadores y permisos de Campaign en [esta página](../start/gs-permissions.md).

* La variable **[!UICONTROL Offer manager]** crea y mantiene ofertas.
* La variable **[!UICONTROL Delivery manager]** aprueba y utiliza ofertas

## Creación de un operador de gestor de ofertas{#offer-manager}

1. Creación de un operador. [Más información](../start/manage-permissions.md#add-users)
1. Vaya a la **[!UICONTROL Groups and named rights]** ventana, haga clic en **[!UICONTROL Add]** y seleccione **[!UICONTROL Offer manager]** grupo.

Se describen los permisos asociados a los administradores de ofertas [here](../start/manage-permissions.md#ootb-productprofiles)

## Creación de un operador Delivery manager {#delivery-manager}

1. Creación de un operador. [Más información](../start/manage-permissions.md#add-users)
1. Vaya a la **[!UICONTROL Groups and named rights]** , haga clic en **[!UICONTROL Add]** y seleccione **[!UICONTROL Delivery manager]** grupo.

Los derechos asignados a los gestores de envío les permiten llevar a cabo las siguientes tareas:

* Mostrar entornos **[!UICONTROL Live]**.
* Mostrar y modificar las categorías de oferta.
* Apruebe ofertas si son sus revisores.

   >[!NOTE]
   >
   >**Administradores de envío** solo puede aprobar una oferta si se han declarado como revisores en la configuración de la oferta.

## Matriz de permisos por operador de interacción {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gestor de ofertas (entorno Design)</strong><br /> </td> 
   <td> <strong>Gestor de ofertas (entorno en directo)</strong><br /> </td> 
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
   <td> <strong>Gestor de envíos (con diseño)</strong><br /> </td> 
   <td> <strong>Gestor de envíos (Live Env.)</strong><br /> </td> 
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
