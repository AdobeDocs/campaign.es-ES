---
title: Manage subscriptions and unsubscriptions in Campaign
description: Learn how to manage subscriptions and unsubscriptions in Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 34%

---

# Manage subscriptions and unsubscriptions{#optin-optout}

Use Adobe Campaign to create and monitor your information services such as newsletters and to manage the subscriptions/unsubscriptions to these services. Se pueden definir varios servicios en paralelo, como, por ejemplo: boletines de prueba para determinadas categorías de productos, temas o áreas de un sitio web, suscripciones a diversos tipos de mensajes de alerta y notificaciones en tiempo real. Consulte Administración de suscripciones.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html)

To subscribe (opt-in) a profile to a service, available options are:

* **[!UICONTROL Subscriptions]****[!UICONTROL Add]**

   ![](assets/subscribe-to-a-service.png)

   ![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;}

* Automatically subscribe a set of recipients to the service. The list of recipients can come from a filtering operation, a group, a folder, an import, or a direct manual selection. Para suscribir a estos destinatarios, haga clic con el botón derecho del ratón. Seleccione **[!UICONTROL Actions > Subscribe selection to a service...]**.

   ![](assets/subscribe-selection.png)

   Select the service concerned, and start the operation.

   ![](assets/subscribe-confirm.png)

   ![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;}


* Importación de destinatarios y subscripción automática a un servicio informativo. Para ello, seleccione el servicio correspondiente en el último paso del asistente para importar.

   ![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients){target=&quot;_blank&quot;}

* Uso de un formulario web para que los destinatarios puedan suscribirse a un servicio.

   ![](assets/opt-in-webapp.png)

   Campaign comes with a default web form to manage opt-in. You can personalize it and map the profile data.

   ![](assets/web-app.png)

   ![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in){target=&quot;_blank&quot;}


* **[!UICONTROL Subscription service]**

   ![](assets/wf-subscription.png)

   ![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/subscription-services.html?lang=en#example--subscribe-a-list-of-recipients-to-a-newsletter){target=&quot;_blank&quot;}

To unsubscribe (opt-out) a profile from a service, available options are:

****

* Personalized unsubscription link or web form
* Manual deletion of an information service
* Manual deletion of recipients from particular subscription service

**Baja automática**

* Specify a duration limit of the information service: recipients will be unsubscribed automatically when the period of validity has expired. El periodo se configura en la pestaña Edit de las propiedades del servicio. Se muestra en días.
* Set up an unsubscription workflow for a population.

![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service){target=&quot;_blank&quot;}


>[!CAUTION]
>
>[](../architecture/enterprise-deployment.md)**** Opt-in and opt-out requests are processed each hour. [Más información](../architecture/new-apis.md#sub-apis)

You can also enable your delivery recipients to forward messages to a friend. Para ello, inserte los vínculos correspondientes en la entrega. Puede hacer un seguimiento de este proceso de uso compartido, así como del número de visitas a las páginas en cuestión.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend)
