---
title: Configuración del canal de correo electrónico de Campaign
description: Configuración del canal de correo electrónico de Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 8%

---

# Configuración del canal de correo electrónico de Campaign

## CCO del correo electrónico

Puede configurar Adobe Campaign para que mantenga una copia de los correos electrónicos enviados desde la plataforma.

>[!NOTE]
>La capacidad de correo electrónico CCO es opcional. Compruebe el acuerdo de licencia.

Adobe Campaign no administra los archivos archivados. Permite enviar los mensajes que elija a una dirección específica, desde la que se pueden procesar y archivar mediante un sistema externo.

Para ello, los archivos .eml correspondientes a los correos electrónicos enviados se transfieren a un servidor remoto, como un servidor de correo electrónico SMTP. El destino de archivado es una dirección de correo electrónico CCO (invisible para los destinatarios de envío) que debe especificar.

Tenga en cuenta que:

* Solo puede usar **one** Dirección de correo electrónico CCO.

* Solo se tienen en cuenta los correos electrónicos enviados correctamente, no los rechazos.

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, [Adobe de contacto](../start/campaign-faq.md#support) para activar el correo electrónico CCO en Campaign. La dirección de correo electrónico CCO que elija debe proporcionarse al equipo de Adobe que la configurará por usted.

Una vez configurado el CCO de correo electrónico, asegúrese de que la función esté habilitada en la plantilla de envío o en la entrega a través del **Email BCC** .

![](assets/email-bcc.png)


**Temas relacionados** en la documentación de Campaign Classic v7:


* [Generar la página espejo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

* [Seleccionar formato de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

* [Seleccionar codificación de caracteres](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

* [Establecer la dirección de correo electrónico de rechazo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

* [Uso de plantillas de envíos de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=es){target=&quot;_blank&quot;}

* [Comprensión de los errores de entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}