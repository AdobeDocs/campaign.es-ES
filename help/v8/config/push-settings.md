---
title: Integración del SDK de AEP y Campaign
description: Descubra cómo integrar el SDK móvil de Adobe Experience Platform con su aplicación
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: 251ce05310f158b0f9ebccc94b42686f892338b1
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 3%

---


# SDK de AEP + Campaign: configurar el canal de notificaciones push {#push-notification-configuration}

Antes de comenzar a enviar notificaciones push con Adobe Campaign, debe asegurarse de que las configuraciones e integraciones estén implementadas en la aplicación móvil y para las etiquetas en Adobe Experience Platform.

El SDK de Adobe Experience Platform Mobile proporciona API de integración del lado del cliente para sus móviles mediante SDK compatibles con Android y iOS.

Para configurar la aplicación con los SDK de Adobe Experience Platform Mobile, siga estos pasos:

1. Marque [requisitos previos](#before-starting)
1. Configure un [propiedad de etiqueta móvil](#launch-property) en la recopilación de datos de Adobe Experience Platform
1. Obtenga el SDK de Adobe Experience Platform Mobile como se detalla [en esta página](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}
1. (opcional) Habilite las métricas de registro y ciclo vital, tal como se detalla [en esta página](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}
1. (opcional) Añadir [Adobe Experience Platform Assurance para su aplicación](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} para validar la implementación
1. Seguir [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} para configurar los SDK de Adobe Experience Platform Mobile en la aplicación.
1. Instalación y configuración [Extensión de Adobe Campaign](#configure-extension) en la propiedad móvil
1. Configure los servicios móviles de iOS y Android en Adobe Campaign como se detalla [en esta página](../send/push.md#push-config).

Al final de esto, también debería haber creado y configurado una propiedad móvil en [!DNL Adobe Experience Platform Data Collection]. Generalmente creará una propiedad móvil para cada aplicación móvil que desee administrar. Obtenga información sobre cómo crear y configurar una propiedad móvil en [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

## Requisitos previos {#before-starting}

### Configuración de permisos {#setup-permissions}

Antes de crear una aplicación móvil, primero debe asegurarse de que tiene o asigna los permisos de usuario correctos para las etiquetas en Adobe Experience Platform. Los permisos de usuario para etiquetas en Adobe Experience Platform se asignan a usuarios a través de Adobe Admin Console. Obtenga más información en [Documentación de etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>La configuración push debe realizarla un usuario experto. Según el modelo de implementación y las personas implicadas en esta implementación, es posible que tenga que asignar el conjunto completo de permisos a un único perfil de producto o compartir permisos entre el desarrollador de la aplicación y el **Adobe Campaign** administrador.

Para asignar **Propiedad** y **Empresa** , siga los pasos a continuación:

1. Acceda a la **[!DNL Admin Console]**.
1. En el **[!UICONTROL Products]** , seleccione **[!UICONTROL Adobe Experience Platform Data Collection]** tarjeta.
1. Seleccione una **[!UICONTROL Product Profile]** o cree uno nuevo con la variable **[!UICONTROL New profile]** botón. Obtenga información sobre cómo crear una nueva **[!UICONTROL New profile]** en el [Documentación de Admin Console](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. En la pestaña **[!UICONTROL Permissions]**, seleccione **[!UICONTROL Property Rights]**.
1. Haga clic en **[!UICONTROL Add all]**. Esto agregará lo siguiente al perfil de su producto:
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

   Estos permisos son necesarios para que el desarrollador de aplicaciones móviles configure credenciales push en **Recopilación de datos de Adobe Experience Platform**.

1. Haga clic en **[!UICONTROL Save]**.

Para asignar **[!UICONTROL Product profile]** para los usuarios, siga los pasos a continuación:

1. Acceda a la **[!DNL Admin Console]**.
1. En el **[!UICONTROL Products]** , seleccione **[!UICONTROL Adobe Experience Platform Data Collection]** tarjeta.
1. Seleccione el **[!UICONTROL Product profile]** configurado anteriormente.
1. En la pestaña **[!UICONTROL Users]**, haga clic en **[!UICONTROL Add user]**.
1. Escriba el nombre o la dirección de correo electrónico del usuario y seleccione el usuario. A continuación, haga clic en **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si el usuario no se ha creado anteriormente en Admin Console, consulte la [Agregar documentación de usuarios](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### Configurar su aplicación {#configure-app}

La configuración técnica implica una estrecha colaboración entre el desarrollador de la aplicación y el administrador empresarial. Antes de empezar a enviar notificaciones push con [!DNL Adobe Campaign], debe definir la configuración en [!DNL Adobe Experience Platform Data Collection] e integre su aplicación móvil con los SDK para móviles de Adobe Experience Platform.

Siga los pasos de implementación detallados en los vínculos siguientes:

* Para **Apple iOS**: Obtenga información sobre cómo registrar su aplicación con APNS en [Documentación de Apple](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
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

## Configuración de una propiedad de etiqueta móvil en la recopilación de datos de Adobe Experience Platform {#launch-property}

La configuración de una propiedad móvil permite que el desarrollador de aplicaciones móviles o el especialista en marketing configuren atributos de SDK móviles, como Tiempos de espera de sesión, el [!DNL Adobe Experience Platform] entorno limitado al que se va a dirigir y **[!UICONTROL Adobe Experience Platform Datasets]** que se utilizará para que el SDK móvil envíe datos a .

Para obtener más información y procedimientos sobre cómo configurar un **propiedad móvil** , consulte los pasos detallados en [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

Para que los SDK necesarios para que funcione la notificación push, necesitará las siguientes extensiones de SDK, tanto para Android como para iOS:

* **[!UICONTROL Mobile Core]** (instalado automáticamente)
* **[!UICONTROL Profile]** (instalado automáticamente)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, opcional pero recomendado para depurar la implementación móvil.

Más información sobre [!DNL Adobe Experience Platform Data Collection] etiquetas de [Documentación de Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Una vez creada, abra la nueva propiedad tag y cree una biblioteca. Para ello, haga lo siguiente:

1. Vaya a **Flujo de publicación** en el panel de navegación izquierdo y seleccione **Agregar biblioteca**.
1. Introduzca el nombre de la biblioteca y seleccione el entorno .
1. Select **Agregar todos los recursos modificados** y **Guardar y crear en desarrollo**.
1. Finalmente, establezca esta biblioteca como su biblioteca de trabajo desde **Seleccionar una biblioteca de trabajo** botón.


## Configurar la extensión de Adobe Campaign en la propiedad móvil {#configure-extension}

La variable **Extensión de Adobe Campaign Classic** para los SDK de Adobe Experience Platform Mobile , alimenta las notificaciones push para sus aplicaciones móviles y le ayuda a recopilar tokens push de usuario y a administrar la medición de interacciones con los servicios de Adobe Experience Platform.

Esta extensión está preinstalada en el entorno y debe configurarse. Para configurar la extensión de la propiedad de etiqueta móvil, siga estos pasos:

1. Abra la propiedad de etiqueta que creó anteriormente.
1. Desde el panel de navegación izquierdo, vaya a **Extensiones** y abra el **Catálogo** pestaña . Utilice el campo de búsqueda para buscar la variable **Adobe Campaign Classic** extensión.
1. En la tarjeta del Campaign Classic, haga clic en el **Instalar** botón.
1. Introduzca la configuración tal como se describe en [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Ahora puede agregar Campaign a su aplicación, tal como se detalla en  [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Configurar los servicios móviles en Campaign{#push-service}

Una vez que la aplicación móvil se haya configurado en [!DNL Adobe Experience Platform Data Collection], debe crear dos servicios (uno para dispositivos iOS y otro para dispositivos Android) para poder enviar notificaciones push desde **[!DNL Adobe Campaign]**.

Obtenga información sobre cómo crear y configurar un servicio para las notificaciones push de iOS y Android en [esta sección](../send/push.md#push-config).
