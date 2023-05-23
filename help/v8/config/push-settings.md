---
title: Integración del SDK de AEP y Campaign
description: Obtenga información sobre cómo integrar el SDK móvil de Adobe Experience Platform con su aplicación
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: ff6990f3db1122670bff4919f417b9f9f04d3183
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 3%

---


# SDK de AEP + Campaign: configurar el canal de notificaciones push {#push-notification-configuration}

Antes de empezar a enviar notificaciones push con Adobe Campaign, debe asegurarse de que las configuraciones y integraciones estén implementadas en la aplicación móvil y para las etiquetas en Adobe Experience Platform.

El SDK de Adobe Experience Platform Mobile proporciona API de integración del lado del cliente para sus móviles a través de SDK compatibles con Android y iOS.

Para configurar la aplicación con los SDK para móviles de Adobe Experience Platform, siga estos pasos:

1. Marque [requisitos previos](#before-starting).
1. Configuración de un [propiedad de etiqueta móvil](#launch-property) en Recopilación de datos de Adobe Experience Platform.
1. Obtenga el SDK de Adobe Experience Platform Mobile tal como se detalla [en esta página](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (Opcional) Habilite el registro y las métricas del ciclo vital, tal como se detalla a continuación [en esta página](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (opcional) Agregar [Adobe Experience Platform Assurance en la aplicación](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. Seguir [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} para configurar los SDK de Adobe Experience Platform Mobile en la aplicación.
1. Instalación y configuración [Extensión de Adobe Campaign](#configure-extension) en su propiedad móvil.
1. Configure los servicios móviles de iOS y Android en Adobe Campaign según se detalla [en esta página](../send/push.md#push-config).


## Requisitos previos {#before-starting}

### Configuración de permisos {#setup-permissions}

Antes de crear una aplicación móvil, primero debe asegurarse de que tiene o asigna los permisos de usuario correctos para las etiquetas en Adobe Experience Platform. Los permisos de usuario para las etiquetas en Adobe Experience Platform se asignan a los usuarios a través de Adobe Admin Console. Obtenga más información en [Documentación de etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>La configuración push la debe realizar un usuario experto. Según el modelo de implementación y las personas involucradas en esta implementación, es posible que tenga que asignar el conjunto completo de permisos a un único perfil de producto o compartir permisos entre el desarrollador de aplicaciones y **Adobe Campaign** administrador.

Para asignar **Propiedad** y **Compañía** derechos, siga los pasos a continuación:

1. Acceda a la **[!DNL Admin Console]**.
1. Desde el **[!UICONTROL Products]** , seleccione la pestaña **[!UICONTROL Adobe Experience Platform Data Collection]** Tarjeta de.
1. Seleccionar un existente **[!UICONTROL Product Profile]** o cree uno nuevo con la variable **[!UICONTROL New profile]** botón. Obtenga información sobre cómo crear un nuevo **[!UICONTROL New profile]** en el [Documentación de Admin Console](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. En la pestaña **[!UICONTROL Permissions]**, seleccione **[!UICONTROL Property Rights]**.
1. Haga clic en **[!UICONTROL Add all]**. Esto añadirá el siguiente derecho a su perfil de producto:
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   Estos permisos son necesarios para instalar y publicar la extensión de Adobe Campaign y publicar la propiedad de la aplicación en **SDK de Adobe Experience Platform Mobile**.

1. A continuación, seleccione **[!UICONTROL Company rights]** en el menú de la izquierda.
1. Añada los siguientes derechos:

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   Estos permisos son necesarios para que el desarrollador de aplicaciones móviles pueda configurar las credenciales push en **Recopilación de datos de Adobe Experience Platform**.

1. Haga clic en **[!UICONTROL Save]**.

Para asignar esto **[!UICONTROL Product profile]** para los usuarios de, siga los pasos a continuación:

1. Acceda a la **[!DNL Admin Console]**.
1. Desde el **[!UICONTROL Products]** , seleccione la pestaña **[!UICONTROL Adobe Experience Platform Data Collection]** Tarjeta de.
1. Seleccione el **[!UICONTROL Product profile]** configurado anteriormente.
1. En la pestaña **[!UICONTROL Users]**, haga clic en **[!UICONTROL Add user]**.
1. Escriba el nombre o la dirección de correo electrónico del usuario y seleccione el usuario. A continuación, haga clic en **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si el usuario no se ha creado anteriormente en Admin Console, consulte la [Documentación de Adición de usuarios](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### Configurar su aplicación {#configure-app}

La configuración técnica implica una estrecha colaboración entre el desarrollador de la aplicación y el administrador empresarial. Antes de empezar a enviar notificaciones push con [!DNL Adobe Campaign], debe definir la configuración en [!DNL Adobe Experience Platform Data Collection] e integre su aplicación móvil con los SDK para móviles de Adobe Experience Platform.

Siga los pasos de implementación detallados en los vínculos siguientes:

* Para **Apple iOS**: Obtenga información sobre cómo registrar la aplicación con APNS en [Documentación de Apple](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* Para **Google Android**: Obtenga información sobre cómo configurar una aplicación cliente de Firebase Cloud Messaging en Android en [Documentación de Google](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

<!--
## Add your app push credentials in Adobe Experience Platform Data Collection {#push-credentials}

After granting the correct user permissions, you now need to add your mobile application push credentials in Adobe Experience Platform Data Collection. 

The mobile app push credential registration is required to authorize Adobe to send push notifications on your behalf. Refer to the steps detailed below:

1. From [!DNL Adobe Experience Platform Data Collection], browse to **[!UICONTROL App Surfaces]** in the left rail.

1. Click **[!UICONTROL Create App Surface]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From **[!UICONTROL Mobile Application Configuration]**, select the system and enter settings.

    * **For iOS**

        1. Enter the mobile app **Bundle Id** in the **[!UICONTROL App ID (iOS Bundle ID)]** field. The app Bundle ID can be found in the **General** tab of the primary target in **XCode**.
        
        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.
        
        1. Drag and drop your .p8 Apple Push Notification Authentication Key file. This key can be acquired from the **Certificates**, **Identifiers** and **Profiles** page.

        1. Provide the **Key ID**. This is a 10 character string assigned during the creation of p8 auth key. It can be found under **Keys** tab in **Certificates**, **Identifiers** and **Profiles** page.
        
        1. Provide the **Team ID**. This is a string value which can be found under the Membership tab.

    * **For Android**

        1. Provide the **[!UICONTROL App ID (Android package name)]**: usually the package name is the app id in your `build.gradle` file.

        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.

        1. Drag and drop the FCM push credentials. For more details on how to get the push credentials refer to [Google Documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.
    

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

## Configuración de una propiedad de etiquetas móviles en la recopilación de datos de Adobe Experience Platform {#launch-property}

La configuración de una propiedad móvil permite al desarrollador o al experto en marketing de la aplicación móvil configurar los SDK móviles. Normalmente, creará una propiedad móvil para cada aplicación móvil que desee administrar. Obtenga información sobre cómo crear y configurar una propiedad móvil en [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

Más información sobre [!DNL Adobe Experience Platform Data Collection] etiquetas en [Documentación de Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Una vez creada, abra la nueva propiedad de etiqueta y cree una biblioteca. Para ello, haga lo siguiente:

1. Navegar a **Flujo de publicación** en el panel de navegación izquierdo y seleccione **Añadir biblioteca**.
1. Introduzca el nombre de la biblioteca y seleccione el entorno.
1. Seleccionar **Añadir todos los recursos modificados**, y **Guardar y generar en desarrollo**.
1. Finalmente, establezca esta biblioteca como su biblioteca de trabajo desde el **Seleccionar una biblioteca de trabajo** botón.


## Configuración de la extensión de Adobe Campaign en la propiedad móvil {#configure-extension}

El **Extensión de Adobe Campaign Classic** para los SDK de Adobe Experience Platform Mobile alimenta las notificaciones push de sus aplicaciones móviles y le ayuda a recopilar tokens push de usuario y a gestionar la medición de interacciones con los servicios de Adobe Experience Platform.

Esta extensión, que se aplica tanto a Campaign Classic v7 como a Campaign v8, está preinstalada en el entorno y debe configurarse. Para configurar la extensión para la propiedad de etiquetas móviles, siga estos pasos:

1. Abra la propiedad de etiquetas que creó anteriormente.
1. En el panel de navegación izquierdo, vaya a **Extensiones** y abra el **Catálogo** pestaña. Utilice el campo de búsqueda para encontrar la variable **Adobe Campaign Classic** extensión.
1. En la tarjeta de Campaign Classic, haga clic en **Instalar** botón.
1. Introduzca la configuración tal como se describe en [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Ahora puede añadir Campaign a la aplicación, tal como se detalla en  [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Configuración de los servicios móviles en Campaign{#push-service}

Una vez configurada la aplicación móvil en en, [!DNL Adobe Experience Platform Data Collection], debe crear dos servicios (uno para dispositivos iOS y otro para Android) desde los que poder enviar notificaciones push **[!DNL Adobe Campaign]**.

Obtenga información sobre cómo crear y configurar un servicio para notificaciones push de iOS y Android en [esta sección](../send/push.md#push-config).
