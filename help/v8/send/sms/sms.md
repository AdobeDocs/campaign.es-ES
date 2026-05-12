---
title: Envío de SMS con Adobe Campaign
description: Introducción a SMS en Campaign
feature: SMS
role: User, Developer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
TQID: https://experienceleague.adobe.com/7ChOYJmYScxaAoqnruyMv-8n0AkXgYAIlt1783hTjvY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 28%

---

# Introducción a los SMS {#gs-sms-channel}

Utilice Adobe Campaign para enviar mensajes de texto a sus clientes en sus dispositivos móviles. Puede crear, personalizar y previsualizar mensajes en formato de texto desde el editor de SMS.

Para enviar SMS a dispositivos móviles con Adobe Campaign, necesita lo siguiente:

* Una cuenta externa configurada en el canal **[!UICONTROL Mobile (SMS)]**. Aprenda a configurar el canal SMS en su [infraestructura intermediaria](sms-mid-sourcing.md). Para esta configuración, debe comprender los [parámetros de cuenta externa de SMPP](smpp-external-account.md) y las [características del canal SMS](sms-channel.md).
Después de esta configuración, compruebe su conexión SMPP y aprenda a solucionarla si es necesario. [Más información](smpp-connection.md).

* Una plantilla de envíos de SMS vinculada correctamente a esta cuenta externa.

Adobe Campaign admite dos conectores SMS utilizados para enviar mensajes SMS a sus clientes. [Más información](sms-connectors.md).

>[!NOTE]
>
>También puede usar Adobe Campaign para enviar [notificaciones push](../push.md) y [LINE](../line/line.md) mensajes a dispositivos móviles.

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-sms.md">
<img alt="Creación de SMS" src="../../assets/do-not-localize/sms-sending.jpg">
</a>
<div><a href="create-sms.md"><strong>Creación de un envío de SMS</strong>
</div>
<p>
</td>
<td>
<a href="sms-content.md">
<img alt="Contenido SMS" src="../../assets/do-not-localize/sms-create.jpeg">
</a>
<div>
<a href="sms-content.md"><strong>Defina su contenido de SMS</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="Audiencia de SMS" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>Selección del público</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="Configuración de SMS" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>Configuración de canal de SMS</strong></a>
</div>
<p>
</td>
</tr></table>
