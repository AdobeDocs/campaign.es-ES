---
title: Trabajo con Campaign y Twitter
description: Aprenda a integrar el entorno de Campaign con Twitter
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 0f15112f0eec1d7cba26523adc1e88fc5d26997c
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 26%

---

# Trabajo con Campaign y Twitter{#tw-ac-ovv}

La variable **Administración de redes sociales (Marketing social)** le permite interactuar con sus clientes a través de Twitter. Utilice esta capacidad para:

* Enviar mensajes: use Adobe Campaign Social Marketing para publicar mensajes en Twitter. También puede enviar mensajes directos a todos sus seguidores de 

* Recopilar nuevos contactos : Adobe Campaign Social Marketing también facilita la adquisición de nuevos contactos: póngase en contacto con los usuarios y pídale que compartan su información de perfil. Si lo aceptan, Adobe Campaign recupera automáticamente los datos, lo que le permite llevar a cabo campañas de objetivo y, cuando sea posible, implementar estrategias multicanal.

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, [Adobe de contacto](../start/campaign-faq.md#support) para conectar Campaign con Twitter. La variable  **Administración de redes sociales (Marketing social)** debe estar instalado en su entorno, a través del paquete dedicado.


Para configurar Adobe Campaign para que publique tweets en sus cuentas de Twitter, delegue el acceso de escritura a Adobe Campaign para estas cuentas. Para ello, haga lo siguiente:

1. Cree una cuenta de Twitter
1. Cree una cuenta de Twitter de prueba para enviar pruebas
1. Crear una aplicación de Twitter (una aplicación por cuenta de Twitter)
1. Crear un nuevo servicio para **[!UICONTROL Twitter]** (un servicio por cuenta de Twitter)

## Creación de una cuenta de prueba en Twitter {#tw-test-account}

Además de la cuenta de Twitter, cree una cuenta privada de Twitter que pueda utilizarse para enviar [pruebas de tweet](../send/twitter.md#send-tw-proofs). Para realizar esto, siga los pasos a continuación:

1. Cree una nueva cuenta de Twitter.
1. Acceso a la cuenta  **Configuración**.
1. Vaya a **Privacidad y seguridad** y **Audiencia y etiquetado** y compruebe el **Protect sus tweets** . Los tuits y demás información de la cuenta solo son visibles para las personas que le siguen.

![](assets/social_tw_test_page.png)

## Creación de una aplicación en Twitter {#create-an-app-on-twitter}

Cree una aplicación de Twitter para permitir que Adobe Campaign publique tweets en su cuenta de Twitter.  Para realizar esto, siga los pasos a continuación:

1. Inicie sesión en su cuenta de Twitter.
1. Conectar a [Portal para desarrolladores de twitter](https://developer.twitter.com/en/apps).
1. Select **Crear una aplicación**.
1. Permita que el asistente de Twitter le guíe a través del proceso.

   Para permitir que Adobe Campaign publique tweets en su cuenta, edite al **Permisos** de la aplicación y seleccione **Lectura y escritura** para el **Acceso** para obtener más información. En la pestaña **Settings**, también debe dejar vacío el campo **Callback URL**.

   ![](assets/social_tw_app.png)

>[!NOTE]
>
>Necesita una aplicación por cuenta de Twitter. Como consecuencia, debe crear otra aplicación de prueba para enviar pruebas a la cuenta de prueba.

## Creación de un servicio de Twitter en Campaign {#create-tw-service}

Para vincular la instancia de Campaign a la cuenta de Twitter, cree una **Twitter** y acceso de escritura delegado a Campaign.

Para introducir la configuración, debe acceder a la consola de Adobe Campaign y a la cuenta de Twitter:

1. Apertura **Twitter** y de [la página Proyecto y aplicaciones](https://developer.twitter.com/en/portal/projects-and-apps), seleccione la aplicación creada anteriormente. Acceda a la **Permisos de la aplicación**.

   ![](assets/social_tw_service.png)

   Edite la pestaña **Teclas y tokens** para acceder a los detalles de la aplicación.

1. En **Adobe Campaign**, vaya a la **[!UICONTROL Profiles and targets]** y seleccione **[!UICONTROL Services and Subscriptions]** vínculo
1. Cree un nuevo servicio.
1. Seleccione el tipo **[!UICONTROL Twitter]**.

   >[!NOTE]
   >
   >La variable **[!UICONTROL Synchronize subscriptions]** está activada de forma predeterminada: esta opción recupera automáticamente la lista de sus seguidores de Twitter para que pueda [enviarles mensajes directos](../send/twitter.md#direct-tw-messages). La sincronización se realiza mediante una [flujo de trabajo técnico dedicado](#synchro-tw-accounts).

1. Introduzca la etiqueta y el nombre interno del servicio.

   >[!CAUTION]
   >
   >La variable **[!UICONTROL Internal name]** del servicio debe ser el mismo nombre de su cuenta de Twitter.

   Para comprobar la configuración, puede:

   * Haga clic en el botón **[!UICONTROL Save]**.
   * En la descripción general de los servicios, seleccione la opción **Twitter** que acaba de crear.
   * Examine la **[!UICONTROL Twitter page]** pestaña: se debe mostrar la cuenta de Twitter.

1. De forma predeterminada, los seguidores se guardan en la carpeta **[!UICONTROL Visitors]**. Puede seleccionar otra ubicación desde la **[!UICONTROL Visitor folder]** campo . [Más información](../send/twitter.md#direct-tw-messages)

1. Desde la aplicación de Twitter, copie el contenido de la **[!UICONTROL Consumer Key (API Key)]** y **[!UICONTROL Consumer Secret (API Secret)]** y péguelos en el **[!UICONTROL Consumer key]** y **[!UICONTROL Consumer secret]** campos de la campaña **Twitter** servicio.

1. Desde la aplicación de Twitter, copie el contenido de la **[!UICONTROL Access Token]** y **[!UICONTROL Access Token Secret]** y péguelos en el **[!UICONTROL Access token]** y **[!UICONTROL Access token secret]** campos de la campaña **Twitter** servicio.

1. En la consola del cliente de Campaign, haga clic en **[!UICONTROL Save]**. Ahora ha delegado el acceso de escritura a Adobe Campaign.


>[!NOTE]
>
>Crear una **Twitter** por cuenta de Twitter. Como consecuencia, debe crear otro servicio de prueba para enviar pruebas a la cuenta de prueba.

## Sincronice su cuenta de Twitter {#synchro-tw-accounts}

La sincronización entre Campaign y Twitter se administra mediante flujos de trabajo técnicos específicos. Estos flujos de trabajo se almacenan en la variable **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** carpeta.

Se detienen de forma predeterminada: debe iniciarlos manualmente cuando comience a usar la variable **Marketing social** módulo.

La variable **[!UICONTROL Twitter account synchronization]** el flujo de trabajo técnico sincroniza las cuentas de Twitter en Adobe Campaign. Este flujo de trabajo recupera la lista de seguidores de Twitter para que pueda enviarles mensajes directos. [Más información](../send/twitter.md#direct-tw-messages)

De forma predeterminada, este flujo de trabajo se activa todos los jueves a las 7:30 a. m. Puede usar la variable **[!UICONTROL Execute pending task(s) now]** para iniciar el flujo de trabajo en cualquier momento mientras implementa esta integración.  También puede editar el planificador para cambiar la frecuencia de activación del flujo de trabajo. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target=&quot;_blank&quot;}.

>[!CAUTION]
>
>Para recuperar la lista de suscriptores de Twitter, la variable **[!UICONTROL Twitter account synchronization]** se debe marcar para el servicio vinculado a la cuenta. [Más información](#create-tw-service)

Los seguidores se almacenan en una tabla específica: la tabla de visitantes. Para mostrar la lista de seguidores de Twitter, vaya a la **[!UICONTROL Profiles and Targets > Visitors]**.

Para cada seguidor, Adobe Campaign almacena la siguiente información:

* **[!UICONTROL Origin]**: nombre de la red social (Twitter)
* **[!UICONTROL External ID]**: identificador de usuario
* **[!UICONTROL User name]**: nombre de cuenta del usuario
* **[!UICONTROL Full name]**: nombre del usuario
* **[!UICONTROL Language]**: idioma del usuario
* **[!UICONTROL Number of friends]**: número de seguidores
* **[!UICONTROL Time zone]**: zona horaria del usuario
* **[!UICONTROL Verified]**: este campo indica si el usuario tiene una cuenta de Twitter verificada

Una vez completada esta configuración, puede publicar tweets en sus cuentas de Twitter y enviar mensajes directos a sus seguidores. [Más información](../send/twitter.md)
