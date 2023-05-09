---
title: Integración del SDK de AEP y Campaign
description: Descubra cómo integrar el SDK móvil de Adobe Experience Platform con su aplicación
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e3ea361cc486096fe6c19ac469e8a71b636371ac
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 3%

---


# SDK de AEP + Campaign: configurar el canal de notificaciones push {#push-notification-configuration}

Antes de comenzar a enviar notificaciones push con Adobe Campaign, debe asegurarse de que las configuraciones e integraciones estén implementadas en la aplicación móvil y para las etiquetas en Adobe Experience Platform...... .... ....


## Antes de empezar {#before-starting}

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

### Integración de la aplicación móvil con el SDK de Adobe Experience Platform {#integrate-mobile-app}

El SDK de Adobe Experience Platform Mobile proporciona API de integración del lado del cliente para sus móviles mediante SDK compatibles con Android y iOS. Seguir [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} para configurar los SDK de Adobe Experience Platform Mobile en la aplicación.

Al final de esto, también debería haber creado y configurado una propiedad móvil en [!DNL Adobe Experience Platform Data Collection]. Generalmente creará una propiedad móvil para cada aplicación móvil que desee administrar. Obtenga información sobre cómo crear y configurar una propiedad móvil en [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.


## Paso 1: Añadir las credenciales push de la aplicación en la recopilación de datos de Adobe Experience Platform {#push-credentials}

Después de conceder los permisos de usuario correctos, debe agregar las credenciales push de la aplicación móvil en la recopilación de datos de Adobe Experience Platform.

El registro de credenciales push de la aplicación móvil es necesario para autorizar al Adobe a enviar notificaciones push en su nombre. Consulte los pasos detallados a continuación:

1. De [!DNL Adobe Experience Platform Data Collection], vaya a **[!UICONTROL App Surfaces]** en el carril izquierdo.

1. Haga clic en **[!UICONTROL Create App Surface]** para crear una configuración nueva.

1. Escriba un **[!UICONTROL Name]** para la configuración.

1. De **[!UICONTROL Mobile Application Configuration]**, seleccione Sistema operativo:

   * **Para iOS**

      1. Introduzca la aplicación móvil **Id De Paquete** en el **[!UICONTROL App ID (iOS Bundle ID)]** campo . El ID del paquete de la aplicación se puede encontrar en la variable **General** de la segmentación principal en **XCode**.

      1. Se ha activado la función **[!UICONTROL Push Credentials]** para añadir las credenciales.

      1. Arrastre y suelte el archivo .p8 Apple Push Notification Authentication Key. Esta clave se puede adquirir desde la **Certificados**, **Identificadores** y **Perfiles** página.

      1. Proporcione la variable **ID de clave**. Es una cadena de 10 caracteres asignada durante la creación de la clave de autenticación p8. Se encuentra en **Claves** en **Certificados**, **Identificadores** y **Perfiles** página.

      1. Proporcione la variable **ID del equipo**. Este es un valor de cadena que se puede encontrar en la pestaña Membership .
   * **Para Android**

      1. Proporcione la variable **[!UICONTROL App ID (Android package name)]**: normalmente, el nombre del paquete es el id de la aplicación en su `build.gradle` archivo.

      1. Se ha activado la función **[!UICONTROL Push Credentials]** para añadir las credenciales.

      1. Arrastre y suelte las credenciales push de FCM. Para obtener más información sobre cómo obtener las credenciales push, consulte [Documentación de Google](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.



1. Haga clic en **[!UICONTROL Save]** para crear la configuración de la aplicación.


## Paso 2: Configuración de una propiedad de etiqueta móvil en la recopilación de datos de Adobe Experience Platform {#launch-property}

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


## Paso 3: Configurar la extensión de Adobe Campaign en la propiedad móvil {#configure-extension}

La variable **Extensión de Adobe Campaign Classic** para los SDK de Adobe Experience Platform Mobile , alimenta las notificaciones push para sus aplicaciones móviles y le ayuda a recopilar tokens push de usuario y a administrar la medición de interacciones con los servicios de Adobe Experience Platform.

Esta extensión está preinstalada en el entorno y debe configurarse. Para configurar la extensión de la propiedad de etiqueta móvil, siga estos pasos:

1. Abra la propiedad de etiqueta que creó anteriormente.
1. Desde el panel de navegación izquierdo, vaya a **Extensiones** y abra el **Catálogo** pestaña . Utilice el campo de búsqueda para buscar la variable **Adobe Campaign Classic** extensión.
1. En la tarjeta del Campaign Classic, haga clic en el **Instalar** botón.
1. Introduzca la configuración tal como se describe en [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Ahora puede agregar Campaign a su aplicación, tal como se detalla en  [Documentación del SDK de Adobe Experience Platform Mobile](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Paso 4: Configurar los servicios móviles en Campaign{#push-service}

Una vez que la aplicación móvil se haya configurado en [!DNL Adobe Experience Platform Data Collection], debe crear dos servicios (uno para dispositivos iOS y otro para dispositivos Android) para poder enviar notificaciones push desde **[!DNL Adobe Campaign]**.

Obtenga información sobre cómo crear y configurar un servicio para las notificaciones push de iOS y Android en [esta sección](../send/push.md#push-config).
