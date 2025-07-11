---
product: campaign
title: Creación de un flujo de trabajo
description: Descubra cómo generar un flujo de trabajo
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: a6003fdb-1035-4b80-8831-73f30a0b4fb2
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 78%

---

# Creación de un flujo de trabajo {#build-a-workflow}

## Cree un nuevo flujo de trabajo {#create-a-new-workflow}

El flujo de trabajo de creación depende del tipo de flujos de trabajo. Puede hacer lo siguiente:

* Cree [flujos de trabajo de destino](#targeting-workflows) desde el nodo **[!UICONTROL Profiles and Targets]** > **[!UICONTROL Jobs]** > **[!UICONTROL Targeting workflows]** del explorador o desde la pestaña **[!UICONTROL Profiles and Targets]** de la página principal, a través de la subpestaña **[!UICONTROL Targeting workflows]**.

  ![](assets/create-targeting-wf.png)

* Crear [flujos de trabajo de campaña](#campaign-workflows) desde la ficha **[!UICONTROL Targeting and workflows]** de una campaña

* Cree [flujos de trabajo técnicos](#technical-workflows) desde el nodo **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** del explorador. La práctica recomendada es crear una carpeta de flujo de trabajo específica para guardar los flujos de trabajo técnicos.

Haga clic en el botón **[!UICONTROL New]** situado sobre la lista de flujos de trabajo.

![](assets/create_a_wf_icon.png)

Introduzca una etiqueta y haga clic en **[!UICONTROL Save]**.

## Adición y vinculación de actividades {#add-and-link-activities}

A continuación debe definir las distintas actividades y vincularlas todas en el diagrama. En esta fase de la configuración, podemos ver la etiqueta del diagrama y el estado del flujo de trabajo (edición en curso). La sección inferior de la ventana se utiliza para editar solo el diagrama. Contiene una barra de herramientas, una paleta de actividades (a la izquierda) y el diagrama (a la derecha).

![](assets/new-workflow-2.png)

>[!NOTE]
>
>Si no se muestra la paleta, haga clic en el primer botón de la barra de herramientas del flujo de trabajo para mostrarla.

Las actividades se agrupan por categorías en las diferentes pestañas de la paleta. Las pestañas y actividades disponibles pueden variar según el tipo de flujo de trabajo (técnico, de objetivos o flujo de trabajo de la campaña).

* La primera pestaña contiene actividades de establecimiento de objetivos y de manipulación de datos. Estas actividades se detallan en [Actividades de establecimiento de objetivos](targeting-activities.md).
* La segunda pestaña contiene las actividades de planificación, que se utilizan principalmente para coordinar otras actividades. Estas actividades se detallan en [Actividades de control de flujos](flow-control-activities.md).
* La tercera pestaña contiene herramientas y acciones que se pueden utilizar en el flujo de trabajo. Estas actividades se detallan en [Actividades de acción](action-activities.md).
* La cuarta pestaña contiene actividades que dependen de un evento determinado, como la recepción de un correo electrónico o la llegada de un archivo en un servidor. Estas actividades se detallan en [Actividades de eventos](event-activities.md).

Creación del diagrama

1. Añada una actividad seleccionándola en la paleta y moviéndola al diagrama mediante una operación de arrastrar y soltar.

   En el diagrama, añada una actividad **Start** y luego una actividad **Delivery**.

   ![](assets/new-workflow-3.png)

1. Para vincular las actividades, arrastre la transición de la actividad **Start** y suéltela sobre la actividad **Delivery**.

   ![](assets/new-workflow-4.png)

   Puede enlazar automáticamente una actividad a la anterior colocando la nueva actividad al final de la transición.

1. Añada las actividades que necesita y vincúlelas como se muestra en el diagrama siguiente.

   ![](assets/new-workflow-5.png)

>[!CAUTION]
>
>Puede copiar y pegar actividades en un mismo flujo de trabajo. Sin embargo, no se recomienda copiar y pegar actividades en diferentes flujos de trabajo. Algunas configuraciones asociadas a actividades como Deliveries y Scheduler podrían provocar conflictos y errores al ejecutar el flujo de trabajo de destino. En su lugar, le recomendamos que **duplique** los flujos de trabajo. Para obtener más información, consulte [Duplicación de flujos de trabajo](#duplicate-workflows).

Puede cambiar la visualización y el diseño del gráfico mediante los siguientes elementos:

* **Uso de la barra de herramientas**

  La barra de herramientas de edición del diagrama le permite acceder a las funciones de diseño y ejecución del flujo de trabajo.

  ![](assets/wf-toolbar.png)

  Esto le permite adaptar el diseño de la herramienta de edición: visualización de la paleta y descripción general, tamaño y alineación de los objetos gráficos.

  ![](assets/s_user_segmentation_toolbar.png)

  Los iconos relacionados con el progreso y la visualización de registros se describen en estas secciones:

   * [Mostrar progreso](monitor-workflow-execution.md#displaying-progress)
   * [Mostrar registros](monitor-workflow-execution.md#displaying-logs)

* **Alineación de objetos**

  Para alinear los iconos, selecciónelos y haga clic en el icono **[!UICONTROL Align vertically]** o **[!UICONTROL Align horizontally]**.

  Utilice la tecla **Ctrl** para seleccionar varias actividades separadas o para anular la selección de una o varias actividades. Haga clic en el fondo del diagrama para anular la selección de todo.

* **Gestión de imágenes**

  Puede personalizar la imagen de fondo del diagrama, así como las relacionadas con las distintas actividades. Consulte [Cambio de imágenes de actividad](change-activity-images.md).

## Configuración de actividades {#configure-activities}

Haga doble clic en una actividad para configurarla o haga clic con el botón derecho y seleccione **[!UICONTROL Open...]**

>[!NOTE]
>
>Las actividades de flujo de trabajo de Campaign se detallan en [esta sección](activities.md).

La primera pestaña contiene la configuración básica. La pestaña **[!UICONTROL Advanced]** contiene los parámetros adicionales, que se utilizan principalmente para definir el comportamiento cuando se encuentra un error para especificar la duración de la ejecución de una actividad y para introducir una secuencia de comandos de inicialización.

Para comprender mejor las actividades y mejorar la legibilidad del flujo de trabajo, se pueden introducir comentarios en las actividades.

![](assets/example1-comment.png)

Estos comentarios se muestran automáticamente cuando los operadores se desplazan por la actividad.

![](assets/example2-comment.png)


## Plantillas de flujo de trabajo {#workflow-templates}

Las plantillas de flujo de trabajo contienen la configuración general de las propiedades y posiblemente diversas actividades concatenadas dentro de un diagrama. Esta configuración se puede reutilizar para crear nuevos flujos de trabajo que contengan un determinado número de elementos preconfigurados

Puede crear nuevas plantillas de flujo de trabajo basadas en plantillas existentes o cambiar un flujo de trabajo en una plantilla directamente.

Las plantillas de flujo de trabajo se almacenan en el nodo **[!UICONTROL Resources > Templates > Workflow templates]** del Explorador.

Además de las propiedades habituales del flujo de trabajo, las propiedades de la plantilla permiten especificar el archivo de ejecución para los flujos de trabajo creados en función de esta plantilla.

![](assets/wf-template-properties.png)

## Duplicación de flujos de trabajo {#duplicate-workflows}

Se pueden duplicar diferentes tipos de flujos de trabajo. Una vez duplicados, las modificaciones del flujo de trabajo no se transfieren a la copia del flujo de trabajo.

Adobe recomienda duplicar un flujo de trabajo en lugar de realizar una copia o pegado de las actividades. Cuando se copia una actividad, se conserva toda su configuración. Para las actividades de canal, el objeto de envío asociado a la actividad también se copia, lo que puede dar lugar a problemas importantes.

1. Haga clic con el botón derecho en un flujo de trabajo.
1. Haga clic en **Duplicate**.

   ![](assets/duplicate-workflows.png)

1. En la ventana de flujo de trabajo, cambie la etiqueta de flujo de trabajo.
1. Haga clic en **Save**.

