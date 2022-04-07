---
title: Perfiles de operador
description: Creación de operadores de administración de ofertas
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 8a43f0fad9f84849745f3a0d426329efbf228105
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 33%

---

# Perfiles de operador {#operator-profiles}

Dos tipos de operadores pueden utilizar Campaign Interaction: **Administradores de ofertas** y **Administradores de envío**. Cada uno de ellos tiene permisos y restricciones específicos. Obtenga más información sobre los operadores y permisos de Campaign en [esta página](../start/permissions.md).

* La variable **[!UICONTROL Offer manager]** crea y mantiene ofertas.
* La variable **[!UICONTROL Delivery manager]** aprueba y utiliza ofertas

## Creación de un operador de gestor de ofertas{#offer-manager}

1. Creación de un operador.

   ![](../assets/do-not-localize/book.png) Los pasos para crear un operador en Campaign se detallan en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vaya a la ventana **[!UICONTROL Groups and named rights]**, haga clic en **[!UICONTROL Add]** y seleccione el grupo **[!UICONTROL Offer manager]**.

Los derechos asignados al Gestor de ofertas permiten realizar las siguientes tareas:

* Modificar entornos **[!UICONTROL Design]**.
* Ver entornos **[!UICONTROL Live]**.
* Configure las funciones de administración (espacios predefinidos y filtros).
* Cree y modifique categorías.
* Cree ofertas.
* Configurar la idoneidad de la oferta.
* Aprobar ofertas.

Si las ofertas se utilizan en un flujo de trabajo, se debe añadir el operador a la variable **[!UICONTROL Administrator]** o **[!UICONTROL Offer managers]** grupo de operadores para ejecutar el flujo de trabajo.

>[!NOTE]
>
>**Administradores de ofertas** solo puede aprobar una oferta si no se especifica ningún revisor o si se han declarado como revisores en la plantilla de oferta.

## Creación de un operador Delivery manager {#delivery-manager}

1. Creación de un operador.

   ![](../assets/do-not-localize/book.png) Los pasos para crear un operador en Campaign se detallan en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vaya a la ventana **[!UICONTROL Groups and named rights]**, haga clic en **[!UICONTROL Add]** y seleccione el grupo **[!UICONTROL Delivery manager]**.

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
