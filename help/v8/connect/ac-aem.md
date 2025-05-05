---
title: Trabajo con Campaign y Adobe Experience Manager
description: Aprenda a trabajar con Campaign y Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 15%

---

# Trabajo con Campaign y Adobe Experience Manager {#ac-aem}

La integración entre Adobe Campaign y Adobe Experience Manager le permite administrar el contenido de las entregas de los correos electrónicos y los formularios directamente en Adobe Experience Manager. Tiene la opción de importar el contenido de **Adobe Experience Manager** en Campaign o conectar su cuenta de **Adobe Experience Manager as a Cloud Service**, lo que le permite editar el contenido directamente desde la interfaz web.

[Descubra cómo editar su contenido de Adobe Experience Manager como Cloud Service en la interfaz web de Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-content.html?lang=es){target="_blank"}.

[Obtenga más información acerca de Adobe Experience Manager en este documento](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html?lang=es#aem-and-adobe-campaign-integration-workflow){target="_blank"}.


>[!NOTE]
>
>Como usuario de Managed Cloud Service, [póngase en contacto con el Adobe](../start/campaign-faq.md#support) para integrar Adobe Experience Manager con Campaign.

## Importación de contenido desde Adobe Experience Manager {#integrating-with-aem}

Esta integración puede utilizarse, por ejemplo, para crear un “newsletter” en Adobe Experience Manager para su uso posterior en Adobe Campaign como parte de una campaña de correo electrónico.

**Desde Adobe Experience Manager:**

1. Vaya a la instancia de autor de [!DNL Adobe Experience Manager] y haga clic en Experiencia de Adobe en la esquina superior izquierda de la página. Elija **[!UICONTROL Sites]** en el menú.

   ![](assets/aem_authoring_1.png)

1. Acceso **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**.

1. Haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Page]** en el menú desplegable.

   ![](assets/aem_authoring_2.png)

1. Seleccione la plantilla de **[!UICONTROL Adobe Campaign Email]** y asigne un nombre al newsletter.

1. Después de crear su página, acceda al menú **[!UICONTROL Page information]** y haga clic en **[!UICONTROL Open Properties]**.

   ![](assets/aem_authoring_3.png)

1. Personalice el contenido del correo electrónico añadiendo componentes como, por ejemplo, campos de personalización de Adobe Campaign. Obtenga más información en [Documentación de Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html?lang=es#editing-email-content){target="_blank"}.

1. Cuando el correo electrónico esté listo, vaya al menú **[!UICONTROL Page information]** y haga clic en **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_4.png)

1. En la primera lista desplegable, seleccione **[!UICONTROL Approve Adobe Campaign]** como modelo de flujo de trabajo y haga clic en **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_5.png)

1. Aparecerá un aviso de exención de responsabilidad en la parte superior de la página que indica `This page is subject to the workflow Approve for Adobe Campaign`. Haga clic en **[!UICONTROL Complete]** al lado del aviso legal para confirmar la revisión y luego haga clic en **[!UICONTROL Ok]**.

1. Vuelva a hacer clic en **[!UICONTROL Complete]** y seleccione **[!UICONTROL Newsletter approval]** en la lista desplegable **[!UICONTROL Next Step]**.

   ![](assets/aem_authoring_6.png)

El boletín ya está listo y sincronizado en Adobe Campaign.

**Desde Adobe Campaign:**

1. En la pestaña **[!UICONTROL Campaigns]** , haga clic en **[!UICONTROL Deliveries]** luego **[!UICONTROL Create]**.

1. Elija la plantilla **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** del menú desplegable **[!UICONTROL Delivery template]**.

   ![](assets/aem_authoring_7.png)

1. Añada a la entrega una **[!UICONTROL Label]** y haga clic en **[!UICONTROL Continue]**.

1. AEM Haga clic en **[!UICONTROL Synchronize]** para acceder a los envíos de la.

   Si el botón no está visible en la interfaz, vaya al botón **[!UICONTROL Properties]** y acceda a la pestaña **[!UICONTROL Advanced]**. AEM Asegúrese de que el campo **[!UICONTROL Content editing mode]** esté configurado en **[!UICONTROL AEM]** e introduzca los detalles de la instancia de la en el campo **[!UICONTROL AEM account]**.

   ![](assets/aem_authoring_8.png)

1. AEM Seleccione la entrega de la creada anteriormente en [!DNL Adobe Experience Manager] y confirme haciendo clic en **[!UICONTROL Ok]**.

   ![](assets/aem_authoring_11.png)

1. AEM Asegúrese de hacer clic en el botón **[!UICONTROL Refresh content]** cada vez que se realicen modificaciones en el envío de la.

   ![](assets/aem_authoring_12.png)

1. Para quitar el vínculo entre el Experience Manager y Campaign, haga clic en **[!UICONTROL Desynchronize]**.

El correo electrónico está listo para enviarlo a su audiencia.

## Importar recursos desde la biblioteca de Adobe Experience Manager Assets {#assets-library}

También puede insertar recursos directamente desde su [!DNL Adobe Experience Manager Assets Library] mientras edita un mensaje de correo electrónico o una página de aterrizaje en Adobe Campaign. Esta funcionalidad se encuentra detallada en [Documentación de Adobe Experience Manager Assets](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=es){target="_blank"}.

**Desde Adobe Experience Manager:**

1. Vaya a la instancia de autor de [!DNL Adobe Experience Manager] y haga clic en Experiencia de Adobe en la esquina superior izquierda de la página. Elija **[!UICONTROL Assets]** `>` **[!UICONTROL Files]** en el menú.

   ![](assets/aem_assets_1.png)

1. Haga clic en **Crear** y luego en **Archivos** para importar el recurso en la **biblioteca de Adobe Experience Manager Assets**. Obtenga más información en [Adobe de Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=es#uploading-assets){target="_blank"}.

   ![](assets/aem_assets_2.png)

1. Cambie el nombre del recurso si es necesario y seleccione **Cargar**.

El recurso se ha cargado a la **biblioteca de Adobe Experience Manager Assets**.

**Desde Adobe Campaign:**

1. En Adobe Campaign, para crear una entrega nueva, vaya a la pestaña **Campañas**, haga clic en **Envíos** y haga clic en el botón **Crear** situado sobre la lista de envíos existentes.

   ![](assets/aem_assets_3.png)

1. Seleccione una **plantilla de envíos** y asigne un nombre a la entrega.

1. Defina y personalice el contenido del mensaje. [Más información](../send/email.md)

1. Para usar tu **biblioteca de Adobe Experience Manager Assets AEM**, accede a **[!UICONTROL Properties]** de tu entrega y selecciona la pestaña **[!UICONTROL Advanced]**.

   AEM Elija su **cuenta de** y habilite la opción **[!UICONTROL Use above AEM instance as shared asset library]**.

   ![](assets/aem_authoring_9.png)

1. Desde el icono **Image**, accede al menú **[!UICONTROL Select a shared asset]**.

   ![](assets/aem_assets_4.png)

1. En la ventana de selección, selecciona una imagen de tu **biblioteca Adobe Experience Manager Assets** y, a continuación, **selecciona**.

   ![](assets/aem_assets_5.png)

El recurso se ha cargado a su envío de correo electrónico. Ahora puede especificar la audiencia de destino, confirmar la entrega y continuar enviándolo.
