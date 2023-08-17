---
title: Contenido condicional
description: Aprenda a crear contenido condicional
feature: Personalization
role: User
level: Beginner
exl-id: bcbf3101-d43c-4ed3-ab02-a9936ec55b71
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 56%

---

# Creación de contenido condicional{#conditional-content}

Al configurar los campos de contenido condicionados, puede crear una personalización avanzada. Los bloques de texto o las imágenes completas se sustituyen cuando se cumple una condición concreta.


## Uso de condiciones en un correo electrónico {#conditions-in-an-email}

En el siguiente ejemplo, aprenda a crear un mensaje personalizado de forma dinámica según la ciudad y los intereses del destinatario.

* Cambiar el mensaje según la ciudad del destinatario,
* Personalice el contenido de la oferta según los intereses del destinatario.

Para crear contenido condicional según el valor de un campo, aplique los pasos siguientes:

1. Abra una entrega existente o cree un nuevo envío de correo electrónico.
1. En el editor de contenido de correo electrónico, haga clic en el icono de personalización y seleccione **[!UICONTROL Conditional content > If]**.

   ![Insertar una condición](assets/condition-insert.png)

   Los elementos de personalización se insertan en el cuerpo del mensaje. Ahora debe configurarlos.

1. Rellene los parámetros del **if** expresión.

   * Seleccione el primer elemento de la expresión, **`<FIELD>`** y haga clic en el icono de personalización para reemplazarlo por el campo de prueba.
   * Reemplace **`<VALUE>`** por el valor del campo para el que se debe cumplir la condición. Este valor debe estar entre comillas.
   * Especifique el contenido que desea que se inserte cuando se cumpla la condición. Puede ser un texto, una imagen, un formulario, un vínculo de hipertexto, etc.

   ![Condición en un correo electrónico](assets/condition-in-email.png)

1. Haga clic en la pestaña **[!UICONTROL Preview]** para ver el contenido del mensaje según el destinatario de la entrega. Seleccione un destinatario para el cual la condición sea verdadera para comprobar el contenido. A continuación, seleccione otro destinatario para el cual sea falso y vuelva a comprobarlo.

Se pueden añadir otros casos y definir contenido diferente según los valores de uno o varios campos. Para ello, utilice **[!UICONTROL Conditional content > Else]** y **[!UICONTROL Conditional content > Else if]**. Estas expresiones se configuran del mismo modo que la expresión **if**.

>[!CAUTION]
>
>El **%> &lt;%** Los caracteres deben eliminarse después de agregar **Else** y **Else if** condiciones.


## Caso de uso: Creación de un correo electrónico multilingüe {#creating-multilingual-email}

En el siguiente ejemplo, aprenda a crear un correo electrónico multilingüe. El contenido se muestra en un idioma o en otro según el idioma preferido del destinatario.

1. Cree un correo electrónico y seleccione la población objetivo. En este ejemplo, la condición para mostrar una versión o la otra se basa en el valor **Language** del perfil del destinatario. Estos valores se establecen en **EN**, **FR**, **ES**.
1. En el contenido HTML del correo electrónico, haga clic en la pestaña **[!UICONTROL Source]** y pegue el código siguiente:

   ```
   <% if (language == "EN" ) { %>
   <DIV id=en-version>Hello <%= recipient.firstName %>,</DIV>
   <DIV>Discover your new offers!</DIV>
   <DIV><a href="https://www.adobe.com/products/en">www.adobe.com/products/en</A></FONT></DIV><%
    } %>
   <% if (language == "FR" ) { %>
   <DIV id=fr-version>Bonjour <%= recipient.firstName %>,</DIV>
   <DIV>Découvrez nos nouvelles offres !</DIV>
   <DIV><a href="https://www.adobe.com/products/fr">www.adobe.com/products/fr</A></DIV><%
    } %>
    <% if (language == "ES" ) { %>
   <DIV id=es-version><FONT face=Arial>
   <DIV>Olà <%= recipient.firstName %>,</DIV>
   <DIV>Descubra nuestros nuevas ofertas !</DIV>
   <DIV><a href="https://www.adobe.com/products/es">www.adobe.com/products/es</A></DIV>
   <% } %>
   ```

1. Pruebe el contenido de los correos electrónicos en la pestaña **[!UICONTROL Preview]** seleccionando destinatarios con diferentes idiomas preferidos.

   >[!NOTE]
   >
   >Como no se ha definido ninguna versión alternativa en el contenido de correo electrónico, asegúrese de filtrar la población de destino antes de enviar el correo electrónico.

## Tutorial en vídeo {#conditionnal-content-video}

Aprenda a añadir contenido condicional a un envío con el ejemplo de una newsletter multilingüe.

>[!VIDEO](https://video.tv.adobe.com/v/335682?quality=12)
