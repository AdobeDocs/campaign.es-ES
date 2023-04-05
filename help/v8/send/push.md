---
title: Envío de notificaciones push con Adobe Campaign
description: Introducción a las notificaciones push en Campaign
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 1bcb1b3d1e6062a8b5c0368725248edfc7e3d1b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Creación y envío de notificaciones push{#push-notifications-create}

Los envíos de aplicaciones móviles permiten enviar notificaciones a dispositivos iOS y Android.

Para enviar notificaciones push en Adobe Campaign, debe:

1. Integre el SDK con la aplicación. [Más información](#push-sdk)
1. Cree un servicio de información de tipo Mobile application para su aplicación móvil y añada las versiones iOS y Android de la aplicación a ese servicio. [Más información](#push-config)
1. Cree un envío tanto para iOS como para Android. [Más información](#push-create)

## Integración del SDK {#push-sdk}

Puede utilizar el SDK de Adobe Experience Platform Mobile configurando la extensión de Adobe Campaign en la interfaz de usuario de recopilación de datos. El SDK móvil de Adobe Experience Platform impulsa las soluciones y los servicios Experience Cloud de Adobe en sus aplicaciones móviles. La configuración de los SDK se administra mediante la interfaz de usuario de recopilación de datos para lograr una configuración flexible e integraciones ampliables basadas en reglas. [Obtenga más información en la documentación de Adobe Developer](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.

También puede integrar el SDK de Campaign para facilitar la integración de la aplicación móvil en la plataforma Adobe Campaign. Las versiones compatibles del SDK se enumeran en [Matriz de compatibilidad de Campaign](../start/compatibility-matrix.md#MobileSDK).

Obtenga información sobre cómo integrar los SDK de iOS y Android de Campaign con su aplicación en [esta página](../config/push-config.md)

## Configuración de la aplicación en Campaign{#push-config}

Antes de enviar notificaciones push, debe definir la configuración de las aplicaciones de iOS y Android en Adobe Campaign.

Las notificaciones push se envían a los usuarios de la aplicación a través de un servicio dedicado. Cuando los usuarios instalan la aplicación, se suscriben a este servicio: Adobe Campaign se basa en este servicio para dirigirse solo a los suscriptores de su aplicación. En este servicio, debe añadir sus aplicaciones de iOS y Android para enviar en dispositivos iOS y Android.

Para crear un servicio para enviar notificaciones push, siga los pasos a continuación:

1. Vaya a **[!UICONTROL Profiles and Targets > Services and Subscriptions]** y haga clic en **[!UICONTROL Create]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. Escriba un **[!UICONTROL Label]** y **[!UICONTROL Internal name]** y seleccione un **[!UICONTROL Mobile application]** tipo .

   >[!NOTE]
   >
   >La asignación de destino predeterminada **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** está relacionada con la tabla de destinatarios. Si desea utilizar una asignación de destinatario diferente, debe crear una nueva asignación de destino e introducirla en el campo **[!UICONTROL Target mapping]** del servicio. Obtenga más información sobre las asignaciones de destino en [esta página](../audiences/target-mappings.md).

1. A continuación, utilice el **[!UICONTROL Add]** a la derecha para definir las aplicaciones móviles que utilizan este servicio.

>[!BEGINTABS]

>[!TAB iOS]

Para crear una aplicación para dispositivos iOS, siga estos pasos:

1. Seleccione **[!UICONTROL Create an iOS application]** y haga clic en **[!UICONTROL Next]**.

   ![](assets/new-ios-app.png){width="600" align="left"}

1. Introduzca el nombre de su aplicación en la **[!UICONTROL Label]** campo .
1. (opcional) Puede enriquecer el contenido de un mensaje push con algunas **[!UICONTROL Application variables]**. Son totalmente personalizables y una parte de la carga útil de mensajes se envía al dispositivo móvil.

   En el ejemplo siguiente, la variable **mediaURl** y **mediaExt** se añaden para crear notificaciones push enriquecidas y, a continuación, proporcionan a la aplicación la imagen que se muestra en la notificación.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. Vaya a la **[!UICONTROL Subscription parameters]** para definir la asignación con una extensión de la pestaña **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** esquema.

1. Vaya a la **[!UICONTROL Sounds]** para definir un sonido que reproducir. Haga clic en **[!UICONTROL Add]** y rellene el campo **[!UICONTROL Internal name]** que debe contener el nombre del archivo incrustado en la aplicación o el nombre del sonido del sistema.

1. Haga clic en **[!UICONTROL Next]** para comenzar a configurar la aplicación de desarrollo.

1. La clave de integración es específica para cada aplicación. Vincula la aplicación móvil con Adobe Campaign.

   Asegúrese de que la misma **[!UICONTROL Integration key]** se define en Adobe Campaign y en el código de la aplicación a través del SDK.

   Si utiliza el SDK de Campaign, obtenga más información en[esta página](../config/push-config.md).


   Si utiliza el SDK de Adobe Experience Platform (recopilación de datos), obtenga más información en [esta página](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]** es totalmente personalizable con un valor de cadena, pero debe ser exactamente igual al especificado en el SDK.
   >
   > No se puede usar el mismo certificado para la versión de desarrollo (entorno limitado) y la versión de producción de la aplicación.

1. Seleccione el icono de la lista **[!UICONTROL Application icon]** para personalizar la aplicación móvil en el servicio.

1. Seleccione el **[!UICONTROL Authentication mode]**. Hay dos modos disponibles:

   * (Recomendado) **[!UICONTROL Token-based authentication]**: Complete la configuración de conexión de APNS **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** y **[!UICONTROL Bundle Id]** a continuación, seleccione el certificado p8 haciendo clic en **[!UICONTROL Enter the private key...]**. Para más información sobre **[!UICONTROL Token-based authentication]**, consulte la [documentación de Apple](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Certificate-based authentication]**: haga clic en **[!UICONTROL Enter the certificate...]**, seleccione la clave p12 e introduzca la contraseña proporcionada por el desarrollador de aplicaciones móviles.
   Puede cambiar el modo de autenticación más adelante en la sección **[!UICONTROL Certificate]** de la aplicación móvil.

1. Utilice la variable **[!UICONTROL Test the connection]** para validar la configuración.

1. Haga clic en **[!UICONTROL Next]** para configurar la aplicación de producción y siga los mismos pasos detallados anteriormente.

1. Haga clic en **[!UICONTROL Finish]**.

La aplicación de iOS ya está lista para su uso en Campaign.

>[!TAB Android]

Para crear una aplicación para dispositivos Android, siga estos pasos:

1. Seleccione **[!UICONTROL Create an Android application]** y haga clic en **[!UICONTROL Next]**.

   ![](assets/new-android-app.png){width="600" align="left"}

1. Introduzca el nombre de su aplicación en la **[!UICONTROL Label]** campo .
1. La clave de integración es específica para cada aplicación. Vincula la aplicación móvil con Adobe Campaign.

   Asegúrese de que la misma **[!UICONTROL Integration key]** se define en Adobe Campaign y en el código de la aplicación a través del SDK.

   Si utiliza el SDK de Campaign, obtenga más información en [esta página](../config/push-config.md).

   Si utiliza el SDK de Adobe Experience Platform (recopilación de datos), obtenga más información en [esta página](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]** es totalmente personalizable con un valor de cadena, pero debe ser exactamente igual al especificado en el SDK.

1. Seleccione el icono de la lista **[!UICONTROL Application icon]** para personalizar la aplicación móvil en el servicio.
1. Select **HTTP v1** en  **[!UICONTROL API version]** lista desplegable.
1. Haga clic en **[!UICONTROL Load project json file to extract project details...]** enlace para cargar el archivo de clave JSON. Para obtener más información sobre cómo extraer el archivo JSON, consulte [Documentación de Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   También puede introducir manualmente los siguientes detalles:
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. Utilice la variable **[!UICONTROL Test the connection]** para validar la configuración.

   >[!CAUTION]
   >
   >La variable **[!UICONTROL Test connection]** no comprueba si el servidor MID tiene acceso al servidor FCM.

1. (opcional) Puede enriquecer el contenido de un mensaje push con algunas **[!UICONTROL Application variables]** si es necesario. Son totalmente personalizables y una parte de la carga útil de mensajes se envía al dispositivo móvil.

1. Haga clic en **[!UICONTROL Finish]**, luego en **[!UICONTROL Save]**. La aplicación de Android ya está lista para su uso en Campaign.

A continuación se muestran los nombres de carga útil de FCM para personalizar aún más la notificación push:

| Tipo de mensaje | Elemento de mensaje configurable (nombre de carga útil de FCM) | Opciones configurables (nombre de carga útil de FCM) |
|:-:|:-:|:-:|
| mensaje de datos | N/A | validate_only |
| mensaje de notificación | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]


## Creación de la primera notificación push{#push-create}

En esta sección se detallan los elementos específicos para la entrega de notificaciones en iOS y Android.

>[!CAUTION]
>
>En el contexto de un [Implementación empresarial (FFDA)](../architecture/enterprise-deployment.md), el registro móvil está ahora **asincrónico**. [Más información](../architecture/staging.md)

Para crear un nuevo envío, vaya a la **[!UICONTROL Campaigns]** , haga clic en **[!UICONTROL Deliveries]** y haga clic en el botón **[!UICONTROL Create]** situado encima de la lista de envíos existentes.

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

Para enviar notificaciones en dispositivos iOS, siga estos pasos:

1. Seleccione la plantilla de envíos **[!UICONTROL Deliver on iOS]**.

   ![](assets/push_ios_1.png)

1. Para definir el objetivo de la notificación, haga clic en el enlace **[!UICONTROL To]** y, luego, en **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. Select **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, seleccione el servicio correspondiente a su aplicación móvil y, a continuación, seleccione la versión de iOS de la aplicación.

   ![](assets/push_ios_3.png)

1. Elija su **[!UICONTROL Notification type]** entre **[!UICONTROL General notification (Alert, Sound, Badge)]** o **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >El modo **Push silenciosa** permite enviar una notificación “silenciosa” a una aplicación móvil. No se avisa al usuario de la llegada de la notificación. Esta se transfiere directamente a la aplicación.

1. En el campo **[!UICONTROL Title]**, introduzca la etiqueta del título que desea que aparezca en la lista de notificaciones disponibles en el centro de notificaciones.

   Este campo permite definir el valor del parámetro **title** de la carga útil de notificación de iOS.

1. Puede añadir un **[!UICONTROL Subtitle]**, valor del parámetro subtítulo de la carga útil de notificación de iOS.****

1. Introduzca el contenido del mensaje en la sección **[!UICONTROL Message content]** del asistente.

1. En la pestaña **[!UICONTROL Sound and Badge]**, puede editar las siguientes opciones:

   * **[!UICONTROL Clean Badge]**: active estas opciones para actualizar el valor del distintivo.

   * **[!UICONTROL Value]**: establezca un número que se utilizará para mostrar directamente en el icono de la aplicación la cantidad de información nueva no leída.

   * **[!UICONTROL Critical alert mode]**: habilite esta opción para agregar sonido a la notificación, incluso si el teléfono del usuario está activado o si el iPhone está silenciado.

   * **[!UICONTROL Name]**: seleccione el sonido que el terminal móvil debe reproducir cuando reciba la notificación.

   * **[!UICONTROL Volume]**: volumen de su sonido de 0 a 100.

      >[!NOTE]
      > 
      >Los sonidos deben incluirse en la aplicación y definirse cuando se cree el servicio.
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

      * **[!UICONTROL Time sensitive]** el sistema presenta la notificación inmediatamente, enciende la pantalla, puede reproducir un sonido y atravesar los modos de Enfoque. Este nivel no requiere un permiso especial de Apple.

      * **[!UICONTROL Critical]** el sistema presenta la notificación inmediatamente, enciende la pantalla y evita el interruptor silencioso o los modos de enfoque. Tenga en cuenta que este nivel requiere un permiso especial de Apple.
   * **[!UICONTROL Relevance score]**: establezca una puntuación de relevancia de 0 a 100. El sistema utiliza esto para ordenar las notificaciones en el resumen de notificaciones.

   ![](assets/push_ios_7.png)

1. Una vez configurada la notificación, haga clic en la pestaña **[!UICONTROL Preview]** para previsualizar la notificación.

   ![](assets/push-ios-preview.png)


>[!TAB Android]

Para enviar notificaciones en dispositivos Android, siga estos pasos:

1. Seleccione la plantilla de envíos **[!UICONTROL Deliver on Android (android)]**.

   ![](assets/push-template-android.png)

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


## Prueba, envío y monitorización de las notificaciones push

Para enviar una prueba y realizar la entrega final, utilice el mismo proceso que para otros envíos.

Obtenga información sobre cómo validar una entrega en [esta página](preview-and-proof.md).

Obtenga información sobre cómo confirmar y realizar la entrega en [esta página](send.md)

Después de enviar mensajes, puede monitorizar y realizar un seguimiento de las entregas. Obtenga más información sobre los motivos de error de entrega de notificaciones push en [esta página](delivery-failures.md#push-error-types).

