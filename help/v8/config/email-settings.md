---
solution: Campaign
product: Adobe Campaign
title: Configuración del canal de correo electrónico de Campaign
description: Configuración del canal de correo electrónico de Campaign
feature: Información general
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 4%

---

# Configuración del canal de correo electrónico de Campaign

## Correo electrónico CCO

Puede configurar Adobe Campaign para que mantenga una copia de los correos electrónicos enviados desde la plataforma.

Sin embargo, el propio Adobe Campaign no administra los archivos archivados. Permite enviar los mensajes que elija a una dirección específica, desde la que se pueden procesar y archivar mediante un sistema externo.

Para ello, los archivos .eml correspondientes a los correos electrónicos enviados se transfieren a un servidor remoto, como un servidor de correo electrónico SMTP. El destino de archivado es una dirección de correo electrónico CCO (invisible para los destinatarios de envío) que debe especificar.

Tenga en cuenta que:

* Solo puede utilizar una dirección de correo electrónico CCO.

* Solo se tienen en cuenta los correos electrónicos enviados correctamente, no los rechazos.

Una vez configurado el CCO de correo electrónico, asegúrese de que la función esté habilitada en la plantilla de envío o en el envío a través de la opción **Email BCC**.

:arrow_upper_right: Para obtener más información, consulte la [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=en#email-bcc)

**Nota**: La capacidad de correo electrónico CCO es opcional. Compruebe el acuerdo de licencia.

: globo_voz: Como usuario de Cloud Services administrados, [póngase en contacto con Adobe](../start/support.md#support) para activar el correo electrónico CCO en Campaign. La dirección de correo electrónico CCO que elija debe proporcionarse al equipo de Adobe que la configurará por usted.