---
title: Send direct mails with Adobe Campaign
description: Get started with direct mail in Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 35%

---

# Creación de envíos de correo directo

Las entregas de correo postal permiten generar un archivo de extracción que contenga datos sobre la población objetivo. A continuación, puede compartir este archivo con el proveedor que enviará mensajes a las poblaciones objetivo.

Los pasos para generar el archivo son:

1. Creación de la entrega

   Create a direct mail delivery based on the template. Puede duplicar y configurar la plantilla integrada **[!UICONTROL Deliver by direct mail (paper)]** .

   ![](../assets/do-not-localize/book.png)[ Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html)

1. Definición de la audiencia

   Los perfiles de destinatario deben contener al menos sus nombres y direcciones postales.

   Las direcciones postales son campos calculados. Una dirección puede contener de forma predeterminada hasta seis líneas: la primera contiene el nombre y los apellidos, las líneas siguientes contienen la dirección postal (calle, etc.) y la última línea contiene el código postal y el municipio o ciudad.

   Se considera que una dirección es completa si el nombre, el campo de código postal y el campo de municipio o ciudad no están vacíos.

   ![](../assets/do-not-localize/book.png)[ Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)

1. Definir el contenido del archivo

   Utilice el asistente de extracción para definir la información (columnas) que se exportará al archivo de salida.

   ![](../assets/do-not-localize/book.png)[ Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html)

1. Validación de la entrega

   Compruebe el resultado del análisis y el contenido del archivo de salida.

   ![](../assets/do-not-localize/book.png)[ Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html)

   In the context of a marketing campaign, on the extraction date, the extraction file is created. Puede ver el contenido del archivo extraído, aprobarlo o cambiar el formato y volver a iniciar la extracción si es necesario. Una vez aprobado el archivo, puede enviar el correo electrónico de notificación al enrutador.

   ![](../assets/do-not-localize/book.png)[ Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html#approving-an-extraction-file)

1. Inicie la entrega

   Una vez validado el archivo de extracción, haga clic en **Confirm delivery** un mensaje de confirmación le permite iniciar el envío.

   La confirmación inicia la extracción de datos en el archivo especificado.

   En el contexto de una campaña de marketing, cuando se han concedido todas las aprobaciones, los archivos de extracción se crean mediante un flujo de trabajo especial que, en una configuración predeterminada, se inicia automáticamente cuando un envío de correo postal está pendiente de extracción.

   ![](../assets/do-not-localize/book.png)[ Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html#starting-an-offline-delivery)
