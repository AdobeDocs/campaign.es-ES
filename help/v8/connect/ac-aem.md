---
title: Trabajo con Campaign y Adobe Experience Manager
description: Aprenda a trabajar con Campaign y Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
TQID: 'https://experienceleague.adobe.com/LM635Kjl7bucy1SMcEPuhCElUI7MNrO4B3fwo9fpyFQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: df0d6518-6f49-46e2-b46e-3bcc513f553f
    internal-label: Experience Manager integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 765af3342eb29f27dafa12f72634f5d91361bed5
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 11%
---
# Trabajo con Campaign y Adobe Experience Manager {#ac-aem}

La integración entre Adobe Campaign y Adobe Experience Manager le permite gestionar el contenido de las entregas de los correos electrónicos y los formularios directamente en Adobe Experience Manager.

## Uso de Adobe Experience Manager as a Cloud Service con la interfaz de usuario web de Campaign {#aem-cs-web-ui}

Con la interfaz de usuario web de Campaign, puede conectar su entorno de Adobe Experience Manager as a Cloud Service para centralizar el contenido. Una única fuente fiable para recursos y plantillas mantiene la coherencia de los mensajes de correo electrónico en todos los canales y evita la duplicación de contenido entre las dos soluciones.

* **Assets**: administre sus recursos en Adobe Experience Manager Assets y reutilícelos directamente en el contenido de su correo electrónico. [Más información](https://experienceleague.adobe.com/es/docs/campaign-web/v8/integrations/aem-assets){target="_blank"}
* **Plantillas**: cree y apruebe plantillas de correo electrónico en Adobe Experience Manager as a Cloud Service y, a continuación, utilícelas como plantillas de contenido en las entregas. [Más información](https://experienceleague.adobe.com/es/docs/campaign-web/v8/integrations/aem-content){target="_blank"}

La conexión depende de una cuenta externa **[!UICONTROL AEM]** configurada en la consola del cliente. Ver [Cuentas externas](../config/external-accounts.md).

## Uso de Adobe Experience Manager con la consola del cliente {#aem-console}

Las secciones siguientes describen la integración en la consola del cliente de Campaign.

[Obtenga más información acerca de Adobe Experience Manager en este documento](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html?lang=es#aem-and-adobe-campaign-integration-workflow){target="_blank"}.


>[!NOTE]
>
>Como usuario de Cloud Services administrados, [póngase en contacto con Adobe](../start/campaign-faq-comprehensive.md#support) para integrar Adobe Experience Manager con Campaign.

## Importación de contenido desde Adobe Experience Manager {#integrating-with-aem}

Esta integración puede utilizarse, por ejemplo, para crear un “newsletter” en Adobe Experience Manager para su uso posterior en Adobe Campaign como parte de una campaña de correo electrónico.

**Desde Adobe Experience Manager:**

1. Vaya a la instancia de autor de [!DNL Adobe Experience Manager] y haga clic en Adobe Experience en la esquina superior izquierda de la página. Elija **[!UICONTROL Sites]** en el menú.

   ![Menú de navegación de Adobe Experience Manager con la opción Sitios resaltada](assets/aem_authoring_1.png)

1. Acceso **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**.

1. Haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Page]** en el menú desplegable.

   ![Carpeta de correo electrónico de AEM Sites con el menú Crear abierto y Página seleccionada](assets/aem_authoring_2.png)

1. Seleccione la plantilla de **[!UICONTROL Adobe Campaign Email]** y asigne un nombre al newsletter.

1. Después de crear su página, acceda al menú **[!UICONTROL Page information]** y haga clic en **[!UICONTROL Open Properties]**.

   ![Editor de páginas de newsletter con el menú Page information abierto y las propiedades abiertas resaltadas](assets/aem_authoring_3.png)

1. Personalice el contenido del correo electrónico añadiendo componentes como, por ejemplo, campos de personalización de Adobe Campaign. Obtenga más información en [Documentación de Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html?lang=es#editing-email-content){target="_blank"}.

1. Cuando el correo electrónico esté listo, vaya al menú **[!UICONTROL Page information]** y haga clic en **[!UICONTROL Start workflow]**.

   ![Editor de página de newsletter con el menú Page information abierto e Iniciar flujo de trabajo resaltado](assets/aem_authoring_4.png)

1. En la primera lista desplegable, seleccione **[!UICONTROL Approve Adobe Campaign]** como modelo de flujo de trabajo y haga clic en **[!UICONTROL Start workflow]**.

   ![Iniciar diálogo de flujo de trabajo con la opción Aprobar para Adobe Campaign seleccionada como modelo de flujo de trabajo](assets/aem_authoring_5.png)

1. Aparecerá un aviso de exención de responsabilidad en la parte superior de la página que indica `This page is subject to the workflow Approve for Adobe Campaign`. Haga clic en **[!UICONTROL Complete]** al lado del aviso legal para confirmar la revisión y luego haga clic en **[!UICONTROL Ok]**.

1. Vuelva a hacer clic en **[!UICONTROL Complete]** y seleccione **[!UICONTROL Newsletter approval]** en la lista desplegable **[!UICONTROL Next Step]**.

   ![Completar cuadro de diálogo de elemento de trabajo con la aprobación de la newsletter seleccionada en la lista Paso siguiente y el botón Aceptar](assets/aem_authoring_6.png)

El boletín ya está listo y sincronizado en Adobe Campaign.

**Desde Adobe Campaign:**

1. En la pestaña **[!UICONTROL Campaigns]** , haga clic en **[!UICONTROL Deliveries]** luego **[!UICONTROL Create]**.

1. Elija la plantilla **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** del menú desplegable **[!UICONTROL Delivery template]**.

   ![Lista de plantillas de envíos de campaña con envío de correo electrónico con contenido de AEM (mailAEMContent) seleccionado](assets/aem_authoring_7.png)

1. Añada a la entrega una **[!UICONTROL Label]** y haga clic en **[!UICONTROL Continue]**.

1. Haga clic en **[!UICONTROL Synchronize]** para acceder a sus envíos de AEM.

   Si el botón no está visible en la interfaz, vaya al botón **[!UICONTROL Properties]** y acceda a la pestaña **[!UICONTROL Advanced]**. Asegúrese de que el campo **[!UICONTROL Content editing mode]** esté configurado en **[!UICONTROL AEM]** e introduzca los detalles de la instancia de AEM en el campo **[!UICONTROL AEM account]**.

   ![Barra de herramientas de envío de correo electrónico de Campaign con el botón Sincronizar resaltado](assets/aem_authoring_8.png)

1. Seleccione la entrega de AEM creada anteriormente en [!DNL Adobe Experience Manager] y confirme haciendo clic en **[!UICONTROL Ok]**.

   ![Sincronizar con el cuadro de diálogo de contenido de AEM que enumera los correos electrónicos de AEM aprobados con la fila de Newsletter seleccionada](assets/aem_authoring_11.png)

1. Asegúrese de hacer clic en el botón **[!UICONTROL Refresh content]** cada vez que se realicen modificaciones en la entrega de AEM.

   ![Envío de correo electrónico sincronizado con el botón Actualizar contenido resaltado y el botón Desincronizar](assets/aem_authoring_12.png)

1. Para eliminar la vinculación entre Experience Manager y Campaign, haga clic en **[!UICONTROL Desynchronize]**.

El correo electrónico está listo para enviarse a la audiencia.

## Importar recursos desde la biblioteca de Adobe Experience Manager Assets {#assets-library}

También puede insertar recursos directamente desde su [!DNL Adobe Experience Manager Assets Library] mientras edita un mensaje de correo electrónico o una página de aterrizaje en Adobe Campaign. Esta funcionalidad se encuentra detallada en [Documentación de Adobe Experience Manager Assets](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=es){target="_blank"}.

**Desde Adobe Experience Manager:**

1. Vaya a la instancia de autor de [!DNL Adobe Experience Manager] y haga clic en Adobe Experience en la esquina superior izquierda de la página. Elija **[!UICONTROL Assets]** `>` **[!UICONTROL Files]** en el menú.

   ![Menú de navegación de AEM Assets con la opción Archivos resaltada](assets/aem_assets_1.png)

1. Haga clic en **Crear** y luego en **Archivos** para importar el recurso en la **biblioteca de Adobe Experience Manager Assets**. Obtenga más información en [Documentación de Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=es#uploading-assets){target="_blank"}.

   ![Vista Archivos de AEM Assets con el menú Crear abierto y Archivos seleccionados para cargar un recurso](assets/aem_assets_2.png)

1. Cambie el nombre del recurso si es necesario y seleccione **Cargar**.

El recurso se ha cargado a la **biblioteca de Adobe Experience Manager Assets**.

**Desde Adobe Campaign:**

1. En Adobe Campaign, para crear una entrega nueva, vaya a la pestaña **Campañas**, haga clic en **Envíos** y haga clic en el botón **Crear** situado sobre la lista de envíos existentes.

   ![Lista de envíos de campaña en la pestaña Campañas con el botón Crear resaltado](assets/aem_assets_3.png)

1. Seleccione una **plantilla de envíos** y asigne un nombre a la entrega.

1. Defina y personalice el contenido del mensaje. [Más información](../send/email.md)

1. Para usar tu **biblioteca Adobe Experience Manager Assets**, accede a **[!UICONTROL Properties]** de tu entrega de AEM y selecciona la pestaña **[!UICONTROL Advanced]**.

   Elija su **cuenta de AEM** y habilite la opción **[!UICONTROL Use above AEM instance as shared asset library]**.

   ![Pestaña Propiedades de entrega avanzadas con conjunto de cuentas de AEM y opción de biblioteca de recursos compartidos habilitada](assets/aem_authoring_9.png)

1. Desde el icono **Image**, accede al menú **[!UICONTROL Select a shared asset]**.

   ![Menú de imagen del editor de correo electrónico de Campaign con Seleccionar un recurso compartido resaltado](assets/aem_assets_4.png)

1. En la ventana de selección, selecciona una imagen de tu **biblioteca Adobe Experience Manager Assets** y, a continuación, **selecciona**.

   ![Seleccione una ventana de recursos compartidos que enumere los archivos de biblioteca de AEM Assets con jogging-newsletter.jpg seleccionado](assets/aem_assets_5.png)

El recurso se ha cargado a su envío de correo electrónico. Ahora puede especificar la audiencia de destino, confirmar la entrega y continuar enviándolo.
