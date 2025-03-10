---
title: Trabajo con Campaign y X (Twitter)
description: Aprenda a integrar su entorno de Campaign con X (anteriormente conocido como Twitter)
role: User, Admin
feature: Social Marketing
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 42241364c1a23ae75d8f0aaf18a2cb1c04ce5b0c
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 11%

---

# Trabajo con Campaign y X (Twitter) {#tw-ac-ovv}

El módulo **Administración de redes sociales (Marketing social)** le permite interactuar con sus clientes a través de X (anteriormente conocido como Twitter). Utilice esta capacidad para lo siguiente:

* Publicar mensajes y enviar DM: utilice Adobe Campaign Social Marketing para publicar mensajes en X. También puede enviar mensajes directos a todos sus seguidores.

* Recopilar nuevos contactos: Adobe Campaign Social Marketing también facilita la adquisición de nuevos contactos: póngase en contacto con los usuarios y pídale que compartan la información de su perfil. Si lo aceptan, Adobe Campaign recupera automáticamente los datos, lo que le permite llevar a cabo campañas de objetivo y, cuando sea posible, implementar estrategias multicanal.


>[!NOTE]
>
>Como usuario de Cloud Services administrados, [póngase en contacto con Adobe](../start/campaign-faq.md#support) para conectar Campaign con X. El complemento **Managing social networks (Social Marketing)** debe estar instalado en su entorno, a través del paquete dedicado y la cuenta externa de Twitter debe estar configurada.


Para configurar Adobe Campaign para que publique tweets en sus cuentas X, delegue el acceso de escritura a Adobe Campaign para estas cuentas. Para ello, debe:

1. Cree una cuenta X y regístrese para obtener una cuenta de desarrollador. [Más información](#dev-account)
1. (opcional) Cree una cuenta X de prueba para enviar pruebas. [Más información](#tw-test-account)
1. Cree una aplicación X (una aplicación por cuenta X). [Más información](#create-an-app-on-twitter)
1. Cree un nuevo servicio para **[!UICONTROL Twitter]** (un servicio por cuenta X). [Más información](#create-tw-service)
1. Sincronice su cuenta X con Campaign. [Más información](#synchro-tw-accounts)

## Cuenta de desarrollador de X {#dev-account}

Para comenzar con esta integración, debes registrarte en [X cuenta de desarrollador](https://developer.twitter.com){target="_blank"}.

Campaign utiliza la versión 1.1 de la API de X. Para utilizarlo, debe solicitar el acceso elevado a través del portal para desarrolladores. Obtenga más información acerca del acceso elevado X [en esta página](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Creación de una solicitud en X {#create-an-app-on-twitter}

Una vez aprobado con acceso elevado, cree una aplicación X para permitir que Adobe Campaign cree publicaciones en su cuenta X. Para realizar esto, siga los pasos a continuación:

1. Inicie sesión en su cuenta X.
1. Conectar con [X portal para desarrolladores](https://developer.twitter.com/en/apps){target="_blank"}.
1. Seleccione **Crear una aplicación**.
1. Deje que el asistente X le guíe a través del proceso.
1. Para permitir que Adobe Campaign cree publicaciones en su cuenta, edite en **Permisos de aplicación** desde la sección Configuración de autenticación de usuario de su aplicación. Seleccione **Leer, escribir y dirigir mensajes**.

   ![](assets/tw-permissions.png)

1. En la sección **Tipo de aplicación**, seleccione **Aplicación web, Aplicación automatizada o Bot**. Puede dejar vacío el campo **URL de devolución de llamada** y guardar la configuración.

   ![](assets/tw-app-type.png)

1. Vuelva al panel de aplicaciones, seleccione su aplicación y vaya a la ficha **Claves y tokens**. En **Token de acceso y secreto**, si no se menciona el permiso **Leer, escribir y dirigir mensajes**, debe volver a generar el token y el secreto de la aplicación. Tenga en cuenta que todas las claves y tokens deben guardarse en el momento de la creación. Los necesitará para configurar su servicio de Twitter de Campaign.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>Necesita una aplicación por cuenta X. Como consecuencia, debe crear otra aplicación de prueba para enviar pruebas a la cuenta de prueba.
>

## Creación de un servicio de Twitter en Campaign {#create-tw-service}

Para vincular la instancia de Campaign con la cuenta X, cree un servicio **Twitter** y delegue el acceso de escritura a Campaign.

>[!CAUTION]
>
>Cree un servicio **Twitter** por cuenta X. Como consecuencia, debe crear otro servicio de prueba para enviar pruebas a su [cuenta de prueba](#tw-test-account).
>
>Adobe también debe crear cada servicio **Twitter** en su instancia intermediaria (MID). Póngase en contacto con su representante de Adobe para configurar su entorno.
>

Para introducir la configuración, debe acceder tanto a la consola del cliente de Adobe Campaign como a los permisos de la aplicación X.

1. En **Adobe Campaign**, vaya a la ficha **[!UICONTROL Profiles and targets]** y seleccione el vínculo **[!UICONTROL Services and Subscriptions]**
1. Cree un nuevo servicio.
1. Seleccione el tipo **[!UICONTROL Twitter]**.
1. Introduzca la etiqueta y el nombre interno del servicio.

   >[!CAUTION]
   >
   >El **[!UICONTROL Internal name]** del servicio debe ser exactamente el mismo nombre de su cuenta X.
   >

1. De manera predeterminada, los seguidores se guardan en la carpeta **[!UICONTROL Visitors]**. Puede seleccionar otra ubicación en el campo **[!UICONTROL Visitor folder]**. [Más información](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >La opción **[!UICONTROL Synchronize subscriptions]** está habilitada de manera predeterminada: esta opción recupera automáticamente la lista de sus seguidores X para que pueda [enviarles mensajes directos](../send/twitter.md#direct-tw-messages). La sincronización es realizada por un [flujo de trabajo técnico dedicado](#synchro-tw-accounts).

1. Desde la aplicación X, copie el contenido de los campos **Clave de API** y **[Secreto de clave de API]** y péguelos en los campos **[!UICONTROL Consumer key]** y **[!UICONTROL Consumer secret]** del servicio **Twitter** de Campaign.

1. Desde la aplicación X, copie el contenido de los campos **Token de acceso** y **Secreto de token de acceso** y péguelos en los campos **[!UICONTROL Access token]** y **[!UICONTROL Access token secret]** del servicio **Twitter** de Campaign.

1. En la consola del cliente de Campaign, haga clic en **[!UICONTROL Save]**. Ahora ha delegado el acceso de escritura a Adobe Campaign.

Para comprobar la configuración, puede:

* Edite el servicio **Twitter** que acaba de crear.
* Examine la ficha **[!UICONTROL Twitter page]**: debe mostrarse su cuenta de Twitter.
  ![](assets/tw-page.png)

## Sincronización de la cuenta X {#synchro-tw-accounts}

La sincronización entre Campaign y X se administra mediante flujos de trabajo técnicos dedicados. Estos flujos de trabajo se almacenan en la carpeta **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]**.

Se detienen de manera predeterminada: debe iniciarlos manualmente cuando comience a utilizar el módulo **Marketing social**.

El flujo de trabajo técnico **[!UICONTROL Synchronization of Twitter accounts]** sincroniza las cuentas X en Adobe Campaign. Este flujo de trabajo recupera la lista de X seguidores para que pueda enviarles mensajes directos. [Más información](../send/twitter.md#direct-tw-messages)

De forma predeterminada, este flujo de trabajo se activa todos los jueves a las 7:30 a.m. Puede usar la opción **[!UICONTROL Execute pending task(s) now]** para iniciar el flujo de trabajo en cualquier momento mientras implementa esta integración.  También puede editar el planificador para cambiar la frecuencia de activación del flujo de trabajo. Obtenga más información en [esta página](../../automation/workflow/scheduler.md).

>[!CAUTION]
>
>Para recuperar la lista de suscriptores X, se debe marcar la opción **[!UICONTROL Twitter account synchronization]** para el servicio vinculado a la cuenta. [Más información](#create-tw-service)

Los seguidores se almacenan en una tabla específica: la tabla de visitantes. Para mostrar la lista de seguidores X, vaya a **[!UICONTROL Profiles and Targets > Visitors]**.

Para cada seguidor, Adobe Campaign almacena la siguiente información:

* **[!UICONTROL Origin]**: Twitter
* **[!UICONTROL External ID]**: identificador de usuario
* **[!UICONTROL Username]**: nombre de cuenta del usuario
* **[!UICONTROL Full name]**: nombre del usuario
* **[!UICONTROL Number of friends]**: número de seguidores
* **[!UICONTROL Checked]**: este campo indica si el usuario tiene una cuenta de Twitter verificada

Una vez completada esta configuración, puede crear publicaciones en sus cuentas X y enviar mensajes directos a sus seguidores. [Más información](../send/twitter.md)

## Crear una cuenta de prueba en X {#tw-test-account}

Además de la cuenta X, cree una cuenta X privada que se pueda usar para enviar [pruebas de tweet](../send/twitter.md#send-tw-proofs). Para realizar esto, siga los pasos a continuación:

1. Cree una nueva cuenta X.
1. Acceda a la cuenta **Configuración**.
1. Vaya a **Privacidad y seguridad** y **Audiencia y etiquetado** y marque la opción **Proteger sus publicaciones**. Tus publicaciones y otra información de la cuenta solo son visibles para las personas que te siguen.

![](assets/do-not-localize/social_tw_test_page.png)

Configure la aplicación X y el servicio Campaign para que funcionen con esta cuenta de prueba, tal como se ha descrito anteriormente.
