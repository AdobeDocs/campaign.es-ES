---
title: Envío de SMS con Adobe Campaign
description: Introducción a SMS en Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
badge: label="Disponibilidad limitada" type="Informative"
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: af1d453179c2d739eca243b435dec90a4b8e2dd5
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 7%

---

# Introducción a los SMS {#gs-sms-channel}

Utilice Adobe Campaign para enviar mensajes SMS personalizados.

>[!IMPORTANT]
>
>Esta documentación es para Adobe Campaign 8.7.2 y posterior.
>
>Para las versiones anteriores, lea la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

>[!NOTE]
>
>Adobe Campaign también le permite enviar notificaciones push a los móviles a través de su opción **Adobe Campaign Mobile App Channel (NMAC)**. Obtenga más información en [esta sección](../push.md).

La simplicidad y facilidad de uso de los SMS lo convierten en un canal de comunicación muy valioso además de su robustez y compatibilidad inigualable sobre miles de millones de terminales.

Existen dos formas principales de enviar un SMS:

* Enviarlo manualmente desde un teléfono. Es la forma habitual de comunicarse directamente entre las personas.
* Enviarlo desde Internet. Esa es la forma en que Adobe Campaign utiliza para enviar mensajes. Para ello, necesita un proveedor de servicios de SMS que haga un puente desde Internet a la red móvil.

Puede ver en esta documentación los pasos para configurar, enviar y monitorizar un envío SMS:

* **Configuración de canal de SMS**

Primero, debe configurar el canal SMS en su [infraestructura intermediaria](sms-mid-sourcing.md).

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

Para esta configuración, debe comprender los [parámetros de cuenta externa de SMPP](smpp-external-account.md) y las [características del canal SMS](sms-channel.md).

Una vez configurada, verifique su conexión [SMPP y aprenda a solucionarla si es necesario](smpp-connection.md).

* **Cree su primer envío de SMS**

Para comenzar la configuración de la entrega de SMS:

1. Cree su envío y complete la [configuración de envío de SMS](sms-delivery-settings.md),

1. [Defina el contenido](sms-content.md) de su envío,

1. [Seleccione la audiencia](sms-audience.md).

Los pasos para definir una audiencia se detallan en [esta página](../../audiences/create-audiences.md).

* **Validar y enviar SMS**

Después de la creación de la entrega:

1. [Enviar pruebas](sms-proofs.md) para validar la representación y el contenido,

1. A continuación, [enviar a la audiencia final](sms-send.md).

* **Monitorizar y rastrear SMS**

Después del envío, [aprenderá a monitorizar y rastrear su SMS](sms-monitor.md).
