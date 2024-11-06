---
title: Envío de SMS con Adobe Campaign
description: Introducción a SMS en Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: bb77b915f50b31d8d91e25da6fa86aa15b03bba4
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 17%

---

# Introducción a los SMS {#gs-sms-channel}

Adobe Campaign le permite enviar SMS personalizados a móviles.

En los mensajes SMS, puede crear, modificar y personalizar mensajes solo de formato de texto. También puede obtener una previsualización de los mensajes SMS antes de enviarlos.

>[!NOTE]
>
>También puedes usar Adobe Campaign para enviar mensajes de [LINE](../../send/line.md), con texto o imágenes y vínculos.

Para enviar SMS a un teléfono móvil con Adobe Campaign, necesita:

* Una cuenta externa configurada en el canal **[!UICONTROL Mobile (SMS)]** o en el canal **[!UICONTROL LINE]**.
* Una plantilla de envíos de SMS vinculada correctamente a esta cuenta externa.

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
