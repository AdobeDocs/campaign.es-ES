---
product: campaign
title: Publicación del paquete de campaña
description: Publicación del paquete de campaña
feature: Distributed Marketing
exl-id: 2cd1981d-f192-41dc-b2f2-4fcd60493079
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 97%

---

# Publicación del paquete de campaña{#publishing-the-campaign-package}

Los operadores de entidad central publican las campañas que desean ofrecer a las entidades locales en la **[!UICONTROL list of campaign packages]**.

Antes de poder publicar los paquetes en la lista de paquetes de campañas, la entidad central debe aprobarlos. Para ello, se puede especificar un revisor o un grupo de revisores a través del vínculo **[!UICONTROL Approval parameters]** del paquete de campañas.

## Asignar un revisor {#assigning-a-reviewer}

Para seleccionar un revisor, haga clic en el vínculo **[!UICONTROL Approval parameters]** del paquete de campaña y elija el revisor correspondiente en la lista desplegable.

![](assets/s_advuser_mkg_dist_define_valid.png)

A continuación, puede iniciar el proceso de aprobación haciendo clic en **[!UICONTROL Submit for approval]**.

![](assets/s_advuser_mkg_dist_valid_process.png)

Hecho esto, se envía un mensaje de notificación al revisor para confirmar la disponibilidad de este paquete de campaña. El mensaje contiene un vínculo para aceptar o rechazar la aprobación mediante el acceso a la web.

![](assets/s_advuser_mkg_dist_valid_process1.png)

>[!NOTE]
>
>En el nivel de la entidad organizativa, también puede especificar los revisores que deben aprobar las solicitudes. Para obtener más información, consulte [Entidades organizativas](about-distributed-marketing.md#organizational-entities).

## Añadir otros revisores {#adding-other-reviewers}

Puede añadir otros revisores desde el vínculo **[!UICONTROL Edit...]** que se encuentra en la pestaña **[!UICONTROL Approval parameters...]** del paquete de la campaña.

![](assets/s_advuser_mkg_dist_select_op_valid.png)

## Cronología de aprobación {#approval-periods}

De forma predeterminada, los revisores tienen tres días a partir de la fecha de envío para procesar la aprobación.

En la ventana de edición de revisores, también puede definir recordatorios que envían uno o varios mensajes si no se ha aprobado un paquete de campañas. Para ello, haga clic en el vínculo **[!UICONTROL Add reminder]** y luego en el botón **[!UICONTROL Add]**.

Los recordatorios pueden enviarse en una fecha determinada o **x** días después de la fecha de presentación. El tipo de recordatorio se puede configurar en la primera columna de la tabla de recordatorios. En el siguiente ejemplo, los revisores recibirán un mensaje recordatorio el 01/11/2023, es decir, dos días antes de la fecha seleccionada en la columna **[!UICONTROL Date]** y un segundo recordatorio un día antes del final del periodo de aprobación, por ejemplo, dos días después de la fecha de envío para la aprobación.

![](assets/s_advuser_mkg_dist_reminder_planning.png)

Una vez definido y enviado el paquete para su aprobación, la programación de ejecución se muestra en la pestaña **[!UICONTROL Audit]**. Muestra la fecha límite de procesamiento calculada en función de la configuración anterior, así como las fechas de todos los recordatorios configurados.

## Aprobación mediante la consola de cliente {#approving-via-the-adobe-campaign-console}

Si no se ha especificado ningún revisor o si ninguno de los operadores de notificación ha aprobado el paquete, el botón **[!UICONTROL Approve the package]** le permite aprobarlo un paquete de campañas directamente desde el **[!UICONTROL Dashboard]** o desde la información general de los paquetes.

![](assets/s_advuser_mkg_dist_valid_button.png)

Una vez realizada la aprobación, la campaña se publica, se añade a la lista y, en cuanto se alcanza su fecha de disponibilidad, las entidades locales pueden utilizarla. Si se han especificado las entidades locales al crear la campaña, se envía un mensaje a los operadores en el grupo de notificación para que sepan que la campaña está disponible. Si no se especificó ninguna entidad con anterioridad, la campaña está disponible para todas las entidades locales de forma predeterminada. Para obtener más información, consulte [Entidades organizativas](about-distributed-marketing.md#organizational-entities).
