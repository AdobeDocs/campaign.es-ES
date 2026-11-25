---
product: campaign
title: Entregas multicanal
description: Descubra más información sobre las entregas multicanal
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
TQID: 'https://experienceleague.adobe.com/hD15kwTxO1uHeIQjrozZmONmVWI5ZrMn40ORMwrGbf8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: bce277d1-7efa-48d8-9a1b-b588bb45ba1c
    internal-label: Channels Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 56%
---
# Entregas multicanal{#cross-channel-deliveries}

Los envíos multicanal están disponibles en la pestaña **[!UICONTROL Deliveries]** de las actividades de [flujo de trabajo de la campaña](campaign-workflows.md).

Seleccione la plantilla en la que desea basar la entrega y defina su contenido.

Puede especificar un público objetivo para la entrega ascendente del flujo de trabajo utilizando las distintas actividades de direccionamiento.

En el siguiente ejemplo, aprenda a crear un flujo de trabajo para enviar un correo electrónico o un SMS a los suscriptores de las notificaciones push una semana después. Para ello:

1. Cree una campaña.
1. En la ficha **[!UICONTROL Targeting and workflows]** de su campaña, agregue una actividad **[!UICONTROL Query]**.
1. Configure your query: seleccione los destinatarios suscritos a las notificaciones push como dimensión objetivo.

   >[!NOTE]
   >
   >Para las notificaciones push, recuerde utilizar la dimensión objetivo **aplicaciones del suscriptor**.

   ![Actividad de consulta con el esquema de aplicaciones del suscriptor seleccionado como documento por el que filtrar.](assets/cross_channel_delivery_1.png)

1. Agregue las condiciones de filtro a la consulta. En este caso, se seleccionarán los destinatarios que tengan un número de teléfono móvil o una dirección de correo electrónico.

   ![El filtro de consulta con Mobile no está vacío y una condición O para Email no está vacía.](assets/cross_channel_delivery_2.png)

1. Añada una actividad **[!UICONTROL Split]** al flujo de trabajo para dividir los destinatarios que tienen número de móvil y aquellos que tienen dirección de correo electrónico.
1. En la pestaña **[!UICONTROL Delivery]**, seleccione una entrega para cada uno de sus destinatarios.

   Cree su envío de la misma manera que con el asistente de envíos clásico haciendo doble clic en la actividad de envío del flujo de trabajo.

   ![Flujo de trabajo de campaña con una consulta y una división que llevan a una entrega móvil y una entrega por correo electrónico.](assets/cross_channel_delivery_3.png)

1. Añada y configure una actividad **[!UICONTROL Wait]** para que los destinatarios no reciban demasiados envíos a la vez.
1. Añada una actividad **[!UICONTROL Split]** para dividir los suscriptores de aplicaciones móviles iOS o Android.

   Seleccione un servicio para cada uno de los sistemas operativos.

   ![Cuadro de diálogo de consulta con aplicaciones de suscriptor como dimensión de segmentación y suscriptores de una aplicación móvil de Android seleccionados.](assets/cross_channel_delivery_4.png)

1. Seleccione y configure una entrega de aplicaciones para dispositivos móviles para cada uno de los sistemas operativos.

   ![Flujo de trabajo con envíos de correo electrónico y SMS que se unen a una actividad de espera y, a continuación, envíos de Split a Push iOS y Push Android.](assets/cross_channel_delivery_5.png)
