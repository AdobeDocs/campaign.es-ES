---
product: campaign
title: Trabajo con plantillas de entrega
description: Aprenda a crear y utilizar plantillas de entrega en Campaign
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
source-git-commit: 822d1bee472330b6195ad9527a7e23e90c7650b4
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 50%

---

# Trabajar con plantilla de envíos{#creating-a-delivery-template}

Utilice plantillas de envío para estandarizar el aspecto creativo y así ejecutar y iniciar las campañas con mayor rapidez.

Una plantilla puede incluir sistemáticamente:

* Tipologías
* Direcciones de remitente y respuesta
* Bloques de personalización básicos
* Vínculos a páginas espejo y baja vínculos
* Contenido, logotipo de la empresa o firma
* Otras propiedades de envío, como la validez de los recursos, los parámetros de reintento o la configuración de cuarentena.

![](assets/do-not-localize/how-to-video.png) [Descubra esta función en vídeo](#delivery-template-video)

Para crear una plantilla de envío, puede duplicar una plantilla integrada, convertir una entrega existente en una plantilla o crear una plantilla de envío desde cero.

## Copiar una plantilla existente{#copy-an-existing-template}

Campaign incluye un conjunto de plantillas integradas para cada canal: correo electrónico, push, SMS, correo postal, etc.

La forma más sencilla de crear una plantilla de envío es duplicar y personalizar una plantilla integrada.

Para duplicar una plantilla de envío, siga los pasos a continuación:

1. Vaya a **[!UICONTROL Resources > Templates > Delivery templates]** en el explorador de Adobe Campaign.
1. Seleccione una plantilla de envío integrada. Las plantillas integradas aparecen en negrita en la lista.
1. Haga clic con el botón derecho y seleccione **[!UICONTROL Duplicate]**.

   ![](assets/duplicate-built-in-template.png)

1. Defina la configuración de la plantilla y guarde la nueva plantilla.

   ![](assets/delivery-template-new.png)

La plantilla se añade a la lista de plantillas de envío. Ahora puede seleccionarlo al crear un nuevo envío.

![](assets/select-the-new-template.png)

## Conversión de una entrega existente en una plantilla {#convert-an-existing-delivery}

Puede convertir una entrega en una plantilla y usarla con las nuevas acciones de envío repetidas.

Para convertir una entrega en una plantilla, siga los pasos a continuación:

1. Seleccione la entrega en la lista de entrega, a la que se puede acceder mediante el **[!UICONTROL Campaign management]** nodo del explorador de Campaign.

1. Haga clic con el botón derecho y seleccione **[!UICONTROL Actions > Save as template...]**.

   ![](assets/save-as-template.png)

1. Edite las propiedades de la entrega y seleccione la carpeta donde se debe guardar la nueva plantilla (en la **[!UICONTROL Folder]** ), y la carpeta donde se deben crear los envíos creados basándose en esta plantilla (en la variable **[!UICONTROL Execution folder]** ).

   ![](assets/template-select-folders.png)

## Crear una plantilla nueva {#create-a-new-template}

>[!NOTE]
>
>Para evitar errores de configuración, Adobe recomienda que [duplicación de una plantilla integrada](#copy-an-existing-template) y personalice sus propiedades en lugar de crear una nueva plantilla.

Para configurar una plantilla de envíos desde cero, siga los pasos a continuación:

1. Vaya a la **Recursos** carpeta en el explorador de Campaign y seleccione **Plantillas** then **Plantillas de envío**.
1. Haga clic en **Nueva** en la barra de herramientas para crear una nueva plantilla de envío.
1. Configure las variables **Etiqueta** y **Nombre interno** de la carpeta.
1. Guarde la plantilla y vuelva a abrirla.
1. En el **Propiedades** , adapte la configuración.
1. En la pestaña **General**, confirme o cambie las ubicaciones seleccionadas en los menús desplegables **Carpeta de ejecución**, **Carpeta** y **Enrutamiento**.
1. Rellene la categoría **parámetros de correo electrónico** con el asunto del correo electrónico y la población objetivo.
1. Añada el **contenido HTML** para personalizar la plantilla. Puede mostrar un vínculo a una página espejo y un vínculo para darse de baja.
1. Seleccione la pestaña **Preview.** En el menú desplegable **Personalización de prueba**, seleccione **Destinatario** para previsualizar la plantilla como el perfil elegido.
1. Haga clic en **Save**. La plantilla ya está lista para utilizarse en una entrega.


## Creación de una entrega a partir de una plantilla{#create-a-delivery-from-a-template}

Para crear una entrega basada en una plantilla existente, seleccione la plantilla de la lista de plantillas de entrega disponibles.

![](assets/select-the-new-template.png)

Si no puede ver la plantilla, haga clic en el botón **[!UICONTROL Select link]** a la derecha del campo para examinar las carpetas de Campaign.

![](assets/browse-templates.png)

Seleccione el directorio que desee en el campo **[!UICONTROL Folder]** o haga clic en el icono **[!UICONTROL Display sub-levels]** para mostrar el contenido de los directorios en los subárboles del directorio actual.

Seleccione la plantilla de envíos que va a utilizar y haga clic en **[!UICONTROL Ok]**.

### Ejecución de una plantilla {#execute-a-template}

Puede iniciar la ejecución de una plantilla directamente desde la lista de plantillas sin tener que crear primero una entrega.

Para ello, seleccione la plantilla que desea ejecutar y haga clic con el botón derecho del ratón. Seleccione **[!UICONTROL Actions>Execute the delivery template...]**.

También puede usar **[!UICONTROL File>Actions>Execute the delivery template...]**.

![](assets/execute-delivery-template.png)

Introduzca los parámetros de envío y haga clic en **[!UICONTROL Send]**.

Esta acción genera una entrega en la carpeta asociada a la plantilla. El nombre de este envío es el nombre de la plantilla de envío desde la que se creó.


## Tutoriales en vídeo {#delivery-template-video}

### Configuración de una plantilla de envíos

En el siguiente vídeo se muestra cómo configurar una plantilla para un envío ad hoc.

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### Configuración de propiedades de plantillas de envíos

El siguiente vídeo muestra cómo configurar las propiedades de las plantillas de envíos y explica cada propiedad en detalle.

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### Implementación de una plantilla de envíos ad-hoc

En este vídeo se explica cómo implementar una plantilla de envíos de correo electrónico ad-hoc, y se explica la diferencia entre un envío de correo electrónico y un flujo de trabajo de envío.

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

Hay disponibles más vídeos de procedimientos para Campaign Classic [aquí](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=es).
