---
title: Previsualización y prueba del correo electrónico
description: Obtenga información sobre cómo validar el envío antes de enviarlo
feature: Personalization
role: User
level: Beginner
exl-id: 5b9fa90c-c23e-47a7-b2ca-de75da4da2ab
TQID: 'https://experienceleague.adobe.com/uVVmB-6U7nTrC0ypEHAINNtp5tcE0gr8ambKwDK56ls'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 13af5358-448e-5a4a-850b-0db592bb0f8f
    internal-label: Personalization
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 18%
---
# Previsualización y prueba del correo electrónico {#preview-test}

Una vez definido el contenido del mensaje, puede utilizar perfiles de prueba para previsualizarlo y probarlo. Si ha insertado [contenido personalizado](personalize.md), puede comprobar cómo se muestra este contenido en el mensaje con los datos del perfil de prueba. Además, para detectar posibles errores en el contenido del mensaje o en la configuración de personalización, envíe pruebas a los perfiles de prueba. Se debe enviar una prueba cada vez que se realiza un cambio para validar el contenido más reciente.

## Previsualización de contenido {#preview-content}

Antes de enviar pruebas, una práctica recomendada es comprobar el contenido del mensaje en la sección de vista previa de la ventana de entrega.

Para obtener una vista previa del contenido del mensaje, siga los pasos a continuación:

1. Vaya a la pestaña **Vista previa** del envío.
1. Haga clic en el botón **[!UICONTROL Test personalization]** para seleccionar un perfil y rellenar los datos de personalización. Puede elegir un destinatario específico en la base de datos, una dirección semilla o seleccionar un perfil de la población de destinatarios, si ya se ha definido. También puede comprobar el contenido sin personalización.

   ![Menú de personalización de prueba en la pestaña Preview: Recipient, A seed address, Delivery target population, No personalization](assets/test-personalization.png)

1. La previsualización se genera para que pueda comprobar la renderización del mensaje. En la vista previa del mensaje, los elementos personalizados se sustituyen por los datos del perfil de prueba seleccionado.

   ![Vista previa del correo electrónico con el asunto y el encabezado personalizados con el nombre del perfil de prueba seleccionado](assets/test-personalization-with-a-recipient.png)

1. Seleccione otros perfiles de prueba para previsualizar el procesamiento de correo electrónico para cada variante del mensaje.

## Envío de pruebas {#send-proofs}

En el caso de los envíos por correo electrónico, puede enviar pruebas para validar el contenido del mensaje. El envío de pruebas le permite comprobar el vínculo de no participación, la página espejo y cualquier otro vínculo, validar el mensaje, comprobar que se muestran las imágenes, detectar posibles errores, etc. También puede que desee comprobar el diseño y la representación en diferentes dispositivos.

Una prueba es un mensaje específico que le permite probar un mensaje antes de enviarlo al público principal. Los destinatarios de la prueba se encargan de aprobar el mensaje: procesamiento, contenido, valores de ajuste de personalización, configuración.

### Destinatarios de prueba {#proofs-recipients}

El objetivo de la prueba se puede definir en la plantilla de envíos o puede ser específico de un envío. En ambos casos, vaya a la pantalla de definición de destino desde el vínculo **[!UICONTROL To]** y seleccione la pestaña **[!UICONTROL Target of the proofs]**.

![Cuadro de diálogo Seleccionar destino, destino de la pestaña de pruebas, con la lista desplegable Modo de segmentación y el botón Agregar](assets/target-of-proofs.png)

El tipo de destino de prueba está seleccionado en la lista desplegable **[!UICONTROL Targeting mode]**.

* Utilice la opción **[!UICONTROL Definition of a specific proof target]** para seleccionar destinatarios en la base de datos como destino de la prueba.
* Utilice la opción **[!UICONTROL Substitution of the address]** para introducir direcciones de correo electrónico y utilizar los datos del destinatario de destino para validar el contenido. Las direcciones de sustitución se pueden introducir manualmente o seleccionar en la lista desplegable. La [enumeración](../config/enumerations.md) asociada es **Dirección de sustitución (rcpAddress)**.

  De forma predeterminada, la sustitución se realiza de forma aleatoria, pero se puede seleccionar un destinatario específico del destino principal mediante el icono **[!UICONTROL Detail]**.

  ![Sustitución del modo de dirección que enumera direcciones de prueba, con el icono Detalle utilizado para seleccionar un perfil específico](assets/target-of-proofs-substitution-details.png){width="800"}

  Elija la opción **[!UICONTROL Select a profile (must be included in the target)]** y seleccione un destinatario.

  ![Cuadro de diálogo de destinatario de prueba independiente con la opción Select a profile y un destinatario elegido de la lista](assets/target-of-proofs-substitution.png){width="800"}


* Utilice la opción **[!UICONTROL Seed addresses]** para usar las direcciones semilla como destino de prueba. Estas direcciones pueden importarse desde un archivo o introducirse manualmente.

  >[!NOTE]
  >
  >Las direcciones semilla no pertenecen a la tabla de destinatarios predeterminada (nms:recipient), sino que se crean en una tabla independiente. Si se amplía la lista de distribución con nuevos datos, debe ampliar la lista de direcciones sembradas con los mismos datos.

  Obtenga más información acerca de las direcciones semilla en [Crear perfiles de prueba en Campaign](../audiences/test-profiles.md).

* Utilice la opción **[!UICONTROL Specific target and Seed addresses]** para combinar direcciones semilla y direcciones de correo electrónico específicas. Las configuraciones relacionadas se definen en dos subpestañas independientes.

### Envío de una prueba {#proofs-send}

Para enviar pruebas de mensajes, siga los pasos a continuación:

1. En la pantalla de definición del mensaje, haga clic en el botón **[!UICONTROL Send a proof]**.
1. En la ventana **[!UICONTROL Send a proof]**, compruebe los destinatarios de prueba.
1. Haga clic en **[!UICONTROL Analyze]** para iniciar la preparación del mensaje de prueba.

   ![Envíe una ventana de prueba con direcciones de sustitución y el registro de análisis de envío ejecutándose después de hacer clic en Analizar](assets/send-proof-analyze.png){width="800"}

1. Una vez completada la preparación del envío, use **[!UICONTROL Confirm delivery]** para empezar a enviar mensajes de prueba.

Vaya a la pestaña **[!UICONTROL Audit]** de la entrega para comprobar la entrega de las copias de prueba.

Se recomienda enviar pruebas después de cada modificación al contenido del mensaje.

>[!NOTE]
>
>En la prueba enviada, el vínculo a la página espejo no está activo. Solo se activa en los mensajes finales.

### Propiedades de revisión {#proofs-properties}

Las propiedades de prueba se establecen en la pestaña **[!UICONTROL Advanced]** de la ventana de propiedades de entrega. Vaya al vínculo **[!UICONTROL Proof properties...]** para definir los parámetros y la etiqueta de las pruebas. Puede optar por mantener:

* Duplicar direcciones en la prueba
* Direcciones en la prueba
* Direcciones en cuarentena en la prueba

De manera predeterminada, los mensajes de prueba se identifican mediante la mención `Proof #N` en el asunto, donde `N` es el número de prueba. Este número se incrementa con cada análisis de entrega de prueba. Puede cambiar el prefijo `proof` según sea necesario.

![Cuadro de diálogo Propiedades de prueba de la pestaña Avanzadas con opciones de prueba y el campo Prefijo de etiqueta establecido en Prueba](assets/proof-parameters.png){width="800"}


## Vídeos explicativos {#video-proof}

Obtenga información sobre cómo enviar y validar una prueba para un envío de correo electrónico.

>[!VIDEO](https://video.tv.adobe.com/v/3447002?captions=spa)
