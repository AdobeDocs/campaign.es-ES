---
title: Utilizar bloques de personalización
description: Aprenda a utilizar bloques de personalización integrados en el contenido del mensaje
feature: Personalization
role: User
level: Beginner
source-git-commit: badcbb83c4bd0cf509c156557f5ea6f7cf7ae771
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 30%

---


# Utilizar bloques de personalización{#personalization-blocks}

Los bloques personalizados son contenido dinámico que contiene una renderización específica que puede insertar en los envíos. Por ejemplo, puede añadir un logotipo, un mensaje de saludo o un vínculo a una página espejo.

Para acceder a los bloques de contenido personalizado, vaya a la **[!UICONTROL Resources > Campaign Management > Personalization blocks]** del explorador. Los bloques de personalización integrados se enumeran en [esta sección](#ootb-personalization-blocks).

También puede definir nuevos bloques para optimizar la personalización de las entregas. [Más información](#create-custom-personalization-blocks).

## Inserción de bloques de personalización {#insert-personalization-blocks}

Para insertar un bloque de personalización en un mensaje, siga los pasos a continuación:

1. En el editor de contenido del asistente de envíos, haga clic en el icono de personalización y seleccione **[!UICONTROL Include]** para abrir el Navegador.
1. Seleccione un bloque personalizado de la lista o haga clic en el botón **[!UICONTROL Other...]** para acceder a la lista completa.

   ![](assets/perso-content-block.png)

1. A continuación, el bloque personalizado se inserta como una secuencia de comandos. Se adapta automáticamente al perfil de destinatario cuando se genera la personalización.
1. Vaya a la **[!UICONTROL Preview]** y seleccione un destinatario para ver el contenido de este bloque para un destinatario específico.

Se puede incluir el código fuente de un bloque personalizado en el contenido de envío. Para ello, escoja **[!UICONTROL Include the HTML source code of the block]** al seleccionarlo.

## Bloques personalizados integrados {#ootb-personalization-blocks}

Los bloques de personalización integrados son:

* **[!UICONTROL Enabled by Adobe Campaign]**: inserta el logotipo &quot;Enabled by Adobe Campaign&quot;.
* **[!UICONTROL Formatting function for proper nouns]**: genera la función JavaScript **[!UICONTROL toSmartCase]**, que cambia la primera letra de cada palabra a mayúscula.
* **[!UICONTROL Greetings]**: inserta los saludos con el nombre completo del destinatario, seguidos de una coma. Ejemplo: &quot;Hola John Doe&quot;.
* **[!UICONTROL Insert logo]**: inserta un logotipo que se define en la configuración de la instancia.
* **[!UICONTROL Link to mirror page]**: inserta un vínculo al [página espejo](mirror-page.md). El formato predeterminado es: &quot;Si no puede ver este mensaje correctamente, haga clic aquí&quot;.
* **[!UICONTROL Mirror page URL]**: inserta la dirección URL de la página espejo, permitiendo que los diseñadores de envío comprueben el vínculo.
* **[!UICONTROL Offer acceptance URL in unitary mode]**: inserta una dirección URL que permite establecer una oferta en **[!UICONTROL Accepted]**. (Este bloque está disponible si el módulo Interaction está habilitado)
* **[!UICONTROL Registration confirmation]**: inserta un vínculo que permite confirmar la suscripción.
* **[!UICONTROL Registration link]**: inserta un vínculo de suscripción. Este vínculo se define en la configuración de la instancia. El contenido predeterminado es: &quot;Para registrarse, haga clic aquí.&quot;
* **[!UICONTROL Registration link (with referrer)]** : inserta un enlace de suscripción que permite identificar el visitante y el envío. Este vínculo se define en la configuración de la instancia.
* **[!UICONTROL Registration page URL]**: inserta una URL de suscripción
* **[!UICONTROL Style of content emails]** y **[!UICONTROL Notification style]**: genere código que dé formato a un correo electrónico con estilos de HTML predefinidos.
* **[!UICONTROL Unsubscription link]**: inserta un vínculo que permite cancelar la suscripción a todas las entregas (lista de bloqueados). El contenido asociado predeterminado es: &quot;Recibe este mensaje porque ha estado en contacto con ***su nombre de organización*** o un afiliado. Para dejar de recibir mensajes de ***su nombre de organización*** haga clic aquí&quot;.

## Creación de bloques personalizados personalizados {#create-custom-personalization-blocks}

Puede definir nuevos bloques de contenido personalizado para insertarlos desde el icono de personalización.

Para crear un bloque personalizado, siga los pasos a continuación:

1. Vaya a la **[!UICONTROL Resources > Campaign Management > Personalization blocks]** carpeta del explorador de Campaign.
1. Sobre la lista de bloques integrados, haga clic en **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. Rellene la configuración del bloque personalizado:

   ![](assets/perso-custom-block.png)

   * Introduzca la etiqueta del bloque. Esta etiqueta se muestra en la ventana de inserción del campo personalizado.
   * Seleccione un **Entrega** tipo de contenido.
   * Active la variable **[!UICONTROL Visible in the customization menus]** para que el bloque esté accesible desde el icono de inserción del campo personalizado.
   * Si es necesario, habilite la variable **[!UICONTROL The content of the personalization block depends upon the format]** para definir dos bloques diferentes para los correos electrónicos de HTML y de texto.
   * Introduzca el contenido (en HTML, texto, JavaScript, etc.) del bloque personalizado y haga clic en **[!UICONTROL Save]**.

Una vez guardado, el nuevo bloque personalizado está disponible en el editor de envíos.

## Tutorial en vídeo {#personalization-blocks-video}

Aprenda a crear bloques de contenido dinámico y a utilizarlos para personalizar el contenido de su envío de correo electrónico en el siguiente vídeo.

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)


