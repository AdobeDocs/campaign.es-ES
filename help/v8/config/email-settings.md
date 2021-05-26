---
solution: Campaign v8
product: Adobe Campaign
title: Configuración del canal de correo electrónico de Campaign
description: Configuración del canal de correo electrónico de Campaign
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 5%

---

# Configuración del canal de correo electrónico de Campaign

## Correo electrónico CCO

Puede configurar Adobe Campaign para que mantenga una copia de los correos electrónicos enviados desde la plataforma.

>[!NOTE]
>La capacidad de correo electrónico CCO es opcional. Compruebe el acuerdo de licencia.

Adobe Campaign no administra los archivos archivados. Permite enviar los mensajes que elija a una dirección específica, desde la que se pueden procesar y archivar mediante un sistema externo.

Para ello, los archivos .eml correspondientes a los correos electrónicos enviados se transfieren a un servidor remoto, como un servidor de correo electrónico SMTP. El destino de archivado es una dirección de correo electrónico CCO (invisible para los destinatarios de envío) que debe especificar.

Tenga en cuenta que:

* Solo puede utilizar **una** dirección de correo electrónico CCO.

* Solo se tienen en cuenta los correos electrónicos enviados correctamente, no los rechazos.

: globo_voz: Como usuario de Cloud Services administrados, [póngase en contacto con Adobe](../start/campaign-faq.md#support) para activar el correo electrónico CCO en Campaign. La dirección de correo electrónico CCO que elija debe proporcionarse al equipo de Adobe que la configurará por usted.

Una vez configurado el CCO de correo electrónico, asegúrese de que la función esté habilitada en la plantilla de envío o en el envío a través de la opción **Email BCC**.

![](assets/email-bcc.png)


**Temas relacionados** en la documentación del Campaign Classic v7:

* [Uso de plantillas de envíos de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* [Descubra los parámetros de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html)
* [Comprensión de los errores de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html)
