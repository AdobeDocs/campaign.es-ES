---
title: Trabajo con Campaign y Adobe Experience Platform
description: Aprenda a trabajar con Campaign y Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# Trabajo con Campaign y Adobe Experience Platform

Los conectores de origen y destino del Cloud Service administrado de Adobe Campaign permiten una integración perfecta entre Adobe Campaign y Adobe Experience Platform:

* Uso **Conector de fuentes de nube gestionada de Adobe Campaign** para enviar segmentos de Experience Platform a Adobe Campaign para su activación,

   ![](assets/aep-destination.png)

* Uso **Conector de destino de Adobe Campaign Managed Cloud** para enviar los registros de envío y seguimiento de Adobe Campaign a Adobe Experience Platform.

   ![](assets/aep-logs.png)

Los pasos para configurar esta integración en Adobe Experience Platform son los siguientes:

1. Configure una nueva conexión de destino de Adobe Campaign Managed Cloud Services para activar un segmento o audiencia y enviar esos datos a Adobe Campaign.

   Proporcione detalles sobre la instancia de Campaign que desea utilizar, seleccione segmentos para activar para el destino y, a continuación, configure los atributos que desea exportar a Campaign.

   [Obtenga información sobre cómo crear una conexión de destino de Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Configure una nueva conexión de origen de Adobe Campaign Managed Cloud Services para introducir eventos de Campaign en Adobe Experience Platform.

   Proporcione detalles sobre la instancia de Campaign y el esquema que se va a utilizar, seleccione un conjunto de datos en el que se deben introducir los datos y, a continuación, configure los campos que se van a recuperar.

   [Obtenga información sobre cómo crear una conexión de origen de Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)
