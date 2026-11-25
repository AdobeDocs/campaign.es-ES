---
product: campaign
title: Seguimiento de una campaña
description: Obtenga información sobre cómo rastrear una campaña con el marketing distribuido de Campaign
feature: Distributed Marketing
version: Campaign v8, Campaign Classic v7
role: User
exl-id: 9904c1c6-c233-4aa2-a237-338ebde15661
TQID: https://experienceleague.adobe.com/v-ZkfPAMBCbVOb0FheuwmYILdV4uFjbGu6cv2uoKccc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: cdc2fbe67fe123c895c8d3d71daffe022ba5c030
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 71%
---
# Seguimiento de una campaña{#tracking-a-campaign}



Los operadores de entidad central pueden rastrear las solicitudes de campaña en la lista de paquetes de campañas.

Esto les permite:

* [Filtración de paquetes](#filter-packages),
* [Editar paquetes](#edit-packages),
* [Cancelar un paquete](#cancel-a-package),
* [Reinicialización de un paquete](#reinitializing-a-package).

## Filtrado de paquetes {#filter-packages}

En la pestaña **[!UICONTROL Campaigns]**, puede mostrar la lista de **[!UICONTROL Campaign packages]** que reagrupa todas las campañas de marketing distribuido existentes. Puede filtrar esta lista para que solo se muestren las campañas publicadas, retrasadas, pendientes de aprobación, etc. Para ello, haga clic en los vínculos de la sección superior de esta vista o utilice el vínculo **[!UICONTROL Filter list]** y seleccione el estado del paquete de campaña que desea visualizar.

![Lista de paquetes de campaña con el filtro de estado abierto: en edición, con aprobación pendiente, aprobado, rechazado, etc.](assets/mkg_dist_catalog_filter.png)

## Edición de paquetes {#edit-packages}

La página **[!UICONTROL Campaign packages]** permite ver el resumen de cada paquete.

Este resumen muestra la siguiente información: etiqueta, tipo de campaña, así como el nombre de la campaña desde la que se creó y la carpeta.

Haga clic en el nombre del paquete para editarlo. También puede ver solicitudes por sus entidades locales y por su estado.

Esta información también se incluye en la vista **[!UICONTROL Campaign orders]**, que enumera todas las solicitudes.

![Lista de pedidos de campaña que muestra cada pedido con su entidad local, campaña y estado (disponible o cancelado).](assets/mkg_dist_catalog_op_command_details.png)

El operador central puede editar la solicitud. Hay dos formas de hacerlo:

1. El operador puede hacer clic en el nombre de la solicitud para editarla: esto muestra los detalles de las solicitudes.

   ![Al hacer clic en un pedido de la lista de pedidos de Campaign, se abre su panel con el estado, el paquete, la entidad local y las aprobaciones.](assets/mkg_dist_catalog_op_command_edit1.png)

   La pestaña **[!UICONTROL Edit > General]** permite ver la información introducida por la entidad local cuando solicita la campaña.

   ![Ficha Order Edit, General: etiqueta, entidad organizativa, operador asignado, estado y comentario de la entidad local.](assets/mkg_dist_catalog_op_command_edit1a.png)

1. El operador puede hacer clic en la etiqueta del paquete de campaña para editarlo y cambiar ciertas configuraciones.

   ![Abriendo un paquete desde la lista y después uno de sus pedidos de campaña, cada uno con su panel.](assets/mkg_dist_catalog_op_command_edit2.png)

## Cancelación de un paquete {#cancel-a-package}

La entidad central puede cancelar un paquete de campaña en cualquier momento.

En el paquete de campaña **[!UICONTROL Dashboard]**, haga clic en **[!UICONTROL Cancel]**.

![Cancelar el botón del paquete en el panel del paquete abre el cuadro de diálogo Acción en el paquete con un campo Comentario.](assets/mkg_dist_cancel_op_from_dashboard.png)

El campo **[!UICONTROL Comment]** le permite justificar la cancelación.

Para las **campañas locales**, cancelar un paquete las elimina de la lista de campañas de marketing disponibles.

Para las **campañas de colaboración**, cancelar un paquete activa varias acciones:

1. Todas las solicitudes relacionadas con este paquete se cancelan.

   ![Panel de paquetes cancelado que enumera sus pedidos de campaña, cada uno con el estado Cancelado.](assets/mkg_dist_mutual_op_cancelled.png)

1. La campaña de referencia se cancela y todos los procesos activos (flujos de trabajo, envíos) se detienen.

   ![Se canceló el panel de campañas de referencia y los envíos de correo electrónico y SMS se muestran como Detenidos.](assets/mkg_dist_mutual_op_cancelled1.png)

1. Se envía una notificación a todas las entidades locales correspondientes.

   ![Cancelación del correo electrónico del paquete que notifica a una entidad local que la campaña se ha cancelado de forma centralizada.](assets/mkg_dist_mutual_op_cancelled2.png)

La entidad central puede seguir accediendo y reiniciando los paquetes cancelados (consulte a continuación) si es necesario. Solo se ofrecen a las entidades locales una vez aprobadas e iniciadas. A continuación, se muestra el proceso de reinicio de paquetes.

## Reinicialización de un paquete {#reinitializing-a-package}

Los paquetes de campañas que ya se han publicado se pueden reiniciar, modificar y ponerlo a disposición de entidades locales.

1. Seleccione el paquete que desee.
1. Haga clic en el enlace **[!UICONTROL Reinitialize the package to reuse it]** y en **[!UICONTROL OK]**.

   ![Reinicializar el cuadro de diálogo de confirmación del paquete: el estado pasa a ser Being edited, con el botón OK.](assets/mkg_dist_mutual_op_reinit.png)

1. Haga clic en el botón **[!UICONTROL Save]** para aprobar el reinicio del paquete.

   ![Se ha cancelado el panel del paquete con el botón Guardar resaltado para aprobar el reinicio.](assets/mkg_dist_mutual_op_reinit2.png)

1. El estado del paquete cambia a **[!UICONTROL Being edited]**. Modifique, apruebe y vuelva a publicarlo para restaurarla en la lista de paquetes de campañas.

>[!NOTE]
>
>También puede reiniciar paquetes de campañas canceladas.
