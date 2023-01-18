---
product: campaign
title: Creación de campañas de marketing
description: Obtenga información sobre cómo crear y ejecutar campañas de marketing
feature: Campaigns, Cross Channel Orchestration, Programs
exl-id: 90dd2dad-1380-490e-b958-4a28a7d930ed
source-git-commit: ad286059a9f4b63d7de4fa5130760f36d0976431
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 58%

---

# Creación de programas y campañas{#create-programs-and-campaigns}

Los componentes de organización de campañas se encuentran en el **[!UICONTROL Campaigns]** pestaña: aquí puede ver una descripción general de los programas y campañas de marketing, y sus elementos asociados.

Un programa de marketing consta de campañas, que están formadas por envíos, recursos, etc. Toda la información sobre los envíos, los presupuestos, los revisores y los documentos vinculados se agrupan en la campaña.

![](assets/campaigns-create-from-home.png)

![](assets/do-not-localize/how-to-video.png) [Descubra programas y campañas en vídeo](#video)

## Trabajar con programas y planes{#work-with-plan-and-program}

### Crear la jerarquía de planes y programas {#create-plan-and-program}

Cada campaña pertenece a un programa que pertenece a un plan. Todos los planes, programas y campañas están disponibles a través de la **[!UICONTROL Campaign calendar]** en el **Campañas** pestaña .

Antes de empezar a crear campañas y envíos, configure la jerarquía de carpetas para planes y programas de marketing.

1. Haga clic en el icono **Explorer** en la página principal.
1. Haga clic con el botón derecho en la carpeta en la que desee crear su plan.
1. Seleccione **Add new folder > Campaign Management > Plan**.

   ![](assets/create-new-plan-folder.png)

1. Cambie el nombre del plan.
1. Haga clic con el botón derecho en el plan recién creado y seleccione **Properties...**
1. En la pestaña **General**, modifique el **Internal name** para evitar duplicados durante las exportaciones de paquetes.

   ![](assets/plan-properties.png)

1. Haga clic en **Save**.
1. Haga clic con el botón derecho del ratón en el plan recién creado y seleccione **Create a new “Program” folder**.

   ![](assets/program-folder.png)

1. Repita los pasos anteriores para cambiar el nombre de la nueva carpeta del programa y su nombre interno.


### Configuración de un programa {#edit-a-program}

Al editar un programa, utilice las pestañas que se describen a continuación para explorarlo y configurarlo.

* La pestaña **Programación** muestra el calendario de programas de un mes, una semana o un día según la pestaña en la que haga clic en el encabezado del calendario. Desde esta página puede crear una campaña, un programa o una tarea. [Más información](#campaign-calendar)

* La pestaña **Editar** permite personalizar el programa: nombre, fechas de inicio y finalización, presupuesto, documentos vinculados, etc.

   ![](assets/new-program-edit-tab.png)

## Trabajar con campañas{#work-with-campaigns}

### Creación de una campaña {#create-a-campaign}

Puede crear una campaña a través de la lista de campañas. Para mostrar esta vista, seleccione la opción **[!UICONTROL Campaigns]** en el **[!UICONTROL Campaigns]** tablero y haga clic en **[!UICONTROL Create]**.

El campo **[!UICONTROL Program]** permite seleccionar el programa al que se asocia la campaña. Esta información es obligatoria.

![](assets/new-campaign-settings.png)

Las campañas también se pueden crear mediante desde el calendario de campañas o programas. [Más información](#campaign-calendar)

En la ventana de creación de campaña, seleccione la plantilla de campaña y añada un nombre y una descripción de la campaña. También puede especificar las fechas de inicio y finalización de la campaña.

Haga clic en **[!UICONTROL OK]** para crear la campaña. Se añade a la programación y a la lista de campañas.

Luego puede editar la campaña que acaba de crear y definir sus parámetros. Para abrir y configurar esta campaña, puede:

1. Examine el calendario de campañas, seleccione la campaña que desee visualizar y luego haga clic en el botón **[!UICONTROL Open]** vínculo.
1. Examine la **[!UICONTROL Schedule]** del programa, seleccione la campaña y ábrala.
1. Examine la lista de campañas y haga clic en el nombre de la campaña que desea editar.

Todas estas acciones lo llevan al panel de campañas.

![](assets/campaigns-dashboard-approve.png)

Acceda a las secciones siguientes para aprender a configurar la campaña:

* [Agregar envíos](marketing-campaign-deliveries.md)
* [Administrar recursos y documentos](marketing-campaign-assets.md)
* [Crear la audiencia de destino](marketing-campaign-target.md)
* [Configuración del proceso de aprobación](marketing-campaign-approval.md)
* [Administrar saldos y presupuestos](providers--stocks-and-budgets.md)


### Editar configuración de campaña {#campaign-settings}

Las campañas se crean mediante plantillas de campaña. Puede configurar plantillas reutilizables para las que algunas opciones están seleccionadas y otras configuraciones ya están guardadas.

Para cada campaña, están disponibles las siguientes capacidades:

* Documentos de referencia y recursos: puede asociar documentos con la campaña (resumen, informe, imágenes, etc.). Se admiten todos los formatos de documento. [Más información](marketing-campaign-deliveries.md#manage-associated-documents).
* Defina los costes: para cada campaña, Adobe Campaign permite definir las entradas de coste y las estructuras de cálculo de costes que se pueden utilizar al crear la campaña de marketing. Por ejemplo: costes de impresión, uso de una agencia externa, alquiler de salas, etc. [Más información](providers--stocks-and-budgets.md#defining-cost-categories).
* Definir objetivos: puede definir objetivos cuantificables para una campaña, por ejemplo: número de suscriptores, volumen comercial, etc. Esta información se utiliza más adelante en los informes de campaña.
* Administrar direcciones semilla y grupos de control. [Más información](marketing-campaign-deliveries.md#defining-a-control-group).
* Administrar aprobaciones: puede seleccionar los tratamientos que desea aprobar y, si es necesario, seleccionar los operadores o grupos de operadores revisores. [Más información](marketing-campaign-approval.md#checking-and-approving-deliveries).

>[!NOTE]
>
>Para acceder y actualizar la configuración de la campaña, vaya a la **[!UICONTROL Advanced campaign parameters...]** en el **[!UICONTROL Edit]** pestaña .

### Monitorización de una campaña {#monitor-a-campaign}

Para cada campaña, los trabajos, recursos y envíos están centralizados en un panel. Esta interfaz le permite administrar y orquestar acciones de marketing.

Con Adobe Campaign, puede configurar procesos de colaboración para la creación y aprobación de los distintos pasos de las campañas: aprobación del presupuesto, objetivo, contenido, etc. Esta organización se detalla en [esta sección](marketing-campaign-approval.md).

![](assets/campaigns-dashboard-approval-tab.png)

>[!NOTE]
>
>Los componentes disponibles en una campaña dependen de su plantilla. La configuración de la plantilla de campaña se presenta en [esta sección](marketing-campaign-templates.md#campaign-templates).

Una vez que se alcance la campaña, use la variable **[!UICONTROL Reports]** para acceder a los informes de campaña.

![](assets/campaigns-reports-dashboard.png)

## Calendario de Campaign {#campaign-calendar}

El calendario de campañas muestra todos los programas, planes, campañas y envíos.

Para editar un plan, programa, campaña o entrega, busque su nombre en el calendario y utilice el **[!UICONTROL Open]** vínculo. A continuación se muestra en una nueva pestaña, como se muestra a continuación:

![](assets/campaign-calendar.png)

Puede filtrar la información que se muestra en el calendario de campañas. Para ello, haga clic en el vínculo **[!UICONTROL Filter]** y seleccione los criterios de filtrado.

![](assets/campaign_planning_filter.png)

>[!NOTE]
>
>Cuando filtra una fecha, se muestran todas las campañas con una fecha de inicio posterior a la fecha especificada o con una fecha de finalización anterior a la fecha especificada. Las fechas se seleccionan utilizando los calendarios a la derecha de cada campo.

También puede utilizar el campo **[!UICONTROL Search]** para filtrar los elementos mostrados.

Los iconos vinculados a cada elemento permiten ver su estado: terminado, en curso, en edición, etc.

Para filtrar las campañas que desea mostrar, haga clic en el vínculo **[!UICONTROL Filter]** y seleccione el estado de las campañas que desee mostrar.

![](assets/calendar-filter-options.png)

Al explorar el calendario, también puede crear un programa o una campaña.

![](assets/campaign-create-from-calendar.png)

Cuando crea una campaña a través de la pestaña **[!UICONTROL Schedule]** de un programa, la campaña se relaciona automáticamente con el programa correspondiente. El campo **[!UICONTROL Program]** está oculto en este caso.


## Uso de la interfaz web {#use-the-web-interface-}

Puede acceder a las pantallas de la consola de Adobe Campaign a través de un explorador de internet para ver todas las campañas y envíos, así como informes e información sobre los perfiles de la base de datos. Este acceso no permite la creación de registros. Según los derechos de los operadores, puede ver o actuar en los datos de la base de datos. Por ejemplo: puede aprobar el contenido de las campañas y su segmentación, reiniciar o detener una entrega, etc.

1. Inicie sesión a través de https://`<your instance>:<port>/view/home`.
1. Utilice los menús para acceder a las descripciones generales.

   ![](assets/web-access-campaigns.png)

Además de desplazarse por las campañas y verlas, puede realizar estos tipos de tareas:

* Monitorización de la actividad en una instancia
* Participar en los procesos de validación, por ejemplo, aprobar o rechazar un contenido de entrega
* Realizar otras acciones rápidas como, por ejemplo, pausar un flujo de trabajo
* Acceder a todas las funciones de creación de informes
* Participar en debates en foros

Esta tabla resume las acciones que se pueden realizar en las campañas desde un explorador:

| Página  | Acción |
| --- | --- |
| Lista de campañas, envíos, ofertas, etc. | Eliminar un elemento de lista |
| Campaña | Cancelar una campaña |
| Entrega | Aprobar el contenido de entrega y el destino<br/>Enviar el contenido de la entrega<br/>Confirmar una entrega<br/>Pausar y detener un envío |
| Aplicación web | Crear una aplicación web<br/>Editar el contenido y las propiedades de la aplicación<br/>Guardar el contenido de la aplicación como una plantilla<br/>Publicar la aplicación |
| Oferta | Aprobar el contenido de la oferta y los requisitos<br/>Desactivación de una oferta en línea |
| Tarea | Finalizar una tarea<br/>Cancelar una tarea |
| Recursos de marketing | Aprobar un recurso<br/>Bloqueo y desbloqueo de un recurso |
| Paquete de campañas | Enviar un paquete para su aprobación<br/>Aprobar o rechazar un paquete<br/>Cancelar un paquete |
| Pedido de la campaña | Crear un pedido<br/>Aceptar o rechazar un pedido |
| Stock | Eliminar una línea de stock |
| Simulación de oferta | Inicio y parada de una simulación |
| Flujo de trabajo de direccionamiento | Iniciar, pausar y detener un flujo de trabajo |
| Informe | Guardar los datos actuales en el historial de informes |
| Foro | Agregar una conversación<br/>Responder a un mensaje en una conversación<br/>Siga la conversación y cancele la suscripción |

### Administración de aprobaciones

Las aprobaciones de un destino o de un contenido de entrega se pueden realizar mediante el acceso a la web.

![](assets/web-access-approval.png)

También puede utilizar el vínculo incluido en los mensajes de notificación. Para obtener más información, consulte [esta sección](marketing-campaign-approval.md#checking-and-approving-deliveries).


## Tutorial en vídeo {#video}

Este vídeo muestra cómo crear planes, programas y campañas de marketing.

>[!VIDEO](https://video.tv.adobe.com/v/333810?quality=12)
