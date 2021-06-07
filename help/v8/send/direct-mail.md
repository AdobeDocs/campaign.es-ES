---
product: Adobe Campaign
title: Enviar correos electrónicos directos con Adobe Campaign
description: Introducción al correo postal en Campaign
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: 67657fa19f3ff4594f7901f30d0d49ac75dcfbe0
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 24%

---

# Creación de envíos de correo postal

Las entregas de correo postal permiten generar un archivo de extracción que contenga datos sobre la población objetivo. A continuación, puede compartir este archivo con el proveedor que enviará mensajes a las poblaciones objetivo.

Los pasos para generar el archivo son:

1. Creación de la entrega

   Cree una entrega de correo postal basada en la plantilla . Puede duplicar y configurar la plantilla integrada **[!UICONTROL Deliver by direct mail (paper)]** .

   [!DNL :arrow_upper_right:] Obtenga más información en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html)

1. Definición de la audiencia

   Los perfiles de destinatario deben contener al menos sus nombres y direcciones postales.

   Las direcciones postales son campos calculados. Una dirección puede contener de forma predeterminada hasta seis líneas: la primera contiene el nombre y los apellidos, las líneas siguientes contienen la dirección postal (calle, etc.) y la última línea contiene el código postal y el municipio o ciudad.

   Se considera que una dirección es completa si el nombre, el campo de código postal y el campo de municipio o ciudad no están vacíos.

   [!DNL :arrow_upper_right:] Obtenga más información en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)

1. Definir el contenido del archivo

   Utilice el asistente de extracción para definir la información (columnas) que se exportará al archivo de salida.

   [!DNL :arrow_upper_right:] Obtenga más información en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html)

1. Validación de la entrega

   Compruebe el resultado del análisis y el contenido del archivo de salida.

   [!DNL :arrow_upper_right:] Obtenga más información en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html)

   En el contexto de una campaña de marketing, en la fecha de extracción, se crea el archivo de extracción. Puede ver el contenido del archivo extraído, aprobarlo o cambiar el formato y volver a iniciar la extracción si es necesario. Una vez aprobado el archivo, puede enviar el correo electrónico de notificación al enrutador.

   [!DNL :arrow_upper_right:] Obtenga más información en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html#approving-an-extraction-file)

1. Inicie la entrega

   Una vez validado el archivo de extracción, haga clic en **Confirm delivery** un mensaje de confirmación le permite iniciar el envío.

   La confirmación inicia la extracción de datos en el archivo especificado.

   En el contexto de una campaña de marketing, cuando se han concedido todas las aprobaciones, los archivos de extracción se crean mediante un flujo de trabajo especial que, en una configuración predeterminada, se inicia automáticamente cuando un envío de correo postal está pendiente de extracción.

   [!DNL :arrow_upper_right:] Obtenga más información en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html#starting-an-offline-delivery)