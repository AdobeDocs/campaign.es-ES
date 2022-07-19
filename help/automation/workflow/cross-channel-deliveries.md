---
product: campaign
title: Entregas multicanal
description: Descubra más información sobre las entregas multicanal
feature: Workflows, Channels Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 76%

---

# Entregas multicanal{#cross-channel-deliveries}

Las entregas multicanal están disponibles en la pestaña **[!UICONTROL Deliveries]** de las actividades de flujo de trabajo de la campaña.[](campaign-workflows.md)

Seleccione la plantilla en la que desea basar la entrega y defina su contenido.

Puede especificar un público objetivo para la entrega ascendente del flujo de trabajo utilizando las distintas actividades de direccionamiento.

En el siguiente ejemplo, aprenda a crear un flujo de trabajo para enviar un correo electrónico o un SMS a los suscriptores de las notificaciones push una semana después. Para ello:

1. Cree una campaña.
1. En el **[!UICONTROL Targeting and workflows]** de la campaña, agregue una **[!UICONTROL Query]** actividad.
1. Configure la consulta: seleccione los destinatarios suscritos a las notificaciones push como dimensión objetivo.

   >[!NOTE]
   >
   >Para las notificaciones push, recuerde utilizar la dimensión objetivo **aplicaciones del suscriptor**.

   ![](assets/cross_channel_delivery_1.png)

1. Agregue las condiciones de filtro a la consulta. En este caso, se seleccionarán los destinatarios que tengan un número de teléfono móvil o una dirección de correo electrónico.

   ![](assets/cross_channel_delivery_2.png)

1. Añada una actividad **[!UICONTROL Split]** al flujo de trabajo para dividir los destinatarios que tienen número de móvil y aquellos que tienen dirección de correo electrónico.
1. En la pestaña **[!UICONTROL Delivery]**, seleccione una entrega para cada uno de sus destinatarios.

   Cree su envío de la misma manera que con el asistente de envíos clásico haciendo doble clic en la actividad de envío del flujo de trabajo. Para obtener más información, consulte  .

   ![](assets/cross_channel_delivery_3.png)

1. Añada y configure una actividad **[!UICONTROL Wait]** para que los destinatarios no reciban demasiados envíos a la vez.
1. Añada una actividad **[!UICONTROL Split]** para dividir los suscriptores de aplicaciones móviles iOS o Android.

   Seleccione un servicio para cada uno de los sistemas operativos. Para obtener más información sobre la creación de servicios, consulte esta sección .

   ![](assets/cross_channel_delivery_4.png)

1. Seleccione y configure una entrega de aplicaciones para dispositivos móviles para cada uno de los sistemas operativos.

   ![](assets/cross_channel_delivery_5.png)
