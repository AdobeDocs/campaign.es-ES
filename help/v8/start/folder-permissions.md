---
title: Concesión y restricción de permisos en carpetas de Campaign
description: Obtenga información sobre cómo conceder o restringir permisos en carpetas
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
version: Campaign v8, Campaign Classic v7
TQID: https://experienceleague.adobe.com/lQQioEkhkrrJpqv6uMCsktMdQhwZT9iUkU2xfRtXaz0
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 315
ht-degree: 28%

---

# Administrar permisos de carpeta{#manage-folder-permissions}

## Restringir el acceso a una carpeta{#restrict-access-to-a-folder}

Utilice permisos en las carpetas para organizar y controlar el acceso a los datos de Campaign.

La administración de carpetas se detalla en [esta página](../audiences/folders-and-views.md).

Para editar permisos en una carpeta de Campaign específica, siga los pasos a continuación:

1. Haga clic con el botón derecho en la carpeta y seleccione **[!UICONTROL Properties...]**.
1. Vaya a la pestaña **[!UICONTROL Security]** para ver las autorizaciones de esta carpeta.

   ![](assets/folder-permissions.png)

* Para **autorizar un grupo o un operador**, haga clic en el botón **[!UICONTROL Add]** y seleccione el grupo u operador para asignar autorizaciones a esta carpeta.
* Para **prohibir un grupo o un operador**, haga clic en **[!UICONTROL Delete]** y seleccione el grupo u operador para quitar la autorización de esta carpeta.
* Para **seleccionar los derechos asignados a un grupo o a un operador**, seleccione el grupo u operador, seleccione los derechos de acceso que desee conceder y anule la selección de los demás.

>[!NOTE]
>
>No debería poder crear un objeto para el que no tenga al menos una carpeta con derechos de escritura.
>
>No necesita ser administrador para crear fragmentos, pero debe tener derechos de escritura en al menos una carpeta “Fragmento visual de contenido”. De lo contrario, no podrá crear un fragmento visual.

## Propagación de permisos {#propagate-permissions}

Para propagar autorizaciones y derechos de acceso, seleccione la opción **[!UICONTROL Propagate]** en las propiedades de la carpeta.

Las autorizaciones definidas en esta ventana se aplican a todas las subcarpetas del nodo actual. Siempre puede sobrecargar estas autorizaciones para cada una de las subcarpetas.

>[!NOTE]
>
>Al desmarcar la opción **[!UICONTROL Propagate]** de una carpeta, no se borra para las subcarpetas: debe borrarla explícitamente para cada una de las subcarpetas.

## Concesión de acceso a todos los operadores {#grant-access-to-all-operators}

En la ficha **[!UICONTROL Security]**, seleccione **[!UICONTROL System folder]** para permitir el acceso a todos los operadores, independientemente de sus permisos.

Si se borra esta opción, se debe volver a añadir explícitamente el operador (o su grupo) a la lista de autorizaciones para que tengan acceso.
