---
title: Monitorización y seguimiento de un SMS
description: Acerca de la monitorización y el seguimiento de un envío SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 42be45db-3a90-4ad0-896d-f082afff1f8e
TQID: 'https://experienceleague.adobe.com/wETwv6lIEctnfT54WQjulzGxeCPo6lZDF-rxlwBtF4I'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%
---
# Monitorización y seguimiento de un SMS

Es importante monitorizar la entrega de SMS para asegurarse de que las campañas de marketing sean eficientes.

Aquí las posibilidades que tiene para saber lo que sucede después de la entrega de su entrega

## Comprensión del panel de envío de SMS

El panel de envío le proporciona mucha información sobre su SMS.

Para acceder al panel, haga doble clic en su entrega en la lista de envíos.

En la ficha **[!UICONTROL Summary]**, tiene los datos principales, como el número de mensajes procesados y el número de mensajes correctos.

![](assets/sms_summary.png){zoomable="yes"}

Después de enviar el SMS, ya no se puede acceder a la pestaña **[!UICONTROL SMS]**, que trata sobre el contenido de la entrega, para variar.

En la ficha **[!UICONTROL Delivery]**, tiene la información sobre los registros de envío. Para cada dirección contactada, puede ver si el SMS se ha enviado o no

![](assets/sms_deliverylogs.png){zoomable="yes"}

Puede ver en la pestaña **[!UICONTROL Exclusions]** los detalles de por qué algunas direcciones se excluyen del destino.

![](assets/sms_exclusions.png){zoomable="yes"}

La ficha **[!UICONTROL Tracking]** trata sobre el seguimiento. A continuación, se muestra el ejemplo de una dirección URL rastreada en el contenido del SMS.

![](assets/sms_trackinglogs.png){zoomable="yes"}

Y por último, la pestaña **[!UICONTROL Audit]** con todos los detalles durante el inicio de la entrega:

![](assets/sms_audit.png){zoomable="yes"}

## Comprender los errores de SMS

Los tipos de errores y los motivos del error para SMS son los mismos que para los correos electrónicos.

Obtenga más información sobre [errores de entrega](../delivery-failures.md) y, específicamente, sobre [cuarentenas de SMS](../delivery-failures.md#sms-quarantines).
