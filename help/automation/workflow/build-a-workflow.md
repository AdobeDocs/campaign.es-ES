---
product: campaign
title: Creación de un flujo de trabajo
description: Descubra cómo generar un flujo de trabajo
feature: Workflows
exl-id: a6003fdb-1035-4b80-8831-73f30a0b4fb2
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 84%

---

# Creación de un flujo de trabajo {#build-a-workflow}

## Cree un nuevo flujo de trabajo {#create-a-new-workflow}

El flujo de trabajo de creación depende del tipo de flujos de trabajo. Puede hacer lo siguiente:

* Crear [Flujos de trabajo de objetivos](#targeting-workflows) desde el **[!UICONTROL Profiles and Targets]** > **[!UICONTROL Jobs]** > **[!UICONTROL Targeting workflows]** del Explorador o desde el **[!UICONTROL Profiles and Targets]** de la página principal, a través de la pestaña **[!UICONTROL Targeting workflows]** subpestaña.

   ![](assets/create-targeting-wf.png)

* Crear [Flujos de trabajo Campaign](#campaign-workflows) desde el **[!UICONTROL Targeting and workflows]** pestaña de una campaña

* Crear [Flujos de trabajo técnicos](#technical-workflows) desde el **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** del explorador. La práctica recomendada es crear una carpeta de flujo de trabajo específica para guardar los flujos de trabajo técnicos.

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

Las plantillas de flujo de trabajo se almacenan en **[!UICONTROL Resources > Templates > Workflow templates]** del explorador.

Además de las propiedades habituales del flujo de trabajo, las propiedades de la plantilla permiten especificar el archivo de ejecución para los flujos de trabajo creados en función de esta plantilla.

![](assets/wf-template-properties.png)

## Duplicación de flujos de trabajo {#duplicate-workflows}

Se pueden duplicar diferentes tipos de flujos de trabajo. Una vez duplicados, las modificaciones del flujo de trabajo no se transfieren a la copia del flujo de trabajo.

>[!CAUTION]
>
>La función de copiar y pegar está disponible en los flujos de trabajo, pero le recomendamos que utilice **Duplicate**. Una vez copiada una actividad, se conserva toda su configuración. Para las actividades de entrega (correo electrónico, SMS, notificaciones push...), el objeto de entrega adjunto a la actividad también se copia, lo que puede provocar un colapso.

1. Haga clic con el botón derecho en un flujo de trabajo.
1. Haga clic en **Duplicate**.

   ![](assets/duplicate-workflows.png)

1. En la ventana de flujo de trabajo, cambie la etiqueta de flujo de trabajo.
1. Haga clic en **Save**.

La función duplicar no está directamente disponible en la vista de una campaña.

Sin embargo, puede crear una vista para mostrar todos los flujos de trabajo de la instancia. En esta vista, puede duplicar flujos de trabajo mediante **Duplicate to**.

**Creación de una vista**

1. En **Explorer**, vaya a la carpeta en la que debe crear la vista.
1. Haga clic con el botón derecho y vaya a **Add a new folder** > **Process** y seleccione **Workflows**.

   ![](assets/add-new-folder-workflows.png)

Se crea la nueva carpeta **Workflows**.

1. Haga clic con el botón derecho y seleccione **Properties**.
1. En el **Restricción** , active la pestaña **Esta carpeta es una vista** y haga clic en **Guardar**.

   ![](assets/folder-is-a-view.png)

La carpeta ahora se rellena con todos los flujos de trabajo de la instancia.

**Duplicación de un flujo de trabajo de campaña**

1. Seleccione un flujo de trabajo de campaña en la vista de flujo de trabajo.
1. Haga clic con el botón derecho en **Duplicate to**.
1. Cambie su etiqueta.
1. Haga clic en **Save**.

Puede ver el flujo de trabajo duplicado en la vista de flujo de trabajo.
