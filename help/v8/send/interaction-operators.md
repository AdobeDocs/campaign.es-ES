---
title: Operadores de interacción de Campaign
description: Creación de operadores de administración de ofertas
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: bda1fc37181396d295ee23a7161053d839d9cfc7
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 37%

---

# Perfiles de operador {#operator-profiles}

Dos tipos de operadores pueden utilizar Campaign Interaction: **Administradores de ofertas** y **Administradores de envío**. Cada uno de ellos tiene permisos y restricciones específicos. Obtenga más información sobre los operadores y permisos de Campaign en [esta página](../start/permissions.md).

* El **[!UICONTROL Offer manager]** crea y mantiene ofertas.
* El **[!UICONTROL Delivery manager]** aprueba y utiliza ofertas

## Creación de un operador de gestor de ofertas{#offer-manager}

1. Creación de un nuevo operador.

   ↗️ Los pasos para crear un operador en Campaign se detallan en [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vaya a la ventana **[!UICONTROL Groups and named rights]**, haga clic en **[!UICONTROL Add]** y seleccione el grupo **[!UICONTROL Offer manager]**.

Los derechos asignados al Gestor de ofertas permiten realizar las siguientes tareas:

* Modificar entornos **[!UICONTROL Design]**.
* Ver entornos **[!UICONTROL Live]**.
* Configurar funciones de administración (espacios predefinidos y filtros).
* Cree y modifique categorías.
* Cree ofertas.
* Configurar la idoneidad de la oferta.
* Aprobar ofertas.

Tenga en cuenta que si se utilizan ofertas en un flujo de trabajo, el operador debe agregarse al grupo de operadores **[!UICONTROL Administrator]** o **[!UICONTROL Offer managers]** para ejecutar el flujo de trabajo.

>[!NOTE]
>
>**Los** administradores de ofertas solo pueden aprobar una oferta si no se especifica ningún revisor o si se han declarado como revisores en la plantilla de oferta.

## Creación de un operador Delivery manager {#delivery-manager}

1. Creación de un nuevo operador.

   ↗️ Los pasos para crear un operador en Campaign se detallan en [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vaya a la ventana **[!UICONTROL Groups and named rights]**, haga clic en **[!UICONTROL Add]** y seleccione el grupo **[!UICONTROL Delivery manager]**.

Los derechos asignados a los gestores de envío les permiten llevar a cabo las siguientes tareas:

* Mostrar entornos **[!UICONTROL Live]**.
* Mostrar y modificar las categorías de oferta.
* Apruebe ofertas si son sus revisores.

   >[!NOTE]
   >
   >**El** gestor de envíos solo puede aprobar una oferta si se ha declarado que es revisor en la configuración de la oferta.

## Matriz de permisos por operador de interacción {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gestor de ofertas (con diseño)</strong><br /> </td> 
   <td> <strong>Gestor de ofertas (Live Env)</strong><br /> </td> 
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
   <td> Filtros de oferta predefinidos<br /> </td> 
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
   <td> Filtros de oferta predefinidos<br /> </td> 
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
