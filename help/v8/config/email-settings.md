---
title: Configuración de canal de correo electrónico de Campaign
description: Configuración de canal de correo electrónico de Campaign
feature: Email
role: User
level: Intermediate, Experienced
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 13%

---

# Configuración de canal de correo electrónico de Campaign

## CCO del correo electrónico {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

Puede configurar Adobe Campaign para que conserve una copia de los correos electrónicos enviados desde su plataforma.

Adobe Campaign no administra los archivos archivados. Esto le permite enviar los mensajes de su elección a una dirección de correo electrónico específica de CCO (copia oculta), desde la que se pueden procesar y archivar mediante un sistema externo. Los archivos .eml correspondientes a los correos electrónicos enviados se pueden transferir a un servidor remoto, como un servidor de correo electrónico SMTP.

>[!CAUTION]
>
>Por motivos de privacidad, los correos electrónicos CCO deben procesarse mediante un sistema de archivado capaz de almacenar información de identificación personal (PII) de forma segura.

El destino de archivado es la dirección de correo electrónico CCO que elija, que permanece invisible para los destinatarios de la entrega.

![](../assets/do-not-localize/speech.png)  Como usuario de Managed Cloud Services, [Adobe de contacto](../start/campaign-faq.md#support){target="_blank"} para comunicar la dirección de correo electrónico CCO que se utilizará para el archivado.

Una vez definida la dirección de correo electrónico de CCO, debe habilitar la opción dedicada en el nivel de entrega.

>[!CAUTION]
>
>Al crear una nueva entrega o plantilla de envíos, **[!UICONTROL Email BCC]** no está activada de forma predeterminada. Debe habilitarlo manualmente en la entrega de correo electrónico o en la plantilla de envíos.


Para realizar esto, siga los pasos a continuación:

1. Ir a **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**, o **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Seleccione la entrega que desee o duplique el de forma predeterminada **[!UICONTROL Email delivery]** plantilla y, a continuación, seleccione la plantilla duplicada.
1. Haga clic en el botón **[!UICONTROL Properties]**.
1. Seleccione la pestaña **[!UICONTROL Delivery]** .
1. Marque la opción **[!UICONTROL Email BCC]**.

   ![](assets/email-bcc.png)

1. Seleccione **[!UICONTROL Ok]**.

Se enviará una copia de todos los mensajes enviados para cada envío en función de esta plantilla a la dirección de CCO de correo electrónico que se haya configurado.

Tenga en cuenta las siguientes especificidades y recomendaciones:

* Solo puede utilizar una dirección de correo electrónico CCO.

* Asegúrese de que la dirección de CCO tenga suficiente capacidad de recepción para archivar todos los correos electrónicos enviados.

* Correo electrónico CCO <!--with Enhanced MTA--> envía a la dirección de correo electrónico CCO antes de enviar a los destinatarios, lo que puede dar como resultado que se envíen mensajes CCO aunque los envíos originales puedan haber rebotado. Para obtener más información sobre las devoluciones, consulte [Comprensión de errores de entrega](../send/delivery-failures.md).

* Si se abren y se hace clic en los correos electrónicos enviados a la dirección de CCO, esto se tiene en cuenta en el cálculo de **[!UICONTROL Total opens]** y **[!UICONTROL Clicks]** en el análisis de envío, lo cual podría provocar algunos cálculos erróneos.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Más información**

En estas secciones:

* [Uso de plantillas de envíos por correo electrónico](../send/create-templates.md)

* [Comprender los errores de envío](../send/delivery-failures.md)


Y en la documentación de Campaign Classic v7:

* [Seleccionar formato de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target="_blank"}

* [Seleccionar codificación de caracteres](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target="_blank"}

* [Establecer la dirección de correo electrónico de rechazo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target="_blank"}

