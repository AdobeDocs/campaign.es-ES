---
title: Previsualizar y probar el correo electrónico
description: Obtenga información sobre cómo validar la entrega antes de enviarlo
feature: Personalization
role: User
level: Beginner
source-git-commit: a6d2cb72968fe489a73f92f00f6a50be8ed3e997
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 12%

---

# Previsualizar y probar el correo electrónico {#preview-test}

Una vez definido el contenido del mensaje, puede utilizar perfiles de prueba para previsualizarlo y probarlo. Si ha insertado [contenido personalizado](personalize.md), puede comprobar cómo se muestra este contenido en el mensaje mediante los datos de perfil de prueba. Además, para detectar posibles errores en el contenido del mensaje o en la configuración de personalización, envíe pruebas a los perfiles de prueba. Se debe enviar una prueba cada vez que se realiza un cambio para validar el contenido más reciente.

## Vista previa del contenido{#preview-content}

Antes de enviar pruebas, se recomienda comprobar el contenido del mensaje en la sección de vista previa de la ventana de entrega.

Para obtener una vista previa del contenido del mensaje, siga los pasos a continuación:

1. Vaya a la **Vista previa** del envío.
1. Haga clic en el **[!UICONTROL Test personalization]** para seleccionar un perfil y rellenar los datos de personalización. Puede elegir un destinatario específico en la base de datos, una dirección semilla o seleccionar un perfil de la población objetivo, si ya se ha definido. También puede comprobar el contenido sin personalización.

   ![](assets/test-personalization.png)

1. La vista previa se genera para que pueda comprobar el procesamiento del mensaje. En la vista previa del mensaje, los elementos personalizados se sustituyen por los datos de perfil de prueba seleccionados.

   ![](assets/test-personalization-with-a-recipient.png)

1. Seleccione otros perfiles de prueba para previsualizar el procesamiento de correo electrónico para cada variante del mensaje.

## Envío de pruebas {#send-proofs}

En el caso de los envíos de correo electrónico, puede enviar pruebas para validar el contenido del mensaje. El envío de pruebas le permite comprobar el vínculo de no participación, la página espejo y cualquier otro vínculo, validar el mensaje, comprobar que se muestran las imágenes, detectar posibles errores, etc. También es posible que desee comprobar el diseño y el procesamiento en distintos dispositivos.

Una prueba es un mensaje específico que le permite probar un mensaje antes de enviarlo a la audiencia principal. Los destinatarios de la prueba se encargan de aprobar el mensaje: renderización, contenido, configuración de personalización, configuración.

### Destinatarios de prueba {#proofs-recipients}

El objetivo de la prueba se puede definir en la plantilla de entrega o en específico para una entrega. En ambos casos, vaya a la pantalla de definición de destino desde la **[!UICONTROL To]** y seleccione el **[!UICONTROL Target of the proofs]** pestaña .

![](assets/target-of-proofs.png)

El tipo de destino de la prueba se selecciona en el **[!UICONTROL Targeting mode]** lista desplegable.

* Utilice la variable **[!UICONTROL Definition of a specific proof target]** para seleccionar destinatarios en la base de datos como destino de prueba.
* Utilice la variable **[!UICONTROL Substitution of the address]** para introducir direcciones de correo electrónico y utilizar los datos de destinatario para validar el contenido. Las direcciones de sustitución se pueden introducir manualmente o seleccionar desde la lista desplegable. La enumeración asociada es Substitution address (rcpAddress).
De forma predeterminada, la sustitución se realiza de forma aleatoria, pero puede seleccionar un destinatario específico del destinatario principal a través del  **[!UICONTROL Detail]** icono.

   ![](assets/target-of-proofs-substitution-details.png){width="800" align="left"}

   Elija la **[!UICONTROL Select a profile (must be included in the target)]** y seleccione un destinatario.

   ![](assets/target-of-proofs-substitution.png){width="800" align="left"}


* Utilice la variable **[!UICONTROL Seed addresses]**  para utilizar las direcciones semilla como destino de prueba. Estas direcciones se pueden importar desde un archivo o introducir manualmente.

   >[!NOTE]
   >
   >Las direcciones semilla no pertenecen a la tabla de destinatarios predeterminada (nms:recipient), sino que se crean en una tabla independiente. Si se amplía la lista de distribución con nuevos datos, debe ampliar la lista de direcciones semilla con los mismos datos.

   Obtenga más información sobre las direcciones semilla en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}.

* Utilice la variable **[!UICONTROL Specific target and Seed addresses]** para combinar direcciones semilla y direcciones de correo electrónico específicas. Las configuraciones relacionadas se definen en dos subpestañas independientes.

### Envío de una prueba{#proofs-send}

Para enviar pruebas de mensajes, siga los pasos a continuación:

1. En la pantalla de definición del mensaje, haga clic en el botón **[!UICONTROL Send a proof]** botón.
1. En el **[!UICONTROL Send a proof]** , compruebe los destinatarios de prueba.
1. Haga clic en **[!UICONTROL Analyze]** para iniciar la preparación del mensaje de prueba.

   ![](assets/send-proof-analyze.png){width="800" align="left"}

1. Una vez finalizada la preparación de la entrega, utilice la variable **[!UICONTROL Confirm delivery]** para empezar a enviar mensajes de prueba.

Vaya a la **[!UICONTROL Audit]** de la entrega para comprobar la entrega de las copias de prueba.

Se recomienda enviar pruebas después de cada modificación al contenido del mensaje.

>[!NOTE]
>
>En la prueba enviada, el vínculo a la página espejo no está activo. Solo se activa en los mensajes finales.

### Propiedades de prueba{#proofs-properties}

Las propiedades de prueba se establecen en la variable **[!UICONTROL Advanced]** de las ventanas de propiedades de entrega. Vaya a la **[!UICONTROL Proof properties...]** para definir los parámetros y la etiqueta de las pruebas. Puede elegir mantener:

* Duplicar direcciones en la prueba
* incluida en la lista de bloqueados direcciones  en la prueba
* Direcciones en cuarentena en la prueba

De forma predeterminada, los mensajes de prueba se identifican mediante la variable `Proof #N` mencione en el asunto, donde `N` es el número de prueba. Este número se incrementa con cada análisis de envío de prueba. Puede cambiar el `proof` , según sea necesario.

![](assets/proof-parameters.png){width="800" align="left"}


## Vídeo explicativo {#video-proof}

Obtenga información sobre cómo enviar y validar una prueba para un envío de correo electrónico.

>[!VIDEO](https://video.tv.adobe.com/v/333404)
