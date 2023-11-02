---
title: Envío de una notificación push con Adobe Campaign
description: Introducción a las notificaciones push en Campaign
feature: Push
role: Data Engineer
level: Intermediate
badge: label="Disponibilidad limitada" type="Informative"
exl-id: 0f22b17c-ed01-4add-8300-8689b8a9f963
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '1389'
ht-degree: 21%

---

# Configuración de notificaciones push revisada {#push-notifications-config}

La versión 8.5 de Campaign presenta nuestro último servicio de notificaciones push, con una estructura sólida basada en una tecnología moderna de vanguardia. Este servicio está diseñado para desbloquear nuevos niveles de escalabilidad, lo que garantiza que las notificaciones puedan llegar a una audiencia más grande con una eficiencia perfecta. Con nuestra infraestructura mejorada y los procesos optimizados, puede esperar una mayor escala y fiabilidad, lo que le permite interactuar y conectarse con los usuarios de sus aplicaciones móviles como nunca antes.

>[!AVAILABILITY]
>
> Esta función es accesible exclusivamente para los nuevos clientes a partir de la versión 8.5 de Campaign y se implementa progresivamente en un conjunto de clientes seleccionados. Si el entorno se ha aprovisionado antes de junio de 2023, esta página no se le aplica y debe seguir los procedimientos detallados [en esta página](push-settings.md).

En el contexto de esta implementación actualizada, para enviar notificaciones push en Adobe Campaign, siga estos pasos:

1. [Crear una superficie de aplicación en la recopilación de datos de Adobe Experience Platform](#create-app-surface)

1. [Configuración de la aplicación en Adobe Campaign](#push-config-campaign)

1. [Creación y configuración de una propiedad móvil en la recopilación de datos de Adobe Experience Platform](#create-mobile-property)

1. [Añadir la extensión de Adobe Experience Platform Assurance de Adobe](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}(recomendado)

1. [Añadir un Campaign Classic a la aplicación móvil.](#campaign-mobile-ap)

1. [Cree un envío tanto para iOS como para Android](##push-create)

>[!NOTE]
>
> La recopilación de datos no es compatible con FCM y APNS p12 heredados.

## Crear una superficie de aplicación en la recopilación de datos de Adobe Experience Platform {#create-app-surface}

Debe añadir las credenciales push de la aplicación móvil en [!DNL Adobe Experience Platform Data Collection].

Se requiere el registro de credenciales push de la aplicación móvil para autorizar al Adobe a enviar notificaciones push en su nombre. Consulte los pasos detallados a continuación:

1. Desde [!DNL Adobe Experience Platform Data Collection], seleccione la **[!UICONTROL App Surfaces]** en el panel izquierdo.

1. Clic **[!UICONTROL Create App Surface]** para crear una nueva configuración.

   ![](assets/push-config-1.png)

1. Introduzca una **[!UICONTROL Name]** para la configuración.

1. Desde **[!UICONTROL Mobile Application Configuration]**, seleccione el Sistema operativo:

   * **Para iOS**

     ![](assets/push-config-2.png)

      1. Introduzca la aplicación móvil **ID de paquete** en el **[!UICONTROL App ID (iOS Bundle ID)]** field.

         El ID del paquete de aplicaciones se encuentra en **General** pestaña del objetivo principal en **XCode** de su cuenta de desarrollador de Apple.

      1. Interruptor activado **[!UICONTROL Push Credentials]** para añadir sus credenciales.

      1. Arrastre y suelte su archivo .p8 de clave de autenticación de notificaciones push de Apple.

         Esta clave se puede adquirir desde el **Certificados**, **Identificadores** y **Perfiles** de su cuenta de desarrollador de Apple.

      1. Proporcione el **ID de clave**. Es una cadena de 10 caracteres asignada durante la creación de la clave de autenticación p8.

         Se encuentra en **Claves** pestaña en **Certificados**, **Identificadores** y **Perfiles** de su cuenta de desarrollador de Apple.

      1. Proporcione el **Identificador de equipo**. Es un valor de cadena que se puede encontrar en la variable **Suscripción** pestaña.

   * **Para Android**

     ![](assets/push-config-3.png)

      1. Proporcione el **[!UICONTROL App ID (Android package name)]**. Normalmente, el nombre del paquete es el ID de aplicación de su `build.gradle` archivo.

      1. Cambiar **[!UICONTROL Push Credentials]** para añadir sus credenciales.

      1. Arrastre y suelte las credenciales push de FCM. Para obtener más información sobre cómo obtener las credenciales push, consulte [Documentación de Google](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

1. Clic **[!UICONTROL Save]** para crear la configuración de la aplicación.

## Configuración de la aplicación en Adobe Campaign{#push-config-campaign}

### Crear un servicio {#create-service}

Antes de enviar notificaciones push, debe definir la configuración de las aplicaciones de iOS y Android en Adobe Campaign.

Las notificaciones push se envían a los usuarios de la aplicación a través de un servicio dedicado. Cuando los usuarios instalan la aplicación, se suscriben a este servicio: Adobe Campaign depende de este servicio para dirigirse únicamente a los suscriptores de la aplicación. En este servicio, debe agregar sus aplicaciones de iOS y Android para enviarlas en dispositivos iOS y Android.

Para crear un servicio para enviar notificaciones push, siga los pasos a continuación:

1. Navegar a **[!UICONTROL Profiles and Targets > Services and Subscriptions]** y haga clic en **[!UICONTROL Create]**.

   ![](assets/push-config-4.png){width="800" align="left"}

1. Introduzca una **[!UICONTROL Label]** y un **[!UICONTROL Internal name]** y seleccione una **[!UICONTROL Mobile application]** escriba.

   >[!NOTE]
   >
   >La asignación de destino predeterminada **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** está relacionada con la tabla de destinatarios. Si desea utilizar una asignación de destinatario diferente, debe crear una nueva asignación de destino e introducirla en el campo **[!UICONTROL Target mapping]** del servicio. Obtenga más información sobre las asignaciones de destino en [esta página](../audiences/target-mappings.md).

1. A continuación, utilice el **[!UICONTROL Add]** en la parte derecha para definir las aplicaciones móviles que utilizan este servicio.

   ![](assets/push-config-5.png)

### Creación de una aplicación móvil {#create-sapp}

Después de crear el servicio, debe definir las aplicaciones móviles que lo utilizarán.

>[!BEGINTABS]

>[!TAB iOS]

Para crear una aplicación para dispositivos iOS, siga estos pasos:

1. En el Servicio, haga clic en **[!UICONTROL Add]** luego seleccione **[!UICONTROL Create an iOS application]**. Haga clic en **[!UICONTROL Next]**.

   ![](assets/push-config-6.png)

1. Desde el **[!UICONTROL Launch app configurations list]** , seleccione la superficie de aplicación creada anteriormente en esta sección. Haga clic en **[!UICONTROL Next]**.

   ![](assets/push-config-7.png)

1. (opcional) Puede enriquecer el contenido de un mensaje push con **[!UICONTROL Application variables]**. Son totalmente personalizables y una parte de la carga útil de mensajes se envía al dispositivo móvil.

   En el ejemplo siguiente, la variable **mediaURl** y **mediaExt** Las variables de se agregan para crear notificaciones push enriquecidas y, a continuación, proporcionan a la aplicación la imagen que se mostrará en la notificación.

   ![](assets/push-config-8.png)

1. Vaya a la **[!UICONTROL Subscription parameters]** para definir la asignación con una extensión del **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** esquema.

1. Vaya a la **[!UICONTROL Sounds]** para definir un sonido para reproducir. Haga clic en **[!UICONTROL Add]** y rellene el campo **[!UICONTROL Internal name]** que debe contener el nombre del archivo incrustado en la aplicación o el nombre del sonido del sistema.

1. Haga clic en **[!UICONTROL Next]** para comenzar a configurar la aplicación de desarrollo.

1. El **[!UICONTROL Integration key]** es específico de cada aplicación. Vincula la aplicación móvil a Adobe Campaign y se utiliza al configurar la extensión de Campaign.

   Asegúrese de que es el mismo **[!UICONTROL Integration key]** se define en Adobe Campaign y en el código de la aplicación a través del SDK.

   Obtenga más información en [la documentación para desarrolladores](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]** es totalmente personalizable con un valor de cadena, pero debe ser exactamente igual al especificado en el SDK.
   >
   > No puede utilizar el mismo certificado para la versión de desarrollo (entorno limitado) y la versión de producción de la aplicación.

   ![](assets/push-config-9.png)

1. Seleccione el icono de la **[!UICONTROL Application icon]** para personalizar la aplicación móvil en el servicio.

1. Haga clic en **[!UICONTROL Next]** para configurar la aplicación de producción y siga los mismos pasos detallados anteriormente. Tenga en cuenta que no puede utilizar el mismo **[!UICONTROL Integration key]** para la versión de desarrollo (entorno limitado) y la versión de producción de la aplicación.

1. Haga clic en **[!UICONTROL Finish]**.

La aplicación de iOS ya está lista para su uso en Campaign.

>[!TAB Android]

Para crear una aplicación para dispositivos Android, siga estos pasos:

1. En el Servicio, haga clic en **[!UICONTROL Add]** luego seleccione **[!UICONTROL Create an Android application]**. Haga clic en **[!UICONTROL Next]**.

   ![](assets/push-config-10.png)

1. Desde el **[!UICONTROL Launch app configurations list]** , seleccione la superficie de aplicación creada en esta sección y haga clic en **[!UICONTROL Next]**.

   ![](assets/push-config-11.png)

1. La clave de integración es específica para cada aplicación. Vincula la aplicación móvil a Adobe Campaign y se utiliza al configurar la extensión de Campaign.

   Asegúrese de que es el mismo **[!UICONTROL Integration key]** se define en Adobe Campaign y en el código de la aplicación a través del SDK.

   Obtenga más información en [la documentación para desarrolladores](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}

   >[!NOTE]
   >
   > **[!UICONTROL Integration key]** es totalmente personalizable con un valor de cadena, pero debe ser exactamente igual al especificado en el SDK.

   ![](assets/push-config-12.png)

1. Seleccione el icono de la **[!UICONTROL Application icon]** para personalizar la aplicación móvil en el servicio.

1. (opcional) Puede enriquecer el contenido de un mensaje push con **[!UICONTROL Application variables]** si es necesario. Son totalmente personalizables y una parte de la carga útil de mensajes se envía al dispositivo móvil.

1. Vaya a la **[!UICONTROL Subscription parameters]** para definir la asignación con una extensión del **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** esquema.

1. Haga clic en **[!UICONTROL Finish]** y luego en **[!UICONTROL Save]**.

La aplicación de Android ya está lista para su uso en Campaign.

>[!ENDTABS]

A continuación se muestran los nombres de carga útil de FCM para personalizar aún más la notificación push:

| Tipo de mensaje | Elemento de mensaje configurable (nombre de carga útil de FCM) | Opciones configurables (nombre de carga útil de FCM) |
|:-:|:-:|:-:|
| mensaje de datos | N/A | validate_only |
| mensaje de notificación | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |

## Configuración de una propiedad móvil en la recopilación de datos de Adobe Experience Platform {#create-mobile-property}

1. En la página de inicio de la recopilación de datos, acceda al menú Etiquetas.

1. Haga clic en **[!UICONTROL New Property]**.

   ![](assets/push-config-13.png)

1. Escriba un nombre para la propiedad y seleccione **[!UICONTROL Mobile]** como plataforma.

   ![](assets/push-config-14.png)

1. Clic **[!UICONTROL Save]** para crear la propiedad móvil.

1. Acceda a la propiedad móvil recién creada.

1. En el panel de la propiedad móvil, acceda a **[!UICONTROL Extensions]** luego el menú **[!UICONTROL Catalog]** pestaña.

   ![](assets/push-config-15.png)

1. Instale el **[!DNL Adobe Campaign Classic]** extensión. [Obtenga más información sobre la extensión de Campaign](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configure-campaign-classic-extension)

   ![](assets/push-config-16.png)

1. Rellene los detalles de la instancia:

   * **[!UICONTROL Registration endpoint]** o **[!UICONTROL Tracking endpoint]** Las direcciones URL se pueden encontrar en **[!UICONTROL Tools]** > **[!UICONTROL Advanced]** > **[!UICONTROL Deployment wizard]** en Campaign.
   * **[!UICONTROL Integration keys]** se encuentra en la aplicación móvil configurada en [esta sección](#create-app).

   ![](assets/push-config-17.png)

1. Haga clic en **[!UICONTROL Save]**.

1. Ahora debe publicar la configuración desde el **[!UICONTROL Publishing flow]** menú. [Más información](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

La propiedad móvil ahora se sincronizará automáticamente con **[!UICONTROL Adobe Experience Platform Data Collection]** flujo de trabajo técnico. [Más información](../../automation/workflow/technical-workflows.md#list-technical-workflows)

## Añadir un Campaign Classic a la aplicación móvil. {#campaign-mobile-app}

El SDK móvil de Adobe Experience Platform impulsa las soluciones y los servicios Experience Cloud de Adobe en sus aplicaciones móviles. La configuración de los SDK se administra mediante la interfaz de usuario de recopilación de datos para lograr una configuración flexible e integraciones ampliables basadas en reglas.

[Obtenga más información en la documentación de Adobe Developer](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Creación de la notificación push{#push-create}

Una vez que haya configurado correctamente la aplicación móvil en Recopilación de datos, ahora puede crear y enviar notificaciones push en Adobe Campaign.

Consulte [esta página](push.md#push-create) para obtener los elementos detallados específicos para el envío de notificaciones de iOS y Android.
