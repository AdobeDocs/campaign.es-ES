---
title: Conceder y restringir permisos en carpetas de Campaign
description: Obtenga información sobre cómo conceder o restringir permisos en carpetas
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
source-git-commit: b96ac3bd2365c548d071e626721d606dd33200b5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 12%

---

# Administrar permisos de carpeta{#manage-folder-permissions}

## Restringir el acceso a una carpeta{#restrict-access-to-a-folder}

Utilice permisos en carpetas para organizar y controlar el acceso a los datos de Campaign.

La administración de carpetas se detalla en [esta página](../audiences/folders-and-views.md).

Para editar permisos en una carpeta específica de Campaign, siga los pasos a continuación:

1. Haga clic con el botón derecho en la carpeta y seleccione **[!UICONTROL Properties...]**.
1. Vaya a la **[!UICONTROL Security]** para ver las autorizaciones de esta carpeta.

   ![](assets/folder-permissions.png)

* Hasta **autorizar un grupo o un operador**, haga clic en **[!UICONTROL Add]** y seleccione el grupo u operador para asignar autorizaciones para esta carpeta.
* Hasta **prohibir un grupo o un operador**, haga clic en **[!UICONTROL Delete]** y seleccione el grupo u operador para quitar la autorización de esta carpeta.
* Hasta **seleccione los derechos asignados a un grupo o a un operador**, seleccione el grupo u operador, seleccione los derechos de acceso que desee conceder y anule la selección de los demás.

## Propagación de permisos {#propagate-permissions}

Para propagar autorizaciones y derechos de acceso, seleccione el **[!UICONTROL Propagate]** en las propiedades de la carpeta.

Las autorizaciones definidas en esta ventana se aplican a todas las subcarpetas del nodo actual. Siempre puede sobrecargar estas autorizaciones para cada una de las subcarpetas.

>[!NOTE]
>
>Desmarcando la **[!UICONTROL Propagate]** para una carpeta no la borra para las subcarpetas: debe borrarlo explícitamente para cada una de las subcarpetas.

## Concesión de acceso a todos los operadores {#grant-access-to-all-operators}

En el **[!UICONTROL Security]** , seleccione **[!UICONTROL System folder]** para permitir el acceso a todos los operadores, independientemente de sus permisos.

Si se borra esta opción, se debe volver a añadir explícitamente el operador (o su grupo) a la lista de autorizaciones para que tengan acceso.
