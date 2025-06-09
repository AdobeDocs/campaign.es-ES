---
title: Utilizar bloques de personalización
description: Aprenda a utilizar bloques de personalización integrados en el contenido del mensaje
feature: Personalization
role: User
level: Beginner
exl-id: 214ad693-d456-47ec-a9c8-199ba23c3d9c
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 33%

---

# Utilizar bloques de personalización{#personalization-blocks}

Los bloques personalizados son contenidos dinámicos que contienen una renderización específica que puede insertar en los envíos. Por ejemplo, puede añadir un logotipo, un mensaje de saludo o un enlace a una página espejo.

Para acceder a bloques de contenido personalizados, vaya al nodo **[!UICONTROL Resources > Campaign Management > Personalization blocks]** del explorador. Los bloques de personalización integrados se enumeran en [esta sección](#ootb-personalization-blocks).

También puede definir nuevos bloques para optimizar la personalización de las entregas. [Más información](#create-custom-personalization-blocks).

## Inserción de bloques de personalización {#insert-personalization-blocks}

Para insertar un bloque de personalización en un mensaje, siga los pasos a continuación:

1. En el editor de contenido del asistente de envíos, haga clic en el icono de personalización y seleccione el menú **[!UICONTROL Include]**.
1. Seleccione un bloque personalizado de la lista o haga clic en el menú **[!UICONTROL Other...]** para acceder a la lista completa.

   ![](assets/perso-content-block.png)

1. A continuación, el bloque personalizado se inserta como una secuencia de comandos. Se adapta automáticamente al perfil de destinatario cuando se genera la personalización.
1. Vaya a la pestaña **[!UICONTROL Preview]** y seleccione un destinatario para ver el contenido de este bloque para un destinatario específico.

Se puede incluir el código fuente de un bloque personalizado en el contenido de envío. Para ello, escoja **[!UICONTROL Include the HTML source code of the block]** al seleccionarlo.

## Bloques de personalización integrados {#ootb-personalization-blocks}

Los bloques de personalización integrados son:

* **[!UICONTROL Enabled by Adobe Campaign]**: inserta el logotipo &quot;Habilitado por Adobe Campaign&quot;.
* **[!UICONTROL Formatting function for proper nouns]**: genera la función JavaScript **[!UICONTROL toSmartCase]**, que cambia la primera letra de cada palabra a mayúscula.
* **[!UICONTROL Greetings]**: inserta los saludos con el nombre completo del destinatario, seguido de una coma. Ejemplo: “Hola, John Doe”.
* **[!UICONTROL Insert logo]**: inserta un logotipo definido en la configuración de la instancia.
* **[!UICONTROL Link to mirror page]**: inserta un vínculo a la [página espejo](mirror-page.md). El formato predeterminado es: “Si no puede ver este mensaje correctamente, haga clic aquí”.
* **[!UICONTROL Mirror page URL]**: inserta la dirección URL de la página espejo, permitiendo que los diseñadores de envío comprueben el vínculo.
* **[!UICONTROL Offer acceptance URL in unitary mode]**: inserta una dirección URL que permite establecer una oferta en **[!UICONTROL Accepted]**. (Este bloque está disponible si el módulo Interacción está habilitado)
* **[!UICONTROL Registration confirmation]**: inserta un vínculo que permite confirmar la suscripción.
* **[!UICONTROL Registration link]**: inserta un vínculo de suscripción. Este vínculo se define en la configuración de la instancia. El contenido predeterminado es: “Para registrarse, haga clic aquí”.
* **[!UICONTROL Registration link (with referrer)]**: inserta un vínculo de suscripción que permite identificar el visitante y la entrega. Este vínculo se define en la configuración de la instancia.
* **[!UICONTROL Registration page URL]**: inserta una URL de suscripción
* **[!UICONTROL Style of content emails]** y **[!UICONTROL Notification style]**: genere un código que dé formato a un correo electrónico con estilos HTML predefinidos.
* **[!UICONTROL Unsubscription link]**: inserta un vínculo que permite cancelar la suscripción a todos los envíos (lista de bloqueados de la). El contenido asociado predeterminado es el siguiente: “Usted recibe este mensaje porque ha estado en contacto con ***nombre de la organización*** o un afiliado. Para dejar de recibir mensajes de ***nombre de la organización*** haga clic aquí”.

## Creación de bloques de personalización personalizados {#create-custom-personalization-blocks}

Puede definir nuevos bloques de contenido personalizado para insertarlos desde el icono de personalización.

Para crear un bloque personalizado, siga los pasos a continuación:

1. Vaya a la carpeta **[!UICONTROL Resources > Campaign Management > Personalization blocks]** del explorador de Campaign.
1. Sobre la lista de bloques integrados, haga clic en **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. Rellene la configuración del bloque personalizado:

   ![](assets/perso-custom-block.png)

   * Introduzca la etiqueta del bloque. Esta etiqueta se muestra en la ventana de inserción del campo personalizado.
   * Seleccione un tipo de contenido de **Envío**.
   * Habilite la opción **[!UICONTROL Visible in the customization menus]** para poder acceder a este bloque desde el icono de inserción del campo personalizado.
   * Si es necesario, habilite la opción **[!UICONTROL The content of the personalization block depends upon the format]** para definir dos bloques diferentes para los correos electrónicos de texto y HTML.
   * Introduzca el contenido (en HTML, texto, JavaScript, etc.) del bloque personalizado y haga clic en **[!UICONTROL Save]**.

Una vez guardado, el nuevo bloque personalizado está disponible en el editor de envíos.

## Tutorial en vídeo {#personalization-blocks-video}

Obtenga información sobre cómo crear bloques de contenido dinámico y cómo utilizarlos para personalizar el contenido de su envío de correo electrónico en el siguiente vídeo.

>[!VIDEO](https://video.tv.adobe.com/v/3449009?quality=12&captions=spa)
