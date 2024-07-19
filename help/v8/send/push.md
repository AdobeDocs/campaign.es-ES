---
title: Envío de una notificación push con Adobe Campaign
description: Introducción a las notificaciones push en Campaign
feature: Push
role: User
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 48aba38f3dc8bb322e6d0b38c1b743e980671cd7
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 61%

---

# Creación y envío de notificaciones push{#push-notifications-create}

Las entregas de aplicaciones móviles permiten enviar notificaciones a dispositivos iOS y Android.

Antes de empezar a enviar notificaciones push con Adobe Campaign, debe asegurarse de que las configuraciones e integraciones estén implementadas en la aplicación móvil y para las etiquetas en Adobe Experience Platform. [Más información acerca de la configuración de inserción.](push-settings.md).

>[!CAUTION]
>
>Algunos cambios importantes en el servicio Android Firebase Cloud Messaging (FCM) se lanzarán en 2024 y pueden afectar a su implementación de Adobe Campaign. Es posible que sea necesario actualizar la configuración de los servicios de suscripción para los mensajes push de Android a fin de que admitan este cambio. Ya puede comprobar y realizar acciones. [Más información](../../technotes/upgrades/push-technote.md).


## Creación de la primera notificación push {#push-create}

En esta sección se detallan los elementos específicos para el envío de notificaciones en iOS y Android.

>[!IMPORTANT]
>
>En el contexto de una implementación [empresarial (FDAC)](../architecture/enterprise-deployment.md), el registro móvil es ahora **asincrónico**. [Más información](../architecture/staging.md)


Para crear una entrega nueva, vaya a la pestaña **[!UICONTROL Campaigns]**, haga clic en **[!UICONTROL Deliveries]** y luego en el botón **[!UICONTROL Create]** situado sobre la lista de entregas existentes.

![](assets/delivery_step_1.png)


De forma predeterminada, Adobe Campaign incluye dos plantillas de envío: una para iOS y otra para Android. Puede duplicarlas para definir su propia configuración. A continuación se detallan los pasos para configurar una entrega push basada en estas plantillas.

>[!BEGINTABS]

>[!TAB iOS]

Para enviar notificaciones en dispositivos iOS, siga estos pasos:

1. Seleccione la plantilla de envíos **[!UICONTROL Deliver on iOS]**.

   ![](assets/push_ios_1.png)

1. Para definir el objetivo de la notificación, haga clic en el enlace **[!UICONTROL To]** y, luego, en **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. Seleccione **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, seleccione el servicio correspondiente a su aplicación móvil y, a continuación, seleccione la versión de iOS de la aplicación.

   ![](assets/push_ios_3.png)

1. Elija su **[!UICONTROL Notification type]** entre **[!UICONTROL General notification (Alert, Sound, Badge)]** o **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >El modo **Push silenciosa** permite enviar una notificación “silenciosa” a una aplicación móvil. No se avisa al usuario de la llegada de la notificación. Esta se transfiere directamente a la aplicación.

1. En el campo **[!UICONTROL Title]**, introduzca la etiqueta del título que desea que aparezca en la lista de notificaciones disponibles en el centro de notificaciones.

   Este campo permite definir el valor del parámetro **title** de la carga útil de notificación de iOS.

1. Puede agregar un **[!UICONTROL Subtitle]**, valor del parámetro **subtitle** de la carga útil de notificaciones de iOS.

1. Escriba el contenido del mensaje en la sección **[!UICONTROL Message content]** del asistente.

1. En la pestaña **[!UICONTROL Sound and Badge]**, puede editar las siguientes opciones:

   * **[!UICONTROL Clean Badge]**: active estas opciones para actualizar el valor del distintivo.

   * **[!UICONTROL Value]**: establezca un número que se utilizará para mostrar directamente en el icono de la aplicación la cantidad de información nueva no leída.

   * **[!UICONTROL Critical alert mode]**: habilite esta opción para agregar sonido a la notificación, incluso si el teléfono del usuario está activado o si el iPhone está silenciado.

   * **[!UICONTROL Name]**: seleccione el sonido que el terminal móvil debe reproducir cuando reciba la notificación.

   * **[!UICONTROL Volume]**: volumen de su sonido de 0 a 100.

     >[!NOTE]
     > 
     >Los sonidos deben incluirse en la aplicación y definirse cuando se cree el servicio.
     >

   ![](assets/push_ios_5.png)

1. En la pestaña **[!UICONTROL Application variables]**, **[!UICONTROL Application variables]** se añaden automáticamente. Permiten definir el comportamiento de las notificaciones: por ejemplo, se puede configurar una pantalla específica de la aplicación que aparece cuando el usuario activa la notificación.

1. En la pestaña **[!UICONTROL Advanced]**, puede editar las siguientes opciones generales:

   * **[!UICONTROL Mutable content]**: active esta opción para permitir que la aplicación móvil descargue contenido multimedia.

   * **[!UICONTROL Thread-id]**: identificador utilizado para agrupar las notificaciones relacionadas.

   * **[!UICONTROL Category]**: nombre de su ID de categoría que mostrará botones de acción. Estas notificaciones proporcionan al usuario una forma más rápida de realizar distintas tareas en respuesta a una notificación sin necesidad de abrir ni navegar por la aplicación.

   ![](assets/push_ios_6.png)

1. Para las notificaciones con distinción de tiempo, puede especificar las siguientes opciones:

   * **[!UICONTROL Target content ID]**: identificador utilizado para destinar la ventana de aplicación que se reenvía cuando se abre la notificación.

   * **[!UICONTROL Launch image]**: nombre del archivo de imagen de lanzamiento que se va a mostrar. Si el usuario decide iniciar la aplicación, se mostrará la imagen seleccionada en lugar de la pantalla de inicio de la aplicación.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**: de forma predeterminada, el sistema presenta la notificación inmediatamente, ilumina la pantalla y puede reproducir un sonido. Las notificaciones no rompen los modos de Enfoque.

      * **[!UICONTROL Passive]**: el sistema agrega la notificación a la lista de notificaciones sin iluminar la pantalla ni reproducir un sonido. Las notificaciones no rompen los modos de Enfoque.

      * **[!UICONTROL Time sensitive]** El sistema presenta la notificación inmediatamente, enciende la pantalla, puede reproducir un sonido y atravesar los modos de Enfoque. Este nivel no requiere un permiso especial de Apple.

      * **[!UICONTROL Critical]** El sistema presenta la notificación inmediatamente, enciende la pantalla y evita el interruptor silencioso o los modos de enfoque. Tenga en cuenta que este nivel requiere un permiso especial de Apple.

   * **[!UICONTROL Relevance score]**: establezca una puntuación de relevancia de 0 a 100. El sistema utiliza esto para ordenar las notificaciones en el resumen de notificaciones.

   ![](assets/push_ios_7.png)

1. Una vez configurada la notificación, haga clic en la pestaña **[!UICONTROL Preview]** para previsualizar la notificación.

   ![](assets/push-ios-preview.png)


>[!TAB Android]

Para enviar notificaciones en dispositivos Android, siga estos pasos:

1. Seleccione la plantilla de envíos **[!UICONTROL Deliver on Android (android)]**.

   ![](assets/push-template-android.png)

   >[!NOTE]
   > 
   >Con las API de FCM más recientes (HTTP v1), debe actualizar las **plantillas de envío** para las notificaciones push de Android a fin de aumentar el número de mensajes por lotes. Para ello, vaya a las propiedades de la plantilla de envíos de Android y, en la pestaña **Envío**, establezca [Cantidad de lotes de mensajes](../../v8/send/configure-and-send.md#delivery-batch-quantity) en **256**. Aplique este cambio a todas las plantillas de envíos utilizadas para sus envíos de Android y a todas las entregas de Android existentes.


1. Para definir el objetivo de la notificación, haga clic en el enlace **[!UICONTROL To]** y, luego, en **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. Seleccione **[!UICONTROL Subscribers of an Android mobile application]**, elija el servicio correspondiente a su aplicación móvil (Neotrips, en este caso), y luego seleccione la versión de Android de la aplicación.

   ![](assets/push-android-subscribers.png)

1. A continuación, introduzca el contenido de la notificación.

   ![](assets/push-android-content.png)

1. Haga clic en el icono **[!UICONTROL Insert emoticon]** para insertar emoticonos en la notificación push.

1. En el campo **[!UICONTROL Application variables]**, introduzca el valor de cada variable. Por ejemplo, puede configurar una pantalla de aplicación específica para que se muestre cuando el usuario active la notificación.

1. Una vez configurada la notificación, haga clic en la pestaña **[!UICONTROL Preview]** para previsualizar la notificación.

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## Prueba, envío y monitorización de las notificaciones push {#push-test}

Para enviar una prueba y realizar la entrega final, utilice el mismo proceso que para los demás envíos.

Obtenga información sobre cómo validar un envío en [esta página](preview-and-proof.md).

Obtenga información sobre cómo confirmar y enviar la entrega en [esta página](send.md)

Después de enviar mensajes, puede monitorizar y realizar un seguimiento de las entregas. Obtenga más información acerca de las razones de error de entrega de notificaciones push en [esta página](delivery-failures.md#push-error-types).

