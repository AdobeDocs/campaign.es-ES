---
title: SMS para definir el contenido
description: Obtenga información sobre cómo configurar el contenido de un envío SMS
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="Disponibilidad limitada" type="Informative"
source-git-commit: a184a29301f2bd739bc3fd1373fc8cfad58f0393
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 33%

---


# Contenido SMS {#sms-content}

Para configurar el contenido de su envío de SMS:

1. Escriba el contenido del mensaje en el asistente **[!UICONTROL Text content]**

   ![](assets/sms_content.png){zoomable="yes"}

1. Puede personalizar el mensaje insertando campos personalizados (por ejemplo, añadiendo el nombre) o insertando bloques personalizados predefinidos (por ejemplo, añadiendo los saludos). Puede hacer clic en el botón de personalización para añadir lo siguiente:

   ![](assets/sms_perso.png){zoomable="yes"}

   Después de hacer clic en **[!UICONTROL Recipient]** > **[!UICONTROL First name]**, la personalización se muestra de esta manera:

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

1. Puede obtener una vista previa de la entrega desde la pestaña **[!UICONTROL Preview]**, haciendo clic en la lista desplegable **[!UICONTROL Test personalization]** y eligiendo un destinatario en la tabla **[!UICONTROL Recipient]**.

   ![](assets/sms_preview.png){zoomable="yes"}

   Tendrá la previsualización de su SMS con la personalización:

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* Los mensajes SMS se limitan a una longitud de 160 caracteres si se utiliza la página de códigos Latin-1 (ISO-8859-1). Si el mensaje se escribe en Unicode, no debe exceder los 70 caracteres. Algunos caracteres especiales pueden afectar la longitud del mensaje. Para obtener más información sobre la longitud del mensaje, consulte la sección [Transliteración de caracteres SMS](smpp-external-account.md#smpp-channel-settings).
>
>* Cuando hay campos de personalización o campos de contenido condicionados, el tamaño del mensaje varía según el destinatario. La longitud del mensaje debe evaluarse cuando se haya realizado la personalización.
>
>* Al iniciar el análisis, se comprueba la longitud de los mensajes y se muestra una advertencia en caso de desbordamiento.

Después de crear el contenido de tu envío, puedes [seleccionar tu audiencia](sms-audience.md).