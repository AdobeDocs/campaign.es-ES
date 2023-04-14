---
title: Ejecución de entrega de mensajes transaccionales
description: Obtenga más información acerca de la ejecución y supervisión de la entrega de mensajes transaccionales
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 72%

---


# Ejecución de envíos {#delivery-execution}

Una vez completado el enriquecimiento y vinculada una plantilla de envío al evento, la entrega se envía desde la instancia de ejecución.

>[!NOTE]
>
>Los mensajes transaccionales tienen prioridad sobre cualquier otro envío.

Todos los envíos se agrupan en la carpeta **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]**.

De forma predeterminada, se clasifican en subcarpetas por mes de envío. Esta ordenación se puede cambiar en las propiedades de la plantilla de mensaje.

## Supervisión de mensajes transaccionales {#transactional-message-monitoring}

Para supervisar los mensajes transaccionales, compruebe los [registros de envío](send.md).

Los envíos transaccionales enviados desde la instancia de ejecución se sincronizan con la instancia de control a través de un flujo de trabajo técnico (**[!UICONTROL Message Center execution instance]**) que se ejecuta cada hora.

>[!NOTE]
>
>Los envíos acumulan semanalmente los eventos en función de la actualización de eventos más reciente y no en la fecha de creación del evento. Por lo tanto, al extraer registros de envío de mensajería transaccional de la instancia de control, el ID de envío asociado con cada ID de registro de envío puede cambiar con el tiempo a medida que se actualiza el registro (por ejemplo, cuando se recibe una devolución de entrada para el evento).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->
