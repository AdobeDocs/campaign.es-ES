---
title: Administración de suscripciones y bajas de suscripción en Campaign
description: Obtenga información sobre cómo administrar suscripciones y bajas en Campaign v8
feature: Subscriptions
role: Data Engineer
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 35%

---

# Administrar suscripciones y bajas{#optin-optout}

Utilice Adobe Campaign para crear y supervisar sus servicios informativos, como boletines informativos, y para administrar las suscripciones/bajas de suscripción a estos servicios. Se pueden definir varios servicios en paralelo, como, por ejemplo: boletines de prueba para determinadas categorías de productos, temas o áreas de un sitio web, suscripciones a diversos tipos de mensajes de alerta y notificaciones en tiempo real. Consulte Administración de suscripciones.

![](../assets/do-not-localize/book.png) Aprenda a crear un servicio informativo, enviar boletín y administrar la inclusión y la exclusión en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html){target=&quot;_blank&quot;}

Para suscribirse (activar) un perfil a un servicio, las opciones disponibles son:

* Añada manualmente el servicio al perfil de destinatario: para ello, en la sección **[!UICONTROL Subscriptions]** de su perfil, haga clic en **[!UICONTROL Add]** y seleccione el servicio informativo que corresponda.

   ![](assets/subscribe-to-a-service.png)

   ![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de la versión 7 de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;}

* Suscribir automáticamente un conjunto de destinatarios al servicio. La lista de destinatarios puede proceder de una operación de filtrado, un grupo, una carpeta, una importación o una selección manual directa. Para suscribir a estos destinatarios, haga clic con el botón derecho del ratón. Seleccione **[!UICONTROL Actions > Subscribe selection to a service...]**.

   ![](assets/subscribe-selection.png)

   Seleccione el servicio correspondiente e inicie la operación.

   ![](assets/subscribe-confirm.png)

   ![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de la versión 7 de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;}


* Importación de destinatarios y subscripción automática a un servicio informativo. Para ello, seleccione el servicio correspondiente en el último paso del asistente para importar.

   ![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de la versión 7 de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients){target=&quot;_blank&quot;}

* Uso de un formulario web para que los destinatarios puedan suscribirse a un servicio.

   ![](assets/opt-in-webapp.png)

   Campaign incluye un formulario web predeterminado para administrar la inclusión. Puede personalizarlo y asignar los datos de perfil.

   ![](assets/web-app.png)

   ![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de la versión 7 de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in){target=&quot;_blank&quot;}


* Creación de un flujo de trabajo de objetivos y uso de un **[!UICONTROL Subscription service]** actividad.

   ![](assets/wf-subscription.png)

   Obtenga más información en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/subscription-services.html).

Para cancelar la suscripción (exclusión) de un perfil de un servicio, las opciones disponibles son:

**Baja manual**

* Vínculo de baja personalizado o formulario web
* Eliminación manual de un servicio de información
* Eliminación manual de destinatarios de un servicio de suscripción en particular

**Baja automática**

* Especifique un límite de duración del servicio informativo: los destinatarios se cancelarán de forma automática cuando el periodo de validez haya caducado. El periodo se configura en la pestaña Edit de las propiedades del servicio. Se muestra en días.
* Configure un flujo de trabajo para darse de baja de una población.

![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de la versión 7 de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service){target=&quot;_blank&quot;}


>[!CAUTION]
>
>En el contexto de un [Implementación empresarial (FFDA)](../architecture/enterprise-deployment.md), las suscripciones y las bajas de suscripción son **asincrónico** procesos. Las solicitudes de inclusión y exclusión se procesan cada hora. [Más información](../architecture/new-apis.md#sub-apis)

También puede permitir que los destinatarios de la entrega reenvíen mensajes a un amigo. Para ello, inserte los vínculos correspondientes en la entrega. Puede hacer un seguimiento de este proceso de uso compartido, así como del número de visitas a las páginas en cuestión.

![](../assets/do-not-localize/book.png) Para obtener más información sobre esta capacidad, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend){target=&quot;_blank&quot;}
