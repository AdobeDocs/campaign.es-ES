---
title: Envío de correos electrónicos con Adobe Campaign
description: Introducción a los correos electrónicos en Adobe Campaign. Envíe correos electrónicos personalizados a un público objetivo.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: a76d2c30d3e1c723bcd4881f28980d346aade3dc
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 20%

---

# Diseño y envío de correos electrónicos

Con Adobe Campaign, cree envíos de correo electrónico para enviar correos electrónicos personalizados a la población objetivo. [Más información](../send/send.md)

>[!NOTE]
>
>Para crear correos electrónicos cautivadores y personalizados individualmente, ve a la [interfaz de usuario web](../start/campaign-ui.md#campaign-web-user-interface-ac-web-ui). Adobe Campaign viene con el Designer de correo electrónico, una interfaz intuitiva de arrastrar y soltar que le permite diseñar y refinar todo el contenido de cada correo electrónico.


Conozca los pasos clave para crear y configurar una entrega en [esta página](../start/create-message.md).

## Crear un envío de correo electrónico

Cree correos electrónicos personalizados y relevantes para el contexto que sean coherentes con el resto de la experiencia del cliente.

![](assets/new-email-content.png)


En el siguiente ejemplo, se muestran los pasos para diseñar una entrega de correo electrónico en Adobe Campaign que contenga datos personalizados, vínculos a una dirección URL externa y un vínculo a la página espejo.

1. **Crear la entrega**

   Para crear una entrega nueva, vaya a la pestaña **Campaigns**, haga clic en **Deliveries** y haga clic en el botón **Create** situado sobre la lista de entregas existentes.

   ![](assets/delivery_step_1.png)

1. **Seleccione la plantilla**

   Seleccione una plantilla de envío y asigne un nombre a la entrega. Este nombre solo está visible para los usuarios de la consola de Adobe Campaign y no para los destinatarios. Sin embargo, este título se muestra en la lista de envíos. Haga clic en **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Importe su contenido**

   Haga clic en la ficha **Source** para pegar el contenido de HTML.

   ![](assets/paste-content.png)

   >[!NOTE]
   >
   >Para evitar problemas de rendimiento, las imágenes incluidas en los correos electrónicos no pueden superar los 100 KB.

1. **Personaliza tu mensaje**

   * Adición del nombre y los apellidos de los destinatarios

     Para insertar el nombre y los apellidos de los perfiles de destino en el contenido del mensaje, coloque el cursor donde desee insertarlos, haga clic en el último icono de la barra de herramientas, luego haga clic en **[!UICONTROL Include]** y seleccione **[!UICONTROL Greetings]**.

     ![](assets/include-greetings.png)

     Vaya a la pestaña preview para comprobar la personalización seleccionando un destinatario.

     ![](assets/perso-check.png)

     Obtenga más información acerca de las opciones de personalización en [esta sección](personalize.md).

   * Inserción de un vínculo rastreado

     Para transferir los destinatarios de envíos a una dirección externa a través de una imagen o un texto, selecciónelo y haga clic en el icono **[!UICONTROL Add a link]** de la barra de herramientas.

     Introduzca la dirección URL del vínculo en el campo **URL** con el formato **https://www.myURL.com** y, a continuación, confirme la acción.

     ![](assets/add-a-link.png)

   * Adición de una página espejo

     Para permitir que los destinatarios vean el contenido de su envío en un explorador web, agregue un vínculo a la [página espejo](mirror-page.md) del mensaje.

     Coloque el cursor donde desee insertar este vínculo y haga clic en el último icono de la barra de herramientas; a continuación, haga clic en **[!UICONTROL Include]** y seleccione **[!UICONTROL link to mirror page]**.

     Obtenga más información acerca de la administración de la página espejo en [esta sección](mirror-page.md#link-to-mirror-page).

1. Puede definir parámetros adicionales para el correo electrónico, como enviar una copia de los mensajes a una dirección de la BBC, cambiar el formato del mensaje, configurar una codificación específica, etc. Obtenga más información en [esta sección](email-parameters.md).

1. Una vez que el contenido esté listo, haga clic en **Guardar**: ahora se mostrará en la lista de envíos, en la pestaña **[!UICONTROL Campaigns > Deliveries]**.

Su primer envío de correo electrónico está listo. Ahora debe definir la audiencia, validar la entrega y enviarlo.

Aprenda a crear un flujo de trabajo para importar un contenido de correo electrónico en este [caso de uso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html){target="_blank"}.

>[!MORELIKETHIS]
>
>* [Crear un envío](../start/create-message.md)
>* [Crear y usar una plantilla de correo electrónico](create-templates.md)
>* [Seleccione la audiencia de su correo electrónico](../audiences/gs-audiences.md)
>* [Validar una entrega y enviar pruebas](preview-and-proof.md)
>* [Configurar y realizar la entrega](configure-and-send.md)
>* [Prácticas recomendadas sobre entregas](../start/delivery-best-practices.md)

## Prueba y validación de correos electrónicos

Campaign ofrece varias formas de probar y validar los correos electrónicos antes de enviarlos a sus audiencias. Obtenga información sobre cómo obtener una vista previa y probar el contenido de su correo electrónico en [esta sección](../send/preview-and-proof.md).

Puede hacer lo siguiente:

* [Envío de pruebas](preview-and-proof.md)
* [Adición de direcciones semilla](../audiences/test-profiles.md)
* [Comprobación de registros de análisis de envío](delivery-analysis.md)

