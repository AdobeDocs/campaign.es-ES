---
product: campaign
title: Foros de debate
description: Aprenda a utilizar los foros de debate de Campaign
feature: Campaigns, Resource Management
role: User
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 45%

---

# Foros de debate{#discussion-forums}

Los operadores de Adobe Campaign pueden utilizar foros de debate para compartir información. Cada uno de los elementos siguientes tiene su propio foro: planes, programas, campañas, recursos de marketing, simulaciones y existencias. Cada operador también tiene un foro personal. Todos los debates son públicos, incluso en foros personales.

Los operadores pueden suscribirse a un foro para recibir un correo electrónico de notificación cada vez que se publica un mensaje.

## Acceso a un foro {#accessing-a-forum}

Para acceder a un foro, vaya a un panel y haga clic en el vínculo **[!UICONTROL Forum]** en la esquina superior derecha.

![](assets/mrm-forum-icon.png)

Los mensajes y sus respuestas se muestran de más reciente a más antiguo.

Para iniciar un nuevo subproceso, haga clic en el botón **[!UICONTROL Add a discussion]** en la esquina superior derecha. De esta forma, aparece el cuadro **[!UICONTROL Discussion forum]** (consulte más abajo).

![](assets/mrm-forum-new-thread.png)


Introduzca el texto en el campo **[!UICONTROL Message]** y un título de conversación en el campo **[!UICONTROL Subject]**.

De forma predeterminada, se notifica a los operadores que ya han publicado un mensaje en este foro. Puede seleccionar un operador adicional al que notificar. Para notificar a varios operadores, seleccione un grupo de operadores.

Puede agregar datos adjuntos al mensaje con el botón **[!UICONTROL Browse...]**. El archivo adjunto también se incluye en el mensaje de correo electrónico de notificación. Los archivos adjuntos solo se pueden enviar individualmente: para enviar varios archivos, debe comprimirlos en un archivo .zip.

>[!CAUTION]
>
>Una vez que se ha publicado un mensaje en el foro, ya no se puede cambiar ni eliminar.

## Publicación en el foro personal de un operador {#posting-to-the-personal-forum-of-an-operator}

Puede enviar un mensaje al foro de un operador. Los foros personales son públicos y todos los operadores pueden ver el mensaje. El operador recibe una notificación por correo electrónico cada vez que alguien publica en su foro personal.

Para acceder al foro de un operador, puede:

* Vaya a la carpeta **[!UICONTROL Administration > Access management > Operators]** del explorador de Campaign, seleccione el operador para abrir su panel y, a continuación, haga clic en el vínculo **[!UICONTROL Forum]** en la esquina superior derecha.
* Busque el nombre del operador en la interfaz de usuario de Adobe Campaign (a través de un mensaje publicado en el foro por este operador, correspondiente a una tarea asignada a él) y haga clic en él para acceder al panel del operador.

## Suscripción a un foro {#subscribing-to-a-forum}

La suscripción a un foro le permite seguir todas las discusiones. Una vez suscrito, recibe una notificación por correo electrónico cada vez que se publica un mensaje en el foro.

Para responder a un mensaje, haga clic en el cuerpo del correo electrónico y luego inicie sesión en la interfaz web de Adobe Campaign.

* Para suscribirse a un foro, haga clic en el botón **[!UICONTROL Follow discussions]** situado en la sección superior derecha de la lista de mensajes.

  La sección se vuelve azul y muestra que está suscrito al foro.

* Para cancelar la suscripción a un foro, haga clic en el botón **[!UICONTROL Unsubscribe]**.

* Su panel personal enumera los foros a los que está suscrito. Haga clic en el vínculo **[!UICONTROL Subscription to discussion forums]** para mostrar la lista y luego haga clic en el elemento que le interese para acceder al foro correspondiente.

  ![](assets/forum-subscribed.png)


## Solución de problemas de entrega de notificaciones {#checking-notification-delivery}

Si los operadores suscritos a un foro no reciben notificaciones como se espera:

* Compruebe que las direcciones de correo electrónico se han introducido correctamente en los perfiles del operador.
* Vaya a la carpeta **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** del explorador de Campaign y compruebe que el flujo de trabajo **[!UICONTROL Jobs in discussion forums]** se ha iniciado sin errores.
* Compruebe los registros de envío:

   * En la página de inicio de Adobe Campaign, vaya a **[!UICONTROL Campaigns > Navigation > Deliveries]** y, a continuación, abra la entrega **[!UICONTROL Discussion forum notification]**.
   * En el explorador de Campaign, vaya a **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]** y, a continuación, haga clic en **[!UICONTROL Discussion forum notifications]**.

  En el cuadro **[!UICONTROL Discussion forum notifications]**, los registros de envío se encuentran en la pestaña **[!UICONTROL Edit > Delivery]**. También puede ver las pestañas **[!UICONTROL Tracking > Log]** y **[!UICONTROL Exclusion causes]**.
