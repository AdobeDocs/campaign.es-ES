---
title: Trabajo con Campaign y X (Twitter)
description: Aprenda a integrar su entorno de Campaign con X (anteriormente conocido como Twitter)
role: User, Admin
feature: Social Marketing
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 8f58db2b00f2fc98afd737f20411f829dd24c78a
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 11%

---

# Trabajo con Campaign y X (Twitter) {#tw-ac-ovv}

El **Administración de redes sociales (Marketing social)** Este módulo le permite interactuar con sus clientes a través de X (anteriormente conocido como Twitter). Utilice esta capacidad para lo siguiente:

* Publicar mensajes y enviar DM: utilice Adobe Campaign Social Marketing para publicar mensajes en X. También puede enviar mensajes directos a todos sus seguidores.

* Recopilar nuevos contactos: Adobe Campaign Social Marketing también facilita la adquisición de nuevos contactos: póngase en contacto con los usuarios y pídale que compartan la información de su perfil. Si lo aceptan, Adobe Campaign recupera automáticamente los datos, lo que le permite llevar a cabo campañas de objetivo y, cuando sea posible, implementar estrategias multicanal.

![](../assets/do-not-localize/speech.png) Como usuario de Managed Cloud Service, [Adobe de contacto](../start/campaign-faq.md#support) para conectar Campaign con X. La variable  **Administración de redes sociales (Marketing social)** El complemento debe instalarse en su entorno, a través del paquete específico, y se debe configurar la cuenta externa de Twitter.


Para configurar Adobe Campaign para que publique tweets en sus cuentas X, delegue el acceso de escritura a Adobe Campaign para estas cuentas. Para ello, debe:

1. Cree una cuenta X y regístrese para obtener una cuenta de desarrollador. [Más información](#dev-account)
1. (opcional) Cree una cuenta X de prueba para enviar pruebas. [Más información](#tw-test-account)
1. Cree una aplicación X (una aplicación por cuenta X). [Más información](#create-an-app-on-twitter)
1. Crear un nuevo servicio para **[!UICONTROL Twitter]** (un servicio por cuenta X). [Más información](#create-tw-service)
1. Sincronice su cuenta X con Campaign. [Más información](#synchro-tw-accounts)

## Cuenta de desarrollador de X {#dev-account}

Para comenzar con esta integración, debe registrarse en un [Cuenta de desarrollador de X](https://developer.twitter.com){target="_blank"}.

Campaign utiliza la versión 1.1 de la API de X. Para utilizarlo, debe solicitar el acceso elevado a través del portal para desarrolladores. Más información sobre el Acceso elevado X [en esta página](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Creación de una solicitud en X {#create-an-app-on-twitter}

Una vez aprobado con acceso elevado, cree una aplicación X para permitir que Adobe Campaign cree publicaciones en su cuenta X. Para realizar esto, siga los pasos a continuación:

1. Inicie sesión en su cuenta X.
1. Conectar a [Portal para desarrolladores de X](https://developer.twitter.com/en/apps).
1. Seleccionar **Crear una aplicación**.
1. Deje que el asistente X le guíe a través del proceso.
1. Para permitir que Adobe Campaign cree publicaciones en su cuenta, edite en **Permisos de aplicación** en la sección Configuración de autenticación de usuario de la aplicación. Seleccionar **Leer, escribir y dirigir mensajes**.

   ![](assets/tw-permissions.png)

1. En el **Tipo de aplicación** , seleccione **Aplicación web, aplicación automatizada o bot**. Puede dejar el **URL de devolución de llamada** vacío y guarde la configuración.

   ![](assets/tw-app-type.png)

1. Vuelva al panel de aplicaciones, seleccione la aplicación y vaya a **Claves y tokens** pestaña. En **Token y secreto de acceso**, si la variable **Leer, escribir y dirigir mensajes** no se menciona el permiso, debe volver a generar el token y el secreto de la aplicación. Tenga en cuenta que todas las claves y tokens deben guardarse en el momento de la creación. Los necesitará para configurar el servicio de Twitter de Campaign.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>Necesita una aplicación por cuenta X. Como consecuencia, debe crear otra aplicación de prueba para enviar pruebas a la cuenta de prueba.
>

## Creación de un servicio de Twitter en Campaign {#create-tw-service}

Para vincular la instancia de Campaign con la cuenta X, cree una **Twitter** y acceso de escritura delegado a Campaign.

>[!CAUTION]
>
>Crear uno **Twitter** servicio por cuenta X. Como consecuencia, debe crear otro servicio de prueba para enviar pruebas a su [cuenta de prueba](#tw-test-account).
>
>Cada **Twitter** El servicio también debe crearse mediante el Adobe en la instancia de MID. Póngase en contacto con el representante del Adobe para configurar su entorno.
>

Para introducir la configuración, debe acceder tanto a la consola del cliente de Adobe Campaign como a los permisos de la aplicación X.

1. Entrada **Adobe Campaign**, vaya a **[!UICONTROL Profiles and targets]** y seleccione la pestaña **[!UICONTROL Services and Subscriptions]** vincular
1. Cree un nuevo servicio.
1. Seleccione el tipo **[!UICONTROL Twitter]**.
1. Introduzca la etiqueta y el nombre interno del servicio.

   >[!CAUTION]
   >
   >El **[!UICONTROL Internal name]** El nombre del servicio debe ser exactamente el mismo nombre de su cuenta X.
   >

1. De forma predeterminada, los seguidores se guardan en **[!UICONTROL Visitors]** carpeta. Puede seleccionar otra ubicación en el **[!UICONTROL Visitor folder]** field. [Más información](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >El **[!UICONTROL Synchronize subscriptions]** : esta opción recupera automáticamente la lista de sus seguidores X de modo que usted pueda hacer lo siguiente: [enviarles mensajes directos](../send/twitter.md#direct-tw-messages). La sincronización se realiza mediante una [flujo de trabajo técnico dedicado](#synchro-tw-accounts).

1. Desde la aplicación X, copie el contenido del **Clave de API** y **[Secreto de clave API]** y péguelos en el campo **[!UICONTROL Consumer key]** y **[!UICONTROL Consumer secret]** campos de la campaña **Twitter** servicio.

1. Desde la aplicación X, copie el contenido del **Token de acceso** y **Secreto de token de acceso** y péguelos en el campo **[!UICONTROL Access token]** y **[!UICONTROL Access token secret]** campos de la campaña **Twitter** servicio.

1. En la consola del cliente de Campaign, haga clic en **[!UICONTROL Save]**. Ahora ha delegado el acceso de escritura a Adobe Campaign.

Para comprobar la configuración, puede:

* Edite el **Twitter** servicio que acaba de crear.
* Examine la **[!UICONTROL Twitter page]** pestaña: se debe mostrar su cuenta de Twitter.
  ![](assets/tw-page.png)

## Sincronización de la cuenta X {#synchro-tw-accounts}

La sincronización entre Campaign y X se administra mediante flujos de trabajo técnicos dedicados. Estos flujos de trabajo se almacenan en **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** carpeta.

Se detienen de forma predeterminada: debe iniciarlos manualmente al comenzar a utilizar la variable **Marketing social** módulo.

El **[!UICONTROL Synchronization of Twitter accounts]** El flujo de trabajo técnico sincroniza las cuentas X en Adobe Campaign. Este flujo de trabajo recupera la lista de X seguidores para que pueda enviarles mensajes directos. [Más información](../send/twitter.md#direct-tw-messages)

De forma predeterminada, este flujo de trabajo se activa todos los jueves a las 7:30 a.m. Puede usar el complemento **[!UICONTROL Execute pending task(s) now]** para iniciar el flujo de trabajo en cualquier momento mientras implementa esta integración.  También puede editar el planificador para cambiar la frecuencia de activación del flujo de trabajo. Obtenga más información en [esta página](../../automation/workflow/scheduler.md).

>[!CAUTION]
>
>Para recuperar la lista de suscriptores X, la variable **[!UICONTROL Twitter account synchronization]** La opción debe activarse para el servicio vinculado a la cuenta. [Más información](#create-tw-service)

Los seguidores se almacenan en una tabla específica: la tabla de visitantes. Para mostrar la lista de seguidores de X, busque **[!UICONTROL Profiles and Targets > Visitors]**.

Para cada seguidor, Adobe Campaign almacena la siguiente información:

* **[!UICONTROL Origin]**: TWITTER
* **[!UICONTROL External ID]**: identificador de usuario
* **[!UICONTROL Username]**: nombre de cuenta del usuario
* **[!UICONTROL Full name]**: nombre del usuario
* **[!UICONTROL Number of friends]**: número de seguidores
* **[!UICONTROL Checked]**: este campo indica si el usuario tiene una cuenta de Twitter verificada

Una vez completada esta configuración, puede crear publicaciones en sus cuentas X y enviar mensajes directos a sus seguidores. [Más información](../send/twitter.md)

## Crear una cuenta de prueba en X {#tw-test-account}

Además de la cuenta X, cree una cuenta X privada que se pueda utilizar para enviar [pruebas de tuit](../send/twitter.md#send-tw-proofs). Para realizar esto, siga los pasos a continuación:

1. Cree una nueva cuenta X.
1. Acceso a la cuenta  **Configuración**.
1. Navegar a **Privacidad y seguridad** y **Audiencia y etiquetado** y compruebe la **Protect sus publicaciones** opción. Tus publicaciones y otra información de la cuenta solo son visibles para las personas que te siguen.

![](assets/do-not-localize/social_tw_test_page.png)

Configure la aplicación X y el servicio Campaign para que funcionen con esta cuenta de prueba, tal como se ha descrito anteriormente.
