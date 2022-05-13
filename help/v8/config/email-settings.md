---
title: Campaign email channel settings
description: Campaign email channel settings
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 9457652f62810eb401c4010acd9b5da42d88d796
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 13%

---

# Campaign email channel settings

## CCO del correo electrónico {#email-bcc}

>[!NOTE]
>
>[](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

You can configure Adobe Campaign to keep a copy of emails sent from your platform.

Adobe Campaign itself does not manage archived files. It does enable you to send the messages of your choice to a dedicated BCC (blind carbon copy) email address, from where they can be processed and archived using an external system. The .eml files corresponding to the sent emails can then be transferred to a remote server, such as an SMTP email server.

>[!CAUTION]
>
>For privacy reasons, BCC emails must be processed by an archiving system capable of storing securely personally identifiable information (PII).

The archiving destination is the BCC email address of your choice, which will remain invisible to the delivery recipients.

![](../assets/do-not-localize/speech.png)[](../start/campaign-faq.md#support)

Once the BCC email address is defined, you must enable the dedicated option at the delivery level.

>[!CAUTION]
>
>**[!UICONTROL Email BCC]** You need to enable it manually in the email delivery or delivery template.


Para realizar esto, siga los pasos a continuación:

1. **[!UICONTROL Campaign Management]****[!UICONTROL Deliveries]****[!UICONTROL Resources]****[!UICONTROL Templates]****[!UICONTROL Delivery templates]**
1. **[!UICONTROL Email delivery]**
1. Haga clic en el botón **[!UICONTROL Properties]**.
1. Seleccione la pestaña **[!UICONTROL Delivery]** .
1. Marque la opción **[!UICONTROL Email BCC]**.

   ![](assets/email-bcc.png)

1. Seleccione **[!UICONTROL Ok]**.

A copy of all sent messages for each delivery based on this template will be sent to the email BCC address which has been configured.

Note the following specificities and recommendations:

* You can only use one BCC email address.

* Make sure the BCC address has enough reception capacity to archive all the emails that are sent.

* <!--with Enhanced MTA--> [](../send/delivery-failures.md)

* Si se abren y se hace clic en los correos electrónicos enviados a la dirección de CCO, esto se tiene en cuenta en el cálculo de **[!UICONTROL Total opens]** y **[!UICONTROL Clicks]** en el análisis de envío, lo cual podría provocar algunos cálculos erróneos.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Obtenga más información en la documentación de Campaign Classic v7**

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page)

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats)

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding)

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails)

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=es)

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html)
