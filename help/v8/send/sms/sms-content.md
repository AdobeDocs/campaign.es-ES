---
title: Definición y personalización del contenido del SMS
description: Obtenga información sobre cómo definir y personalizar el contenido de un envío SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
TQID: https://experienceleague.adobe.com/N4C8Rkg-Kl-82FCZAvJ12KofuRObW170ySJaCHgW5wM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 254
ht-degree: 31%

---

# Definición del contenido del SMS {#sms-content}

Para configurar el contenido de su envío de SMS:

1. Escriba el contenido del mensaje en la ficha **[!UICONTROL Text content]**.

   ![](assets/sms_content.png){zoomable="yes"}

1. Puede personalizar el mensaje insertando campos personalizados (por ejemplo, añadiendo el nombre) o insertando bloques personalizados predefinidos (por ejemplo, añadiendo los saludos). Haga clic en el botón de personalización para añadir lo siguiente:

   ![](assets/sms_perso.png){zoomable="yes"}

   Por ejemplo, después de hacer clic en **[!UICONTROL Recipient]** > **[!UICONTROL First name]**, el contenido del SMS se actualiza con el campo de personalización, como se muestra a continuación:

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

   Obtenga más información acerca de la personalización en Adobe Campaign en [esta sección](../personalize.md).

1. Puede obtener una vista previa del contenido de su envío desde la pestaña **[!UICONTROL Preview]**. Para comprobar la configuración de personalización, haga clic en la lista desplegable **[!UICONTROL Test personalization]** y seleccione un destinatario.

   ![](assets/sms_preview.png){zoomable="yes"}

   Puede comprobar la previsualización de su SMS con la personalización:

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* Los mensajes SMS se limitan a una longitud de 160 caracteres si se utiliza la página de códigos Latin-1 (ISO-8859-1). Si el mensaje se escribe en Unicode, no debe exceder los 70 caracteres. Algunos caracteres especiales pueden afectar la longitud del mensaje. Para obtener más información sobre la longitud del mensaje, consulte la sección [Transliteración de caracteres SMS](smpp-external-account.md#smpp-channel-settings).
>
>* Cuando hay campos de personalización o campos de contenido condicionados, el tamaño del mensaje varía según el destinatario. La longitud del mensaje debe evaluarse cuando se haya realizado la personalización.
>
>* Al iniciar el análisis, se comprueba la longitud de los mensajes y se muestra una advertencia en caso de desbordamiento.

Después de crear el contenido de tu envío, puedes [seleccionar tu audiencia](sms-audience.md).
