---
title: Trabajo con Campaign y Adobe Experience Platform
description: Aprenda a trabajar con Campaign y Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: f8c4e05ba2fc97d981fb31f9b11c5de1dcc1ff6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Trabajo con Campaign y Adobe Experience Platform

Los conectores Origen y Destino del Cloud Service administrado de Adobe Campaign permiten una integración perfecta entre Adobe Campaign y Adobe Experience Platform.

* Uso de un Adobe Campaign Managed Cloud Services **Conexión de destino** para enviar segmentos del Experience Platform a Adobe Campaign para su activación:

  Para ello, configure un nuevo Adobe Campaign Managed Cloud Services **Conexión de destino** para activar un segmento o una audiencia y enviar esos datos a Adobe Campaign. Proporcione detalles sobre la instancia de Campaign que desea utilizar, seleccione los segmentos que desea activar para el destino y configure los atributos que desea exportar a Campaign. [Obtenga información sobre cómo crear una conexión de destino de Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

  ![](assets/aep-destination.png){width="800" align="center"}

* Uso de un Adobe Campaign Managed Cloud Services **Conexión de origen** para enviar los registros de envío y seguimiento de Adobe Campaign a Adobe Experience Platform:

  Para ello, configure un nuevo Adobe Campaign Managed Cloud Services **Conexión de origen** para introducir eventos de Campaign en Adobe Experience Platform. Proporcione detalles sobre la instancia de Campaign y el esquema que desea utilizar, seleccione un conjunto de datos donde se deben introducir los datos y, a continuación, configure los campos que desea recuperar. [Obtenga información sobre cómo crear una conexión de origen de Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}
