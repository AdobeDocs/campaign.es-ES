---
product: campaign
title: Plantillas de campañas de marketing
description: Plantillas de campañas de marketing
feature: Campaigns, Templates
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 1bd8d3e7-aaa9-4e00-96bb-0d30614ab380
TQID: 'https://experienceleague.adobe.com/qmz-Sd1EJmACFfgozVirCHCaeiQN-lGKuxd9-VAPMHs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: baf8e746-117b-5e73-b179-0a83edc0295f
    internal-label: Templates
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '1331'
ht-degree: 37%
---
# Creación y configuración de plantillas de campaña {#campaign-templates}

Todas las campañas de marketing se basan en una plantilla que almacena las características y capacidades principales. Campaign viene con una plantilla integrada para crear campañas. Esta plantilla tiene todas las funcionalidades habilitadas: Documentos, Direcciones semilla, Aprobaciones, Contornos de entrega, etc.

Las funcionalidades disponibles dependen de los permisos, los complementos y la configuración de la plataforma de Adobe Campaign.


>[!NOTE]
>
>El árbol se muestra al hacer clic en el icono **[!UICONTROL Explorer]** de la página de inicio.

Se proporciona una plantilla integrada para crear una campaña sin ninguna configuración específica definida. Puede crear y configurar las plantillas de campañas y luego crear campañas a partir de estas plantillas.

## Creación de una plantilla de campaña {#create-a-campaign-template}

Para crear una plantilla de campaña, siga estos pasos:

1. Abra el **Explorador** de Campaign y vaya a **Recursos > Plantillas > Plantillas de campaña**.
1. Haga clic en **Nuevo** en la barra de herramientas situada encima de la lista de plantillas.

![Lista de plantillas de campaña en Recursos > Plantillas, con el botón Nuevo resaltado en la barra de herramientas.](assets/campaign-template-node.png)

También puede **duplicar** la plantilla integrada para reutilizar y adaptar su configuración. Para ello, haga clic con el botón derecho en la plantilla y seleccione **Duplicate**.

1. Introduzca la etiqueta de la nueva plantilla de campaña.
1. Haga clic en **Save** y vuelva a abrir la plantilla.
1. En la ficha **Editar**, defina las propiedades de la plantilla.
1. Seleccione el vínculo **Advanced campaign parameters...** para agregar un flujo de trabajo a la plantilla de campaña.

   ![Nueva pestaña Editar plantilla de campaña con el vínculo Advanced campaign parameters resaltado.](assets/campaign-template-parameters.png)

1. Cambie el valor de **Segmentación y flujos de trabajo** a **Sí**. y confirme la acción. Aprenda a agregar funcionalidades en [Tipología de módulos](#typology-of-enabled-modules).
1. La ficha **Segmentación y flujos de trabajo** se ha agregado a la plantilla. Haga clic en **Agregar un flujo de trabajo...**, escriba una **Etiqueta** y haga clic en **Aceptar**.
1. Cree su flujo de trabajo según sus necesidades.

   ![Pestaña Segmentación y flujos de trabajo de la plantilla con un flujo de trabajo que contiene Consulta y Lista de lectura que lleva a la entrega por correo electrónico.](assets/campaign-template-create-wf.png)

1. Haga clic en **Save**. La plantilla ya está lista para utilizarse para crear una nueva campaña.

Las distintas pestañas y subpestañas de la plantilla de campaña permiten acceder a su configuración, tal y como se describe en [Configuración general](#general-configuration).

## Selección de módulos {#select-modules}

El vínculo **[!UICONTROL Advanced campaign parameters...]** permite habilitar y deshabilitar los trabajos de las campañas en función de esta plantilla. Seleccione las funciones que desee habilitar en las campañas creadas en función de esta plantilla.

![La ficha Configuración avanzada enumera todas las funciones con un valor Sí o No; Gastos y objetivos es No.](assets/campaign-template-select-modules.png)

Si no se selecciona una funcionalidad, los elementos correspondientes del proceso (menús, iconos, opciones, pestañas, subpestañas, etc.) no aparecen en la interfaz de la plantilla ni en las campañas basadas en esta plantilla. Las pestañas a la izquierda de los detalles de la campaña y las pestañas disponibles coinciden con las funcionalidades seleccionadas en la plantilla. Por ejemplo, si la funcionalidad **Gastos y objetivos** no está habilitada, la pestaña **[!UICONTROL Budget]** correspondiente no se muestra en las campañas basadas en esta plantilla.

Además, los accesos directos a las ventanas de configuración se añaden al panel de control de campañas. Cuando una funcionalidad está habilitada, un vínculo directo le permite acceder a ella desde el panel de control de campañas.

### Muestras de configuración

* Por ejemplo, con la siguiente configuración:

  ![Configuración avanzada: grupo de control, direcciones semilla y documentos establecidos en Sí; aprobaciones, segmentación y flujos de trabajo establecidos en No.](assets/campaign-template-select-functionalities.png)

  El panel de campañas muestra:

  ![Panel de campañas solo con las fichas Panel y Editar, y Agregar una entrega y Agregar vínculos a documentos.](assets/campaign-template-dashboard-sample-1.png)

  Observe que falta la ficha **[!UICONTROL Targeting and workflows]**.

  Estas son las funcionalidades disponibles:

  ![Pestaña Editar de la campaña con las secciones Propiedades, Documentos y Auditoría y sin sección Presupuesto.](assets/campaign-template-edit-sample-1.png)

  Observe que falta la ficha **[!UICONTROL Budget]**.

  La configuración avanzada de la campaña también refleja esta configuración.

  ![Configuración avanzada de Campaign con fichas de población de control y direcciones semilla y sin ficha de Aprobaciones.](assets/campaign-template-parameters-sample-1.png)

  Tenga en cuenta que la ficha **[!UICONTROL Approvals]** no está disponible.

* Con esta configuración:
  ![Configuración avanzada: aprobaciones, segmentación y flujos de trabajo, gastos y objetivos establecidos en Sí; otras funcionalidades: No.](assets/campaign-template-dashboard-sample-2.png)

  El panel de campañas muestra:

  ![Tablero de campaña con la ficha Segmentación y flujos de trabajo y un vínculo Agregar envío, pero no un vínculo Agregar documento.](assets/campaign-template-select-functionalities-2.png)

  Tenga en cuenta que la ficha **[!UICONTROL Targeting and workflows]** está disponible, pero falta el vínculo **Agregar documento**.

  Estas son las funcionalidades disponibles:

  ![Editar ficha con la sección Presupuesto abierta, que muestra las fichas de presupuesto, objetivos y costos y gastos relacionados.](assets/campaign-template-edit-sample-2.png)

  Tenga en cuenta que la ficha **[!UICONTROL Budget]** está disponible.

  La configuración avanzada de la campaña también refleja esta configuración.

  ![Configuración avanzada con la ficha Aprobaciones y validaciones de trabajo, y sin fichas Población de control o Direcciones semilla.](assets/campaign-template-parameters-sample-2.png)

  Tenga en cuenta que la ficha **[!UICONTROL Approvals]** está disponible, pero las fichas **[!UICONTROL Control population]** y **[!UICONTROL Seed addresses]** no están habilitadas.


## Tipología de módulos {#typology-of-enabled-modules}

* **Grupo de control**

  Cuando se selecciona este módulo, se añade una pestaña adicional a la configuración avanzada de la plantilla y a las campañas basadas en esta plantilla. La configuración se puede definir mediante la plantilla o bien por separado para cada campaña. Obtenga más información acerca de los grupos de control en [envíos de campañas de marketing](marketing-campaign-deliveries.md).

  ![Configuración avanzada: ficha Población de control con la opción de grupo de control habilitada y un vínculo Editar para su configuración.](assets/template-activate-1.png)


* **Direcciones semilla**

  Cuando se selecciona este módulo, se añade una pestaña adicional a la configuración avanzada de la plantilla y a las campañas basadas en esta plantilla. La configuración se puede definir mediante la plantilla o bien por separado para cada campaña.

  ![Configuración avanzada: ficha Direcciones semilla con un vínculo Importar plantillas semilla y una lista de direcciones semilla.](assets/template-activate-2.png)

* **Documentos**

  Cuando se selecciona este módulo, se añade una pestaña adicional a la pestaña **[!UICONTROL Edit]** de la plantilla y a las campañas basadas en esta plantilla. Los documentos adjuntos se pueden agregar desde la plantilla o bien por separado para cada campaña. Obtenga más información acerca de los documentos en [Envíos de campañas de marketing](marketing-campaign-deliveries.md).

  ![La sección Documentos de la ficha Editar muestra los documentos adjuntos, con los botones Agregar, Eliminar y Detalle.](assets/template-activate-3.png)

* **Descripción de la entrega**

  Cuando se selecciona este módulo, se añade una subpestaña **[!UICONTROL Delivery outlines]** a la pestaña **[!UICONTROL Documents]** para definir los esquemas de entrega de la campaña. Obtenga más información acerca de los esquemas de entrega en [Usar esquemas de entrega](marketing-campaign-assets.md#delivery-outlines).

  ![Subpestaña Contornos de entrega de la sección Documentos con el vínculo Añadir un esquema de entrega.](assets/template-activate-4.png)

* **Establecimiento de objetivos y flujos de trabajo**

  Al seleccionar el módulo de **[!UICONTROL Targeting and workflows]**, se añade una pestaña para permitirle crear uno o más flujos de trabajo para las campañas basadas en esta plantilla. Los flujos de trabajo también se pueden configurar individualmente para cada campaña basada en esta plantilla.Obtenga más información acerca de los flujos de trabajo de la campaña en [Envíos de campañas de marketing](marketing-campaign-deliveries.md).

  ![Ficha Segmentación y flujos de trabajo con un flujo de trabajo: consulta y lista de lectura, anulación de duplicación y, a continuación, envío móvil](assets/template-activate-5.png).

  Cuando este módulo está habilitado, se agrega una pestaña **[!UICONTROL Jobs]** a la configuración avanzada de la campaña para definir la secuencia de ejecución del proceso.

* **Aprobaciones**

  Si activa **[!UICONTROL Approvals]**, puede seleccionar los procesos de aprobación y los operadores asignados al proceso de aprobación. Obtenga más información sobre aprobaciones en [Seleccionar revisores](marketing-campaign-approval.md#select-reviewers).

  ![Pestaña Aprobaciones de configuración avanzada con aprobaciones de contenido, destino, presupuesto y extracción habilitadas y revisores asignados.](assets/template-activate-6.png)

  Puede elegir si desea habilitar o no la aprobación del proceso mediante la pestaña **[!UICONTROL Approvals]** de la sección de configuración avanzada de plantillas.

* **Gastos y objetivos**

  Cuando se selecciona este módulo, se añade una pestaña **[!UICONTROL Budget]** a los detalles de la plantilla y las campañas basadas en esta plantilla, de modo que se pueda seleccionar el presupuesto asociado.

  ![Sección Presupuesto de la ficha Editar con campos de presupuesto relacionados, Objetivos y la ficha Costos con líneas de costo.](assets/template-activate-7.png)


## Propiedades de plantilla {#template-properties}

![Pestaña Editar plantilla de campaña con la lista desplegable Tipo de operación abierta, que muestra Único, Recurrente y Periódico.](assets/template-op-type.png)

Cuando crea una plantilla de campaña, debe introducir la siguiente información:

* Escriba la **etiqueta** de la plantilla: la etiqueta es obligatoria y es la etiqueta predeterminada para todas las campañas basadas en esta plantilla.
* Seleccione la **naturaleza** de la campaña en la lista desplegable. Los valores disponibles en esta lista son los guardados en la enumeración **[!UICONTROL natureOp]**.

  Obtenga información sobre cómo acceder y configurar las enumeraciones en [Administrar enumeraciones](../../v8/config/enumerations.md).

* Seleccione el **tipo de campaña**: única, recurrente o periódica. De manera predeterminada, las plantillas de campaña se aplican a las campañas únicas. Las campañas recurrentes y periódicas se detallan en [Crear campañas recurrentes y periódicas](recurring-periodic-campaigns.md).
* Especifique la duración de la campaña, es decir, el número de días durante los que se desarrolla la campaña. Al crear una campaña basada en esta plantilla, las fechas de inicio y finalización de la campaña se rellenan automáticamente.

  Si la campaña es recurrente, debe especificar las fechas de inicio y finalización de la campaña directamente en la plantilla.

* Especifique el **programa relacionado** de la plantilla: las campañas basadas en esta plantilla están vinculadas al programa seleccionado.

<!--
## Track campaign execution{#campaign-reverse-scheduling}

You can create a schedule for a campaign and track accomplishments, for instance to prepare an event schedule for a specific date. Campaign templates now let you calculate the start date of a task based on the end date of a campaign.


In the task configuration box, go to the **[!UICONTROL Implementation schedule]** area and check the **[!UICONTROL The start date is calculated based on the campaign end date]** box. (Here, "start date" is the task start date). Go to the **[!UICONTROL Start]** field and enter an interval: the task will start this long before the campaign end date. If you enter a period which is longer than the campaign is set to last, the task will begin before the campaign.

![](assets/mrm_task_in_template_start_date.png)

When you create a campaign using this template, the task start date will be calculated automatically. However, you can always change it later.
-->
