---
audience: end-user
title: Diseño de una entrega de notificaciones push enriquecidas
description: Aprenda a diseñar una entrega de notificaciones push enriquecidas para Android con Adobe Campaign Web
feature: Push
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 42e3623b-b401-4fcc-80a7-ea38347fddc6
source-git-commit: 5f1ffd5d59791a0e6ff8a67feb08c8eed128cc1e
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 13%

---

# Diseño de una entrega push enriquecida para Android {#rich-push}

Con Firebase Cloud Messaging, puede elegir entre dos tipos de mensajes:

* El **[!UICONTROL Data message]** es gestionado por la aplicación del cliente. Estos mensajes se envían directamente a la aplicación móvil, que genera y muestra una notificación de Android en el dispositivo. Los mensajes de datos solo contienen las variables de aplicación personalizadas.

* El **[!UICONTROL Notification message]**, gestionado automáticamente por el SDK de FCM. FCM muestra automáticamente el mensaje en los dispositivos de los usuarios en nombre de la aplicación del cliente. Los mensajes de notificación contienen un conjunto predefinido de parámetros y opciones, pero pueden personalizarse aún más con las variables de aplicación personalizadas.

## Definición del contenido de la notificación {#push-message}

Una vez creado el envío push, puede definir su contenido. Hay tres plantillas disponibles:

* **Plantilla predeterminada** permite enviar notificaciones con un icono simple y una imagen adjunta.

* **Plantilla básica** Puede incluir texto, imágenes y botones en las notificaciones.

* **Plantilla de carrusel** le permite enviar notificaciones con texto e imágenes múltiples que los usuarios pueden deslizar.

Examine las pestañas siguientes para aprender a componer el mensaje para cada plantilla.

>[!BEGINTABS]

>[!TAB Plantilla predeterminada]

1. Del desplegable **[!UICONTROL Notification type]**, seleccione **[!UICONTROL Default]**.

   ![](assets/rich_push_default.png)

1. Para redactar el mensaje, escriba el texto en la **[!UICONTROL Title]** y **[!UICONTROL Message]** campos.

   ![](assets/rich_push_default_2.png)

1. Utilice campos de personalización dinámicos para definir contenido, personalizar datos y agregar contenido dinámico. [Más información](../send/personalize.md)

1. Para personalizar aún más la notificación push, configure el **[!UICONTROL Notification options]** y **[!UICONTROL HTTPv1 additional options]** de la notificación push. [Más información](#push-advanced)

   ![](assets/rich_push_default_3.png)

Una vez definido el contenido del mensaje, puede utilizar los suscriptores de prueba para previsualizar y probar el mensaje.

>[!TAB Plantilla básica]

1. Del desplegable **[!UICONTROL Notification Type]**, seleccione **[!UICONTROL Basic]**.

   ![](assets/rich_push_basic.png)

1. Para redactar el mensaje, escriba el texto en la **[!UICONTROL Title]**, **[!UICONTROL Message]** y **[!UICONTROL Expanded message]** campos.

   El **[!UICONTROL Message]** el texto aparece en la vista contraída mientras que la variable **[!UICONTROL Expanded message]** se muestra cuando se expande la notificación.

   ![](assets/rich_push_basic_2.png)

1. Utilice campos de personalización dinámicos para definir contenido, personalizar datos y agregar contenido dinámico. [Más información](../send/personalize.md)

1. En el **[!UICONTROL Color options]** , introduzca los códigos de color hexadecimales para su **[!UICONTROL Title]**, **[!UICONTROL Message]** y **[!UICONTROL Background]**.

1. Añadir un **[!UICONTROL Remind later button]** si es necesario. Introduzca su **[!UICONTROL Reminder Text]** y **Fecha** en los campos correspondientes.

   El **[!UICONTROL Reminder Date]** El campo espera un valor que represente una época en segundos.

1. Clic **[!UICONTROL Add button]** y rellene los campos siguientes:

   * **[!UICONTROL Label]**: texto mostrado en el botón.
   * **[!UICONTROL Link URI]**: especifique el URI que se ejecutará al hacer clic en el botón.

   Tiene la opción de incluir hasta tres botones en la notificación push. Si opta por el **[!UICONTROL Remind later button]**, solo puede incluir un máximo de dos botones.

1. Seleccione el **[!UICONTROL Link type]** de la URL vinculada del botón:

   * **[!UICONTROL Web URL]**: las URL web dirigen a los usuarios al contenido en línea. Al hacer clic en, se solicita al explorador web predeterminado del dispositivo que abra y navegue hasta la dirección URL designada.

   * **[!UICONTROL Deeplink]**: los vínculos profundos son direcciones URL que guían a los usuarios a secciones específicas de una aplicación aunque esta esté cerrada. Al hacer clic en él, puede aparecer un cuadro de diálogo que permite a los usuarios elegir entre varias aplicaciones capaces de gestionar el vínculo.

   * **[!UICONTROL Open App]**: Las direcciones URL de aplicaciones abiertas le permiten conectarse directamente al contenido de una aplicación. Permite a la aplicación establecerse como controlador predeterminado para un tipo específico de vínculo, omitiendo el cuadro de diálogo de desambiguación.

   Para obtener más información sobre cómo gestionar vínculos de aplicaciones Android, consulte [Documentación para desarrolladores de Android](https://developer.android.com/training/app-links).

   ![](assets/rich_push_basic_3.png)

1. Para personalizar aún más la notificación push, configure el **[!UICONTROL Notification options]** y **[!UICONTROL HTTPv1 additional options]** de la notificación push. [Más información](#push-advanced)

   ![](assets/rich_push_basic_4.png)

Una vez definido el contenido del mensaje, puede utilizar los suscriptores de prueba para previsualizar y probar el mensaje.

>[!TAB Plantilla de carrusel]

1. Del desplegable **[!UICONTROL Notification Type]**, seleccione **[!UICONTROL Carousel]**.

   ![](assets/rich_push_carousel.png)

1. Para redactar el mensaje, escriba el texto en la **[!UICONTROL Title]**, **[!UICONTROL Message]** y **[!UICONTROL Expanded message]** campos.

   El **[!UICONTROL Message]** el texto aparece en la vista contraída mientras que la variable **[!UICONTROL Expanded message]** se muestra cuando se expande la notificación.

   ![](assets/rich_push_carousel_1.png)

1. Utilice el Editor de expresiones para definir contenido, personalizar datos y agregar contenido dinámico. [Más información](../send/personalize.md)

1. En el **[!UICONTROL Color options]** , introduzca los códigos de color hexadecimales para su **[!UICONTROL Title]**, **[!UICONTROL Message]** y **[!UICONTROL Background]**.

1. Elija cómo se usa el **[!UICONTROL Carousel]** funciona:

   * **[!UICONTROL Auto]**: recorre automáticamente las imágenes como diapositivas, en transición a intervalos predefinidos.
   * **[!UICONTROL Manual]**: permite a los usuarios deslizar manualmente entre diapositivas para navegar por las imágenes.

1. Desde el **[!UICONTROL Layout]** menú desplegable, seleccione **[!UICONTROL Filmstrip]** para incluir vistas previas de las imágenes anterior y siguiente junto con la diapositiva principal.

1. Clic **[!UICONTROL Add image]** e introduzca la URL de imagen, la URL de texto y la URL de acción.

   Asegúrese de incluir un mínimo de tres imágenes y un máximo de cinco.

   ![](assets/rich_push_carousel_2.png)

1. Para personalizar aún más la notificación push, configure el **[!UICONTROL Notification options]** y **[!UICONTROL HTTPv1 additional options]** de la notificación push. [Más información](#push-advanced)

   ![](assets/rich_push_carousel_3.png)

Una vez definido el contenido del mensaje, puede utilizar los suscriptores de prueba para previsualizar y probar el mensaje.

>[!ENDTABS]

## Configuración avanzada de notificación push {#push-advanced}

### Opciones de notificación {#notification-options}

| Parámetro | Descripción |
|---------|---------|
| **[!UICONTROL Channel ID]** | Establezca el ID de canal de la notificación. La aplicación debe crear un canal con este ID de canal antes de recibir cualquier notificación. |
| **[!UICONTROL Icon]** | Configure el icono de la notificación para que se muestre en los dispositivos de sus perfiles. |
| **[!UICONTROL Sound]** | Configure el sonido para que se reproduzca cuando el dispositivo reciba la notificación. |
| **[!UICONTROL Tag]** | Establezca un identificador utilizado para reemplazar las notificaciones existentes en el cajón de notificaciones. Esto ayuda a evitar la acumulación de varias notificaciones y garantiza que solo se muestre la notificación relevante más reciente. |
| **[!UICONTROL Color]** | Establezca el color del icono de la notificación con un código de color hexadecimal. |
| **[!UICONTROL Click action]** | Configure la acción asociada con un clic del usuario en la notificación. |
| **[!UICONTROL Notification background color]** | Establece el color de tu fondo de notificación con tus códigos de color hexadecimales. |
| **[!UICONTROL Link type]** | <ul><li>URL web: las URL web dirigen a los usuarios al contenido en línea. Al hacer clic en, se solicita al explorador web predeterminado del dispositivo que abra y navegue hasta la dirección URL designada.</li><li>Vínculos profundos: Los vínculos profundos son direcciones URL que guían a los usuarios a secciones específicas de una aplicación aunque esta esté cerrada. Al hacer clic en él, puede aparecer un cuadro de diálogo que permite a los usuarios elegir entre varias aplicaciones capaces de gestionar el vínculo.</li><li> Abrir aplicación: Las direcciones URL de Abrir aplicación permiten conectarse directamente al contenido de una aplicación. Permite a la aplicación establecerse como controlador predeterminado para un tipo específico de vínculo, omitiendo el cuadro de diálogo de desambiguación.</li></ul> |

### Opciones adicionales de HTTPv1 {#additional-options}

| Parámetro | Descripción |
|---------|---------|
| **[!UICONTROL Ticker]** | Configure el texto del valor de la notificación. Solo está disponible para dispositivos configurados con Android 5.0 Lollipop. |
| **[!UICONTROL Sticky]** | Cuando se activa, la notificación permanece visible incluso después de que el usuario haga clic en ella. <br>Si se desactiva, la notificación se descarta automáticamente cuando el usuario interactúa con ella. El comportamiento adhesivo permite que las notificaciones importantes persistan en la pantalla durante períodos más largos. |
| **[!UICONTROL Image]** | Configure la dirección URL de la imagen para que se muestre en la notificación. |
| **[!UICONTROL Notification Priority]** | Defina el nivel de prioridad de la notificación, que puede ser predeterminado, mínimo, bajo o alto. El nivel de prioridad determina la importancia y la urgencia de la notificación, lo que influye en cómo se muestra y si puede omitir determinada configuración del sistema. Para más información, consulte la [documentación de FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#notificationpriority). |
| **[!UICONTROL Notification Count]** | Configure el número de información nueva no leída que se mostrará directamente en el icono de la aplicación. Esto permite al usuario ver rápidamente el número de notificaciones pendientes. |
| **[!UICONTROL Visibility]** | Defina el nivel de visibilidad de la notificación, que puede ser pública, privada o secreta. El nivel de visibilidad determina la cantidad de contenido de la notificación que se muestra en la pantalla de bloqueo y en otras áreas confidenciales. Para obtener más información, consulte la [Documentación de FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#visibility). |
| **[!UICONTROL Application variables]** | Permite definir el comportamiento de las notificaciones. Estas variables son totalmente personalizables y se incluyen, ya que una parte de la carga útil de mensajes se envía al dispositivo móvil. |
