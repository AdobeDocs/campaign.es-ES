---
product: campaign
title: Plantillas de hipótesis
description: Aprenda a crear hipótesis en el Gestor de respuestas de Campaign
feature: Campaigns, Templates
version: Campaign v8, Campaign Classic v7
audience: campaign
content-type: reference
topic-tags: response-manager
exl-id: 428c7677-454b-4618-bae7-0be7df6dfcaa
TQID: 'https://experienceleague.adobe.com/FKf9pDlOZI1NEhwmdSpcpvEbNsT28wEvgy81TBEQQgo'
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
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: d72afaa0-c842-48c8-9a3c-51b7911edc1b
    internal-label: Response Management
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 76%
---
# Plantillas de hipótesis{#hypothesis-templates}



## Creación de un modelo de hipótesis {#creating-a-hypothesis-model}

La configuración de la plantilla de hipótesis permite definir el contexto para medir las reacciones, ya sea para una entrega o para una oferta. Aquí es donde se hace referencia a las distintas tablas de medición, incluidas las usadas para definir relaciones entre individuos, hipótesis y la tabla de transacciones.

Para crear una plantilla de hipótesis, aplique los siguientes pasos:

1. En Adobe Campaign Explorer, haga clic en **[!UICONTROL Resources>Templates>Hypothesis templates]**.

   ![Explorador con recursos > Plantillas > Plantillas de hipótesis seleccionadas y una plantilla de hipótesis abierta en la ficha General.](assets/response_hypothesis_model_creation_001.png)

1. Haga clic en **[!UICONTROL New]** o haga clic con el botón secundario en la lista de plantillas y elija **[!UICONTROL New]** en la lista desplegable.
1. Introduzca la etiqueta de hipótesis.
1. Especifique si la plantilla está destinada a hipótesis en ofertas o envíos a través de **[!UICONTROL Hypothesis type]**.
1. Para las plantillas de tipo **[!UICONTROL Delivery]**, especifique si se deben realizar mediciones con o sin un grupo de control. [Más información](#properties-of-a-hypothesis-template)
1. Para las plantillas de tipo **[!UICONTROL Delivery]**, puede elegir un canal específico o decidir aplicar la plantilla a todos los canales disponibles en Adobe Campaign mediante la lista desplegable **[!UICONTROL Channel]**. [Más información](#properties-of-a-hypothesis-template)
1. Seleccione el **[!UICONTROL Execution folder]** en el que desea crear y ejecutar automáticamente la hipótesis que se creará a partir de esta plantilla.
1. Elija la configuración de ejecución. [Más información](#hypothesis-template-execution-settings)
1. Especifique el periodo de cálculo de hipótesis. [Más información](#hypothesis-template-execution-settings)

   >[!CAUTION]
   >
   >Este periodo se determina a partir de la fecha de contacto.

1. En la pestaña **[!UICONTROL Transactions]**, especifique las tablas y los campos necesarios para el cálculo de hipótesis. [Más información](#transactions)
1. Si la plantilla está configurada para hipótesis de **[!UICONTROL Offer]**, puede habilitar la opción **[!UICONTROL Update offer proposition status]**: en este caso, seleccione el estado de la propuesta de oferta que desea cambiar.
1. Especifique el ámbito de la aplicación de hipótesis. [Más información](#hypothesis-perimeter)
1. Si es necesario, utilice una secuencia de comandos para completar el filtrado. [Más información](#hypothesis-perimeter)

### Propiedades de una plantilla de hipótesis {#properties-of-a-hypothesis-template}

La pestaña plantilla **[!UICONTROL General]** le permite especificar las opciones generales de plantilla. Los campos disponibles son:

* **[!UICONTROL Hypothesis type]**: le permite determinar si la plantilla debe estar destinada a hipótesis sobre envíos u ofertas.

  También puede optar por crear una hipótesis que se aplicará a los envíos y a las ofertas.

  >[!NOTE]
  >
  >Si la plantilla se aplica a las ofertas, la opción **[!UICONTROL Update offer proposition status]** está disponible en la pestaña **[!UICONTROL Transactions]**.

* **[!UICONTROL Measurement with control group]**: permite establecer el estado de un grupo de control para la entrega o la campaña e incluirla en indicadores de medición. El grupo de control, que no recibe envíos, le permite medir el impacto de la campaña después de la entrega, comparándolo con la población objetivo que recibió la entrega.

  >[!NOTE]
  >
  >Si la plantilla está configurada para tener un grupo de control en cuenta pero no se define ningún grupo en la entrega, los resultados se basarán únicamente en los destinatarios seleccionados.

  Para obtener más información sobre la definición y configuración de un grupo de control, consulte la [documentación de la versión 8 de Campaign](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=es#add-a-control-group){target=_blank}.

* **[!UICONTROL Channel]**: puede elegir un canal específico o hacer que la plantilla de hipótesis esté disponible para todos los canales de la consola de Adobe Campaign seleccionando **[!UICONTROL All channels]** en la lista desplegable. Si configura la plantilla para un canal específico, le permite filtrar automáticamente los envíos por canal al crear la hipótesis. [Más información](creating-hypotheses.md)

  ![Pestaña General de plantilla de hipótesis con la lista desplegable Canal abierta y Todos los canales resaltados.](assets/response_properties_001.png)

* **[!UICONTROL Execution folder]**: permite especificar la carpeta de ejecución de la hipótesis.
* **[!UICONTROL Taken into account in campaign ROI calculation]**: utiliza el resultado de la hipótesis en el cálculo de ROI de la campaña relacionada.

### Configuración de ejecución de plantillas de hipótesis {#hypothesis-template-execution-settings}

La pestaña **[!UICONTROL General]** de la plantilla también permite especificar los parámetros de la ejecución de hipótesis. Las opciones disponibles son las siguientes:

* **[!UICONTROL Schedule execution for a time of low activity]**: permite programar el inicio de la hipótesis para optimizar el rendimiento de Adobe Campaign. Cuando se activa esta opción, el flujo de trabajo de procesamiento de las campañas ejecuta el cálculo de hipótesis durante el tiempo de espera.

  ![Configuración de ejecución de plantilla de hipótesis con la ejecución de programación durante un período de baja actividad comprobada.](assets/response_exec_settings_002.png)

* **[!UICONTROL Priority]**: nivel aplicado a la hipótesis para agotar las solicitudes de cálculo de hipótesis si hay ejecuciones simultáneas.

  ![Lista desplegable de prioridad de plantilla de hipótesis baja, media y alta.](assets/response_exec_settings_003.png)

* **[!UICONTROL Automatic execution]**: si es necesario, permite programar el cálculo de hipótesis (por ejemplo, si desea actualizar los indicadores regularmente hasta el final de la entrega).

  ![Ejecución automática comprobada con el vínculo Frequency of execution y su cuadro de diálogo Hypothesis con el botón Change.](assets/response_exec_settings_001.png)

  Para especificar una programación, aplique el siguiente proceso:

  1. Haga clic en el vínculo **[!UICONTROL Frequency of execution...]** y luego en el botón **[!UICONTROL Change...]**.

     ![El cuadro de diálogo de hipótesis que indica que la programación de tareas no está definida, con el botón Cambiar para definir la frecuencia.](assets/response_frequency_execution_001.png)

  1. Configure la frecuencia, los eventos relacionados y el periodo de validez.

     ![Asistente para la edición de programación: frecuencia semanal, miércoles y viernes seleccionados y válido desde el período de validez.](assets/response_frequency_execution_002.png)

  1. Haga clic en **[!UICONTROL Finish]** para guardar la programación.

     ![Paso de resumen del asistente de edición de programación que enumera las horas de inicio, con el botón Finalizar.](assets/response_frequency_execution_003.png)

* **[!UICONTROL Log SQL queries in journal]**: esta función está reservada para usuarios expertos. Le permite añadir una pestaña a la auditoría de hipótesis de medición para mostrar consultas SQL. Esto permite detectar posibles errores que se pueden dar en una simulación.
* **[!UICONTROL Keep execution workflow]**: permite mantener el flujo de trabajo generado automáticamente al principio del cálculo de hipótesis. En las hipótesis creadas a partir de una plantilla que tiene esta opción activada, el flujo de trabajo generado permite hacer un seguimiento del proceso.

  >[!CAUTION]
  >
  >Esta opción debe activarse solo para fines de depuración, en caso de error al ejecutar la hipótesis.\
  >Además, los flujos de trabajo generados automáticamente no se deben modificar. No se tendrá en cuenta ninguna modificación para realizar cálculos más adelante.\
  >Si ha comprobado esta opción, elimine el flujo de trabajo una vez que se haya ejecutado.

### Transacciones {#transactions}

Esta pestaña contiene los distintos campos y tablas que permiten guardar el historial de reacciones del destinatario en términos de transacciones. Consulte esta [sección](https://experienceleague.adobe.com/en/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/about-schema-reference){target="_blank"} para obtener más información sobre las tablas dedicadas a la gestión de respuestas.

* **[!UICONTROL Schema (reaction log storage)]**: seleccione la tabla de limpieza del destinatario. La tabla predeterminada de Adobe Campaign es **NmsRemaMatchRcp**.
* **[!UICONTROL Transaction schema]**: elija la tabla a la que se referirán las hipótesis, es decir, la transacción o la tabla de compras.
* **[!UICONTROL Querying schema]**: elija los criterios de filtro para la hipótesis.
* **[!UICONTROL Link to individuals]**: elija el vínculo entre las personas y la tabla utilizada como esquema de transacción.
* **[!UICONTROL Link to the household]**: seleccione el vínculo al hogar en el esquema de transacciones si desea incluir a todos los miembros de un hogar en una hipótesis. Este campo es opcional.
* **[!UICONTROL Transaction date]**: este campo es opcional pero recomendado, ya que permite definir un periodo para el cálculo de hipótesis.
* **[!UICONTROL Measurement period]**: le permite configurar las fechas de inicio y finalización durante las cuales se ejecutan las hipótesis y se recuperan las líneas de compra.

  Cuando la hipótesis está vinculada a una entrega, la medición se activa automáticamente unos días después de la fecha de contacto para los envíos de correo directo, o después de la fecha de entrega para envíos de correo electrónico o SMS.

  ![Pestaña Transacciones con el campo de fecha de transacción y los períodos Inicio del cálculo y Fin del cálculo.](assets/response_measurement_001.png)

  Si la hipótesis se inicia sobre la marcha, se puede forzar si quisiera activarla inmediatamente. De lo contrario, se activa automáticamente según el final de la fecha de cálculo configurada, que se basa en la fecha de creación de la hipótesis. [Más información](creating-hypotheses.md#creating-a-hypothesis-on-the-fly-on-a-delivery)).

* **[!UICONTROL Transaction/Margin amount]**: estos campos son opcionales y permiten calcular los indicadores de facturación automáticamente. [Más información](hypothesis-tracking.md#indicators)
* **[!UICONTROL Unit amount]**: permite configurar una cantidad para calcular ingresos. [Más información](hypothesis-tracking.md#indicators)

  ![Ficha Transacciones con el importe de transacción establecido en @amount y una flecha que señala al campo Importe unitario.](assets/response_transactions_001.png)

* **[!UICONTROL Additional measures and data]**: permite especificar medidas o ejes de informes adicionales de los campos en las distintas tablas.
* **[!UICONTROL Update offer proposition status]**: permite cambiar el estado de la propuesta de oferta si la hipótesis identifica un destinatario de la oferta.

  ![Ficha de transacciones Sección de propuestas con la opción Actualizar estado de propuesta de oferta activada y la lista desplegable Estado abierta.](assets/response_offer_status_001.png)

### Perímetro de hipótesis {#hypothesis-perimeter}

Una vez que haya definido la tabla de transacciones y los campos a los que se referirá la hipótesis, puede refinar el alcance de sus hipótesis especificando las transacciones y envíos específicos utilizando filtros. También puede utilizar una secuencia de comandos de JavaScript para indicar explícitamente el producto al que se hace referencia en la tabla de transacciones.

* **Filtrar transacciones**: en la pestaña **[!UICONTROL Scope]**, puede configurar un filtro en la hipótesis. Para ello:

  1. Haga clic en el vínculo **[!UICONTROL Edit query]**.

     ![Ficha Scope con el vínculo Edit query en Filtering of transactions linked to reactions.](assets/response_scope_filtering_001.png)

  1. Especifique las condiciones del filtro.

     ![Asistente para editar consultas: se seleccionaron las condiciones de filtrado y, a continuación, el botón Editar expresión y el árbol de selección de campos.](assets/response_scope_filtering_002.png)

  1. Seleccione la transacción a la que quiere vincular la hipótesis.

     ![Editar condiciones de filtro de consulta: existen líneas de compra como, con la compra igual a la lista de valores abierta.](assets/response_scope_filtering_003.png)

* **Filter on recipients**: en la pestaña **[!UICONTROL Scope]**, puede limitar la hipótesis a cualquier información vinculada a un mensaje (entrega, destinatario, dirección de correo electrónico, servicio, etc.):

  1. Haga clic en el vínculo **[!UICONTROL Add a filter]** luego en **[!UICONTROL Edit query]**.

     ![Ficha Scope con el vínculo Add a filter y el vínculo Edit query en Filtering of the delivery messages.](assets/response_scope_filtering_004.png)

  1. Especifique las condiciones del filtro.

     ![El asistente de edición de consultas del esquema de registro de envíos de destinatarios con un mensaje de correo electrónico contiene una condición de filtro.](assets/response_scope_filtering_005.png)

  1. Haga clic en **[!UICONTROL Finish]** para guardar la consulta.

     ![Pestaña Ámbito que muestra el filtro de mensaje de envío guardado, Consulta: el correo electrónico contiene, resaltado.](assets/response_scope_filtering_006.png)

* **Script**: puede utilizar una secuencia de comandos de JavaScript para sobrecargar dinámicamente la configuración de hipótesis durante su ejecución.

  Para ello, haga clic en el vínculo **[!UICONTROL Advanced settings]** e introduzca la secuencia de comandos deseada.

  >[!NOTE]
  >
  >Esta opción es para usuarios expertos.

  ![Cuadro de diálogo Configuración avanzada con un script de inicialización introducido, abierto desde el vínculo Configuración avanzada en la ficha Ámbito.](assets/response_hypothesis_model_creation_011.png)

## Ejemplo: Creación de una plantilla de hipótesis para una entrega {#example--creating-a-hypothesis-template-on-a-delivery}

En este ejemplo, vamos a crear una plantilla de hipótesis para una entrega de correo directo. La tabla de transacciones (**Purchases** en nuestro ejemplo) en la que se basarán las hipótesis contiene líneas de compra vinculadas a artículos o productos. Queremos configurar nuestro modelo para crear hipótesis sobre artículos o productos en la tabla de compras.

1. En Adobe Campaign Explorer, vaya al directorio **[!UICONTROL Resources > Templates > Hypothesis templates]**.
1. Haga clic en **[!UICONTROL New]** para crear una plantilla.

   ![Lista de plantillas de hipótesis con el botón Nuevo resaltado y una plantilla nueva abierta en la ficha General.](assets/response_hypothesis_model_example_001.png)

1. Cambie la etiqueta de la plantilla.

   ![Pestaña Plantilla general con la etiqueta cambiada a Hipótesis en compras y Envíos como tipo de hipótesis.](assets/response_hypothesis_model_example_002.png)

1. Seleccione **[!UICONTROL Deliveries]** como tipo de hipótesis.
1. Especifique que la entrega puede contener un grupo de control comprobando el cuadro correspondiente.
1. Seleccione el canal **[!UICONTROL Direct mail]** (Correo postal).

   >[!NOTE]
   >
   >Debido a que la plantilla es específica para los envíos de correo directo, las hipótesis creadas utilizando este modelo pueden no estar vinculadas a ningún otro tipo de entrega.

1. En la pestaña **[!UICONTROL Transactions]**, seleccione la tabla de reacciones de destinatarios.

   ![Ficha Transactions con el cuadro de diálogo Seleccionar un esquema y las reacciones del esquema de destinatarios seleccionado.](assets/response_hypothesis_model_example_006.png)

1. En el campo **[!UICONTROL Transactions schema]**, seleccione la tabla de compra.

   ![Ficha Transacciones con el cuadro de diálogo Seleccionar un documento filtrado en compras y Compras seleccionadas.](assets/response_hypothesis_model_example_007.png)

1. Seleccione las líneas de compra en el campo **[!UICONTROL Querying schema]**.

   ![Consulta de la lista desplegable de esquema que enumera las líneas de compra, las compras y las reacciones de los destinatarios.](assets/response_hypothesis_model_example_008.png)

1. Seleccione los destinatarios vinculados a la tabla de compra.

   ![Seleccione un cuadro de diálogo de expresión para vincular a personas con el vínculo de destinatario seleccionado en Compra.](assets/response_hypothesis_model_example_009.png)

1. Seleccione el campo vinculado a la fecha de compra.

   Esto permite definir un intervalo de tiempo para hipótesis. Este paso no es obligatorio; sin embargo, es recomendable.

   ![Seleccione un cuadro de diálogo de expresión para la fecha de transacción con el campo Fecha de compra seleccionado.](assets/response_hypothesis_model_example_010.png)

1. Configure el periodo de cálculo de 5 a 25 días.

   ![Se ha resaltado la pestaña Transacciones con el valor 5d en Inicio de cálculo y el valor 25d en Fin de cálculo.](assets/response_hypothesis_model_example_005.png)

1. En la pestaña **[!UICONTROL Scope]**, haga clic en **[!UICONTROL Edit query]** para crear un filtro de hipótesis.

   ![Pestaña Ámbito con Editar consulta en la que se hizo clic y el asistente Editar consulta que enumera los tipos de filtro, Filtrar por producto seleccionado.](assets/response_hypothesis_model_example_011.png)

   La plantilla creada le permite ejecutar hipótesis sobre los productos o artículos de la tabla de compra.

1. Haga clic en **[!UICONTROL Save]** para guardar la plantilla.
