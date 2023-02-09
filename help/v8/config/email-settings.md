---
title: Configuración del canal de correo electrónico de Campaign
description: Configuración del canal de correo electrónico de Campaign
feature: Email
role: User
level: Intermediate, Experienced
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 15%

---

# Configuración del canal de correo electrónico de Campaign

## CCO del correo electrónico {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

Puede configurar Adobe Campaign para que mantenga una copia de los correos electrónicos enviados desde la plataforma.

Adobe Campaign no administra los archivos archivados. Esto le permite enviar los mensajes que elija a una dirección de correo electrónico específica de CCO (copia oculta), desde la que se pueden procesar y archivar utilizando un sistema externo. Los archivos .eml correspondientes a los correos electrónicos enviados se pueden transferir a un servidor remoto, como un servidor de correo electrónico SMTP.

>[!CAUTION]
>
>Por motivos de privacidad, los correos electrónicos CCO deben ser procesados por un sistema de archiving capaz de almacenar información personal segura (PII).

El destino de archivado es la dirección de correo electrónico CCO que elija, que permanecerá invisible para los destinatarios de la entrega.

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, [Adobe de contacto](../start/campaign-faq.md#support){target="_blank"} para comunicar la dirección de correo electrónico de CCO que se utilizará para el archivado.

Una vez definida la dirección de correo electrónico CCO, debe activar la opción dedicada en el nivel de envío.

>[!CAUTION]
>
>Al crear un nuevo envío o plantilla de envío, **[!UICONTROL Email BCC]** no está activada de forma predeterminada. Debe activarlo manualmente en la entrega de correo electrónico o en la plantilla de envío.


Para realizar esto, siga los pasos a continuación:

1. Vaya a **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]** o **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Seleccione la entrega que desee o duplique el **[!UICONTROL Email delivery]** y, a continuación, seleccione la plantilla duplicada.
1. Haga clic en el botón **[!UICONTROL Properties]**.
1. Seleccione la pestaña **[!UICONTROL Delivery]** .
1. Marque la opción **[!UICONTROL Email BCC]**.

   ![](assets/email-bcc.png)

1. Seleccione **[!UICONTROL Ok]**.

Se enviará una copia de todos los mensajes enviados para cada envío basado en esta plantilla a la dirección de CCO de correo electrónico que se haya configurado.

Tenga en cuenta las siguientes características específicas y recomendaciones:

* Solo puede utilizar una dirección de correo electrónico CCO.

* Asegúrese de que la dirección de CCO tenga suficiente capacidad de recepción para archivar todos los correos electrónicos enviados.

* Email BCC <!--with Enhanced MTA--> envía a la dirección de correo electrónico de CCO antes de realizar la entrega a los destinatarios, lo que puede dar como resultado que se envíen mensajes CCO aunque las entregas originales puedan haber rebotado. Para obtener más información sobre devoluciones, consulte [Comprensión de los errores de entrega](../send/delivery-failures.md).

* Si se abren y se hace clic en los correos electrónicos enviados a la dirección de CCO, esto se tiene en cuenta en el cálculo de **[!UICONTROL Total opens]** y **[!UICONTROL Clicks]** en el análisis de envío, lo cual podría provocar algunos cálculos erróneos.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Obtenga más información en la documentación de Campaign Classic v7**

* [Generar la página espejo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target="_blank"}

* [Seleccionar formato de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target="_blank"}

* [Seleccionar codificación de caracteres](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target="_blank"}

* [Establecer la dirección de correo electrónico de rechazo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target="_blank"}

* [Uso de plantillas de envíos de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=es){target="_blank"}

* [Comprender los errores de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target="_blank"}
