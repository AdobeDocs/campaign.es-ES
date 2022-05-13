---
title: Send push notification with Adobe Campaign
description: Get started with push notification in Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 9457652f62810eb401c4010acd9b5da42d88d796
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 29%

---

# Create and send push notifications

Mobile app deliveries let you send notifications to iOS and Android systems.

Para enviar notificaciones push en Adobe Campaign, debe:

1. Configure your Campaign environment
1. Create a Mobile application-type information service for your mobile application.
1. Añada a este servicio las versiones de iOS y Android de la aplicación.
1. Cree un envío tanto para iOS como para Android.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## Integración del SDK de Campaign

Campaign SDK facilitates the integration of your mobile application into the Adobe Campaign platform.

[](../start/compatibility-matrix.md#MobileSDK)

![](../assets/do-not-localize/glass.png)[](../config/push-config.md)

<!--
### Configure Campaign Extension in Launch

You can integrate Adobe Experience Platorm Launch SDK with Campaign, by leveraging Campaign Classic extension.

![](../assets/do-not-localize/book.png) Learn more in [Adobe Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic){target="_blank"}

-->

## Configure your app settings in Campaign

You must define your iOS and Android apps settings in Adobe Campaign.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=es#sending-messages)

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## Create your first push notification

En esta sección se detallan los elementos específicos para la entrega de notificaciones en iOS y Android.

>[!CAUTION]
>
>[](../architecture/enterprise-deployment.md)**** [Más información](../architecture/staging.md)

**[!UICONTROL Campaigns]****[!UICONTROL Deliveries]****[!UICONTROL Create]**

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages)

### Send notifications on iOS {#send-notifications-on-ios}

>[!NOTE]
>
>[](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

1. Seleccione la plantilla de envíos **[!UICONTROL Deliver on iOS]**.

   ![](assets/push_ios_1.png)

1. Para definir el objetivo de la notificación, haga clic en el enlace **[!UICONTROL To]** y, luego, en **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**

   ![](assets/push_ios_3.png)

1. **[!UICONTROL Notification type]****[!UICONTROL General notification (Alert, Sound, Badge)]****[!UICONTROL Silent notification]**

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >El modo **Push silenciosa** permite enviar una notificación “silenciosa” a una aplicación móvil. No se avisa al usuario de la llegada de la notificación. Esta se transfiere directamente a la aplicación.

1. **[!UICONTROL Title]**

   Este campo permite definir el valor del parámetro **title** de la carga útil de notificación de iOS.

1. **[!UICONTROL Subtitle]******

1. Introduzca el contenido del mensaje en la sección **[!UICONTROL Message content]** del asistente.

1. **[!UICONTROL Sound and Badge]**

   * **[!UICONTROL Clean Badge]**

   * **[!UICONTROL Value]**

   * **[!UICONTROL Critical alert mode]**

   * **[!UICONTROL Name]**

   * **[!UICONTROL Volume]**

      >[!NOTE]
      > 
      >Los sonidos deben incluirse en la aplicación y definirse cuando se cree el servicio.
      >
      >[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en)
   ![](assets/push_ios_5.png)

1. **[!UICONTROL Application variables]****[!UICONTROL Application variables]** They let you define notification behavior, for instance, you can configure a specific application screen to be displayed when the user activates the notification.

   Para obtener más información, consulte [esta sección](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en).

1. **[!UICONTROL Advanced]**

   * **[!UICONTROL Mutable content]**

   * **[!UICONTROL Thread-id]**

   * **[!UICONTROL Category]** Estas notificaciones proporcionan al usuario una forma más rápida de realizar distintas tareas en respuesta a una notificación sin necesidad de abrir ni navegar por la aplicación.

   ![](assets/push_ios_6.png)

1. For time sensitive notification, you can specify the following options:

   * **[!UICONTROL Target content ID]**

   * **[!UICONTROL Launch image]** If the user chooses to launch your application, the selected image will displayed instead of your application&#39;s launch screen.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]** Notifications do not break through Focus modes.

      * **[!UICONTROL Passive]** Notifications do not break through Focus modes.

      * **[!UICONTROL Time sensitive]** This level does not require a special permission from Apple.

      * **[!UICONTROL Critical]** Note that this level requires a special permission from Apple.
   * **[!UICONTROL Relevance score]** The system uses this to sort the notifications in the notification summary.

   ![](assets/push_ios_7.png)

1. Una vez configurada la notificación, haga clic en la pestaña **[!UICONTROL Preview]** para previsualizar la notificación.

   ![](assets/push-ios-preview.png)

### Send notifications on Android {#send-notifications-on-android}

1. Seleccione la plantilla de envíos **[!UICONTROL Deliver on Android (android)]**.

   ![](assets/push-template-android.png)

1. Para definir el objetivo de la notificación, haga clic en el enlace **[!UICONTROL To]** y, luego, en **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. Seleccione **[!UICONTROL Subscribers of an Android mobile application]**, elija el servicio correspondiente a su aplicación móvil (Neotrips, en este caso), y luego seleccione la versión de Android de la aplicación.

   ![](assets/push-android-subscribers.png)

1. A continuación, introduzca el contenido de la notificación.

   ![](assets/push-android-content.png)

1. Haga clic en el icono **[!UICONTROL Insert emoticon]** para insertar emoticonos en la notificación push.

1. En el campo **[!UICONTROL Application variables]**, introduzca el valor de cada variable. For example, you can configure a specific application screen to be displayed when the user activates the notification.

1. Una vez configurada la notificación, haga clic en la pestaña **[!UICONTROL Preview]** para previsualizar la notificación.

   <!--![](assets/push-android-preview.png)-->

## Test, send and monitor your push notifications

Para enviar una prueba y realizar la entrega final, utilice el mismo proceso que en las entregas por correo electrónico. Obtenga más información en la documentación de Campaign Classic v7:

* Validate a delivery and send proofs
   ![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

* Confirm and send the delivery
   ![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en)

Después de enviar mensajes, puede monitorizar y realizar un seguimiento de las entregas. Obtenga más información en la documentación de Campaign Classic v7:

* Cuarentenas de notificaciones push
   ![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines)

* Resolución de problemas
   ![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en)
