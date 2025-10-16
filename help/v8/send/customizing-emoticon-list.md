---
product: campaign
title: Personalización de la lista de emoticonos
description: Obtenga información sobre cómo personalizar la lista de emoticonos al utilizar Adobe Campaign
feature: Email, Push
role: User, Data Engineer
version: Campaign v8, Campaign Classic v7
source-git-commit: 25ee55d5327e0ba7f2192f7b462853269c8cbf46
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 96%

---

# Personalización de la lista de emoticonos {#customize-emoticons}

La lista de emoticonos que se muestra en la ventana emergente se rige por una enumeración que permite mostrar valores en una lista para restringir las opciones que el usuario tiene para un campo determinado.
El orden de lista de emoticonos se puede personalizar y también se pueden añadir otros emoticonos a la lista.

Tenga en cuenta que los emoticonos solo están disponibles para correo electrónico y notificaciones push. Consulte esta [sección](defining-the-email-content.md#inserting-emoticons) para obtener más información.


## Adición de un nuevo emoticono {#add-new-emoticon}

>[!CAUTION]
>
>La lista de emoticonos no puede mostrar más de 81 entradas.

1. Elija el nuevo emoticono que desee añadir desde esta [página](https://unicode.org/emoji/charts/full-emoji-list.html). Recuerde que debe ser compatible con las distintas plataformas, como el explorador y el sistema operativo.

1. En el **[!UICONTROL Explorer]**, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Enumerations]** y haga clic en la enumeración predeterminada **[!UICONTROL Emoticon list]**.

   >[!NOTE]
   >
   >Solo un administrador de la consola de Adobe Campaign Classic puede administrar las enumeraciones predeterminadas.

   ![](assets/emoticon_1.png)

1. Haga clic **[!UICONTROL Add]**.

1. Rellene los campos:

   * **[!UICONTROL U+]**: Código del nuevo emoticono. Puede encontrar la lista de los códigos de emoticonos en esta [página](https://unicode.org/emoji/charts/full-emoji-list.html).
Para evitar problemas de compatibilidad, le recomendamos que elija emoticonos compatibles con los navegadores y con todos los sistemas operativos.

   * **[!UICONTROL Label]**: Etiqueta del nuevo emoticono.

   ![](assets/emoticon_5.png)

1. Haga clic en **[!UICONTROL Ok]** y luego en **[!UICONTROL Save]** cuando finalice la configuración.
El nuevo emoticono se coloca automáticamente en la tienda.

1. Para mostrarlo en la ventana **[!UICONTROL Insert emoticon]** de los envíos, seleccione el emoticono recién creado haciendo doble clic en él.

1. Elija en la lista desplegable **[!UICONTROL Display order]** el orden en que se va a mostrar el nuevo emoticono. Recuerde que al seleccionar un orden de visualización ya asignado, el emoticono existente se moverá automáticamente a la tienda.

   <br>En este ejemplo, elegimos el número de orden de visualización 61, lo que significa que si una entrada ya tenía este orden, automáticamente se mueve a la tienda y la nueva entrada ocupará su lugar en la enumeración.

   ![](assets/emoticon_2.png)

1. El nuevo emoticono se ha añadido a la enumeración predeterminada **[!UICONTROL Insert emoticon list]**. Puede cambiar su **[!UICONTROL Display order]** en cualquier momento o moverlo a la tienda si ya no lo necesita.

1. Para que los cambios se tengan en cuenta, desconéctese y vuelva a conectarse desde Adobe Campaign Classic. Si el nuevo emoticono aún no aparece en la ventana emergente **[!UICONTROL Insert emoticon]**, es posible que tenga que borrar la caché. Para ello, utilice el menú **[!UICONTROL File > Clear the local cache]**.

1. El nuevo emoticono ahora se encuentra en los envíos de la ventana emergente **[!UICONTROL Insert emoticon]** en la posición 61, que se configuró en los pasos anteriores. Para obtener más información sobre cómo usar emoticonos en los envíos, consulte esta [sección](defining-the-email-content.md#inserting-emoticons).

   ![](assets/emoticon_4.png)

1. Si los siguientes emoticonos aparecen en la ventana emergente **[!UICONTROL Insert emoticon]**, significa que no se han configurado correctamente. Compruebe si el código **[!UICONTROL U+]** o **[!UICONTROL Display order]** es correcto en la **[!UICONTROL Emoticon list]**.

   ![](assets/emoticon_6.png)
