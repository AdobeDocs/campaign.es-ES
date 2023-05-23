---
product: campaign
title: Plantillas de campañas de marketing
description: Plantillas de campañas de marketing
feature: Campaigns, Templates
exl-id: 1bd8d3e7-aaa9-4e00-96bb-0d30614ab380
source-git-commit: 1c879c7803c346d4b602089a22c2639eb83e82be
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 55%

---

# Creación y configuración de plantillas de campaña {#campaign-templates}

Todas las campañas de marketing se basan en una plantilla que almacena las características y capacidades principales. Campaign viene con una plantilla integrada para crear campañas. Esta plantilla tiene todas las funcionalidades habilitadas: Documentos, Direcciones semilla, Aprobaciones, Contornos de entrega, etc.

Las funcionalidades disponibles dependen de los permisos, los complementos y la configuración de la plataforma de Adobe Campaign.


>[!NOTE]
>
>El árbol se muestra al hacer clic en el icono **[!UICONTROL Explorer]** de la página de inicio.

Se proporciona una plantilla para crear una campaña sin ninguna configuración específica definida. Puede crear y configurar las plantillas de campañas y luego crear campañas a partir de estas plantillas.

## Creación de una plantilla de campaña {#create-a-campaign-template}

Para crear una plantilla de campaña, siga estos pasos:

1. Abrir campaña **Explorer** y vaya a **Recursos > Plantillas > Plantillas de campaña**.
1. Clic **Nuevo** en la barra de herramientas situada encima de la lista de plantillas.

![](assets/campaign-template-node.png)

También puede **duplicado** la plantilla integrada para reutilizar y adaptar su configuración. Para ello, haga clic con el botón derecho en la plantilla y seleccione **Duplicar**.

1. Introduzca la etiqueta de la nueva plantilla de campaña.
1. Haga clic en **Save** y vuelva a abrir la plantilla.
1. En el **Editar** pestaña, defina las propiedades de la plantilla.
1. Seleccionar **Parámetros de campaña avanzados...** para añadir un flujo de trabajo a la plantilla de campaña.

   ![](assets/campaign-template-parameters.png)

1. Cambie el **Segmentación y flujos de trabajo** valor hasta **Sí**. y confirme. Obtenga información sobre cómo añadir funcionalidades en [esta sección](#typology-of-enabled-modules).
1. El **Segmentación y flujos de trabajo** se añade a la plantilla. Clic **Añadir un flujo de trabajo...**, introduzca un **Etiqueta** y haga clic en **Ok**.
1. Cree su flujo de trabajo según sus necesidades.

   ![](assets/campaign-template-create-wf.png)

1. Haga clic en **Save**. La plantilla ya está lista para utilizarse para crear una nueva campaña.

Las distintas pestañas y subpestañas de la plantilla de campaña permiten acceder a su configuración, tal y como se describe en [Configuración general](#general-configuration).

## Selección de módulos {#select-modules}

El vínculo **[!UICONTROL Advanced campaign parameters...]** permite habilitar y deshabilitar los trabajos de las campañas en función de esta plantilla. Seleccione las funciones que desee habilitar en las campañas creadas en función de esta plantilla.

![](assets/campaign-template-select-modules.png)

Si no se selecciona una funcionalidad, los elementos correspondientes del proceso (menús, iconos, opciones, pestañas, subpestañas, etc.) no aparecen en la interfaz de la plantilla ni en las campañas basadas en esta plantilla. Las pestañas a la izquierda de los detalles de la campaña y las pestañas disponibles coinciden con las funcionalidades seleccionadas en la plantilla. Por ejemplo, la variable **Gastos y objetivos** no está activada, la función correspondiente **[!UICONTROL Budget]** no se muestran en las campañas basadas en esta plantilla.

Además, los accesos directos a las ventanas de configuración se añaden al panel de campañas. Cuando una funcionalidad está habilitada, un vínculo directo le permite acceder a ella desde el panel de campañas.

### Muestras de configuración

* Por ejemplo, con la siguiente configuración:

   ![](assets/campaign-template-select-functionalities.png)

   El panel de campañas muestra:

   ![](assets/campaign-template-dashboard-sample-1.png)

   Tenga en cuenta que la variable **[!UICONTROL Targeting and workflows]** falta la pestaña.

   Estas son las funcionalidades disponibles:

   ![](assets/campaign-template-edit-sample-1.png)

   Tenga en cuenta que la variable **[!UICONTROL Budget]** falta la pestaña.

   La configuración avanzada de la campaña también refleja esta configuración.

   ![](assets/campaign-template-parameters-sample-1.png)

   Tenga en cuenta que la variable **[!UICONTROL Approvals]** La pestaña no está disponible.

* Con esta configuración:
   ![](assets/campaign-template-dashboard-sample-2.png)

   El panel de campañas muestra:

   ![](assets/campaign-template-select-functionalities-2.png)

   Tenga en cuenta que la variable **[!UICONTROL Targeting and workflows]** está disponible, pero la pestaña **Agregar un documento** falta el vínculo.

   Estas son las funcionalidades disponibles:

   ![](assets/campaign-template-edit-sample-2.png)

   Tenga en cuenta que la variable **[!UICONTROL Budget]** está disponible.

   La configuración avanzada de la campaña también refleja esta configuración.

   ![](assets/campaign-template-parameters-sample-2.png)

   Tenga en cuenta que la variable **[!UICONTROL Approvals]** está disponible, pero la pestaña **[!UICONTROL Control population]** y **[!UICONTROL Seed addresses]** Las pestañas no están activadas.


## Tipología de módulos {#typology-of-enabled-modules}

* **Grupo de control**

   Cuando se selecciona este módulo, se añade una pestaña adicional a la configuración avanzada de la plantilla y a las campañas basadas en esta plantilla. La configuración se puede definir mediante la plantilla o bien por separado para cada campaña. Obtenga más información sobre los grupos de control en [esta sección](marketing-campaign-deliveries.md#defining-a-control-group).

   ![](assets/template-activate-1.png)


* **Direcciones semilla**

   Cuando se selecciona este módulo, se añade una pestaña adicional a la configuración avanzada de la plantilla y a las campañas basadas en esta plantilla. La configuración se puede definir mediante la plantilla o por separado para cada campaña.

   ![](assets/template-activate-2.png)

* **Documentos**

   Cuando se selecciona este módulo, se añade una pestaña adicional a la pestaña **[!UICONTROL Edit]** de la plantilla y a las campañas basadas en esta plantilla. Los documentos adjuntos se pueden agregar desde la plantilla o bien por separado para cada campaña. Obtenga más información sobre los documentos en [esta sección](marketing-campaign-deliveries.md#manage-associated-documents).

   ![](assets/template-activate-3.png)

* **Descripción del envío**

   Cuando se selecciona este módulo, se añade una subpestaña **[!UICONTROL Delivery outlines]** a la pestaña **[!UICONTROL Documents]** para definir los esquemas de entrega de la campaña. Obtenga más información sobre los esquemas de entrega en [esta sección](marketing-campaign-assets.md#delivery-outlines).

   ![](assets/template-activate-4.png)

* **Establecimiento de objetivos y flujos de trabajo**

   Al seleccionar el módulo de **[!UICONTROL Targeting and workflows]**, se añade una pestaña para permitirle crear uno o más flujos de trabajo para las campañas basadas en esta plantilla. Los flujos de trabajo también se pueden configurar por separado para cada campaña basada en esta plantilla. Obtenga más información sobre los flujos de trabajo de campañas en [esta sección](marketing-campaign-deliveries.md#build-the-main-target-in-a-workflow).

   ![](assets/template-activate-5.png)

   Cuando este módulo está habilitado, se crea un **[!UICONTROL Jobs]** se añade a la configuración avanzada de la campaña para definir la secuencia de ejecución del proceso.

* **Aprobaciones**

   Si activa la variable **[!UICONTROL Approvals]**, puede seleccionar los procesos de aprobación y los operadores asignados al proceso de aprobación. Obtenga más información sobre aprobaciones en [esta sección](marketing-campaign-approval.md#select-reviewers).

   ![](assets/template-activate-6.png)

   Puede elegir si desea habilitar o no la aprobación del proceso mediante el **[!UICONTROL Approvals]** de la sección configuración avanzada de plantillas.

* **Gastos y objetivos**

   Cuando se selecciona este módulo, se añade una pestaña **[!UICONTROL Budget]** a los detalles de la plantilla y las campañas basadas en esta plantilla, de modo que se pueda seleccionar el presupuesto asociado.

   ![](assets/template-activate-7.png)


## Propiedades de plantilla {#template-properties}

![](assets/template-op-type.png)

Cuando crea una plantilla de campaña, debe introducir la siguiente información:

* Introduzca el **etiqueta** de la plantilla: la etiqueta es obligatoria y es la etiqueta predeterminada para todas las campañas basadas en esta plantilla.
* Seleccione la **naturaleza** de la campaña en la lista desplegable. Los valores disponibles en esta lista son los guardados en la enumeración **[!UICONTROL natureOp]**.

Obtenga información sobre cómo acceder y configurar las enumeraciones en [esta página](../../v8/config/ui-settings.md#enumerations).


* Seleccione el **tipo de campaña**: única, recurrente o periódica. De manera predeterminada, las plantillas de campaña se aplican a las campañas únicas. Las campañas recurrentes y periódicas se detallan en [esta sección](recurring-periodic-campaigns.md).
* Especifique la duración de la campaña, es decir, el número de días durante los que se desarrolla la campaña. Al crear una campaña basada en esta plantilla, las fechas de inicio y finalización de la campaña se rellenan automáticamente.

   Si la campaña es recurrente, debe especificar las fechas de inicio y finalización de la campaña directamente en la plantilla.

* Especifique el **programa relacionado** de la plantilla: las campañas basadas en esta plantilla están vinculadas al programa seleccionado.

<!--
## Track campaign execution{#campaign-reverse-scheduling}

You can create a schedule for a campaign and track accomplishments, for instance to prepare an event schedule for a specific date. Campaign templates now let you calculate the start date of a task based on the end date of a campaign.


In the task configuration box, go to the **[!UICONTROL Implementation schedule]** area and check the **[!UICONTROL The start date is calculated based on the campaign end date]** box. (Here, "start date" is the task start date). Go to the **[!UICONTROL Start]** field and enter an interval: the task will start this long before the campaign end date. If you enter a period which is longer than the campaign is set to last, the task will begin before the campaign.

![](assets/mrm_task_in_template_start_date.png)

When you create a campaign using this template, the task start date will be calculated automatically. However, you can always change it later.-->
