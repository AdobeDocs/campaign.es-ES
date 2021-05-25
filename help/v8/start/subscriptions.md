---
solution: Campaign v8
product: Adobe Campaign
title: Administración de suscripciones y bajas de suscripción en Campaign
description: Obtenga información sobre cómo administrar suscripciones y bajas de suscripción en Campaign v8
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 25%

---

# Administrar suscripciones y bajas{#optin-optout}

Utilice Adobe Campaign para crear y supervisar sus servicios informativos, como boletines informativos, y para administrar las suscripciones/bajas de suscripción a estos servicios. Se pueden definir varios servicios en paralelo, como, por ejemplo: boletines de prueba para determinadas categorías de productos, temas o áreas de un sitio web, suscripciones a diversos tipos de mensajes de alerta y notificaciones en tiempo real. Consulte Administración de suscripciones.

:arrow_upper_right: Aprenda a crear un servicio informativo, enviar boletín y administrar la inclusión y la exclusión en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html)

Para suscribirse (activar) un perfil a un servicio, las opciones disponibles son:

* Añada manualmente el servicio al perfil de destinatario: para ello, en la pestaña **[!UICONTROL Subscriptions]** de su perfil, haga clic en **[!UICONTROL Add]** y seleccione el servicio informativo que corresponda.

   :arrow_upper_right: Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)

* Suscribir automáticamente un conjunto de destinatarios al servicio. La lista de destinatarios puede proceder de una operación de filtrado, un grupo, una carpeta, una importación o una selección manual directa. Para suscribir a estos destinatarios, haga clic con el botón derecho del ratón. Seleccione **[!UICONTROL Actions > Subscribe selection to a service...]**, seleccione el servicio correspondiente e inicie la operación.

   :arrow_upper_right: Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)


* Importación de destinatarios y subscripción automática a un servicio informativo. Para ello, seleccione el servicio correspondiente en el último paso del asistente para importar.

   :arrow_upper_right: Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients)

* Uso de un formulario web para que los destinatarios puedan suscribirse a un servicio.

   :arrow_upper_right: Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in)


* Cree un flujo de trabajo de objetivos y utilice una actividad **[!UICONTROL Subscription service]** .

   :arrow_upper_right: Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/subscription-services.html?lang=en#example--subscribe-a-list-of-recipients-to-a-newsletter)


Para cancelar la suscripción (exclusión) de un perfil de un servicio, las opciones disponibles son:

**Baja manual**

* Vínculo de baja personalizado o formulario web
* Eliminación manual de un servicio de información
* Eliminación manual de destinatarios de un servicio de suscripción en particular

**Baja automática**

* Especifique un límite de duración del servicio informativo: los destinatarios se cancelarán de forma automática cuando el periodo de validez haya caducado. El periodo se configura en la pestaña Edit de las propiedades del servicio. Se muestra en días.
* Configuración de un flujo de trabajo de baja para una población

:arrow_upper_right: Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service)


>[!CAUTION]
>
>Las suscripciones y las bajas de suscripción son procesos **asíncronos**. Las solicitudes de inclusión y exclusión se procesan cada hora. [Obtenga más información](../dev/new-apis.md#sub-apis)

También puede permitir que los destinatarios de la entrega reenvíen mensajes a un amigo. Para ello, inserte los vínculos correspondientes en la entrega. Puede hacer un seguimiento de este proceso de uso compartido, así como del número de visitas a las páginas en cuestión.

:arrow_upper_right: Para obtener más información sobre esta capacidad, consulte la [documentación del Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend).