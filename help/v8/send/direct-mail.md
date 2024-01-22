---
title: Envío de correos directos con Adobe Campaign
description: Introducción al correo directo en Campaign
feature: Direct Mail
role: User
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: f04db53bee75c935bc8737eef93fa05ec6868ebc
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 13%

---

# Creación de envíos de correo directo

Las entregas de correo postal permiten generar un archivo de extracción que contenga datos sobre la población objetivo. A continuación, puede compartir este archivo con el proveedor que enviará los mensajes a las poblaciones objetivo.

Los pasos para generar el archivo son los siguientes:

1. Creación de la entrega

   Cree una entrega de correo directo basado en la plantilla. Puede duplicar y configurar el **[!UICONTROL Deliver by direct mail (paper)]** plantilla integrada.

   ![](../assets/do-not-localize/book.png) Obtenga más información en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html){target="_blank"}

1. Definición del público

   Los perfiles de destinatario deben contener al menos sus nombres y direcciones postales.

   Las direcciones postales son campos calculados. Una dirección puede contener de forma predeterminada hasta seis líneas: la primera contiene el nombre y los apellidos, las líneas siguientes contienen la dirección postal (calle, etc.) y la última línea contiene el código postal y el municipio o ciudad. La definición del campo postalAddress calculado predeterminado se puede revisar en el esquema nms:recipient.

   Se considera que una dirección es completa si el nombre, el campo de código postal y el campo de municipio o ciudad no están vacíos. Los destinatarios con direcciones incompletas se excluirán de las entregas de correo directo.

   ![](../assets/do-not-localize/book.png) Obtenga más información en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

1. Definición del contenido del archivo

   Utilice el asistente de extracción para definir la información (columnas) que se exportarán en el archivo de salida.

   ![](../assets/do-not-localize/book.png) Obtenga más información en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html){target="_blank"}

1. Validación del envío

   Compruebe el resultado del análisis y el contenido del archivo de salida.

   ![](../assets/do-not-localize/book.png) Obtenga más información en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html){target="_blank"}

   En el contexto de una campaña de marketing, en la fecha de extracción se crea el archivo de extracción. Puede ver el contenido del archivo extraído, aprobarlo o cambiar el formato y volver a iniciar la extracción si es necesario. Una vez aprobado el archivo, puede enviar el correo electrónico de notificación al enrutador. Obtenga más información en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html)

1. Inicio de la entrega

   Una vez validado el archivo de extracción, haga clic en **Confirmar envío** un mensaje de confirmación le permite iniciar la entrega.

   La confirmación inicia la extracción de datos en el archivo especificado.

   En el contexto de una campaña de marketing, cuando se han concedido todas las aprobaciones, los archivos de extracción se crean mediante un flujo de trabajo especial que, en una configuración predeterminada, se inicia automáticamente cuando una entrega de correo directo está pendiente de extracción. Obtenga más información en [esta sección](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=es)
