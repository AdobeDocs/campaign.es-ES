---
product: campaign
title: Reglas de coherencia
description: Reglas de coherencia
feature: Typology Rules
version: Campaign v8, Campaign Classic v7
exl-id: dcb4ffcf-71e5-48a2-b0f7-42915a599652
TQID: 'https://experienceleague.adobe.com/KaybpQFNgtTiMgQOWX0-bNqPEMeWGWR8vb6qjZzr63k'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: e5fb657f-3c0a-4fcc-9980-3589a23ab4de
    internal-label: Typology rules
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 64%
---
# Reglas de coherencia{#consistency-rules}

Adobe Campaign garantiza comunicaciones coherentes gracias a un conjunto de reglas contenidas en tipologías de campaña. Su objetivo es controlar las entregas que se realizan a los destinatarios como, por ejemplo, volumen, tipo, relevancia, etc.

Las reglas de **capacidad**, por ejemplo, pueden evitar la sobrecarga en la plataforma correspondiente de envío de mensajes. Por ejemplo, las ofertas especiales que contienen un vínculo de descarga no se deben enviar a demasiadas personas a la vez para evitar la saturación del servidor; las campañas telefónicas no deben superar la capacidad de procesamiento de los centros de llamadas, etc.

## Control de la capacidad {#control-capacity}

Antes de enviar mensajes, debe asegurarse de que su organización tiene la capacidad (infraestructura física) para procesar la entrega, las respuestas que puede generar la entrega (mensajes entrantes) y el número de llamadas que se realizan para ponerse en contacto con los suscriptores (capacidad de procesamiento del centro de llamadas), por ejemplo.

Para ello, cree **[!UICONTROL Capacity]** reglas de tipología.

En el siguiente ejemplo, creamos una regla de tipología para una campaña de lealtad por teléfono. Restringimos el número de mensajes a 20 por día, es decir, la capacidad de procesamiento diaria de un centro de llamadas. Una vez aplicada la regla a dos envíos, podemos monitorizar el consumo mediante registros.

Para diseñar una regla de capacidad nueva, siga los pasos a continuación:

1. En la carpeta **[!UICONTROL Administration > Campaign management > Typology management > Typology rules]**, haga clic en **[!UICONTROL New]**.
1. Seleccione un tipo de regla de **[!UICONTROL Capacity]**.

   ![Pantalla de creación de reglas de tipología con la opción Capacity seleccionada en la lista desplegable de tipo de regla.](assets/campaign_opt_create_capacity_01.png)

1. En la pestaña **[!UICONTROL Capacity]**, cree las líneas de disponibilidad: en este ejemplo, son periodos durante los cuales se pueden realizar llamadas. Seleccione un periodo de 24 horas e introduzca 150 en la cantidad inicial, lo que significa que el centro de llamadas puede gestionar 150 llamadas al día.

   ![Pestaña Capacidad con el cuadro de diálogo Editar línea de disponibilidad para especificar la cantidad inicial, final e inicial.](assets/campaign_opt_create_capacity_02.png)

   >[!NOTE]
   >
   >Las líneas de disponibilidad solo tienen fines informativos. Si necesita excluir mensajes cuando se alcance el límite de capacidad, consulte [Excluir mensajes cuando se alcance el límite de capacidad](#exclude-messages-when-capacity-limit-reached).

1. Asocie esta regla a una tipología y luego haga referencia a la misma en su envío para aplicar esta regla de capacidad. Para obtener más información, consulte [Aplicar una tipología a una entrega](apply-rules.md#apply-a-typology-to-a-delivery).
1. Puede monitorizar el consumo desde las pestañas **[!UICONTROL Consumptions]** y **[!UICONTROL Capacity]** de la regla.

   Cuando se utiliza una regla en una entrega, las columnas **[!UICONTROL Consumed]** y **[!UICONTROL Remaining]** facilitan información sobre la carga, como se muestra a continuación:

   ![Pestaña Capacidad que muestra una línea de disponibilidad con 150 cantidades iniciales, 200 consumidas y -50 restantes.](assets/campaign_opt_create_capacity_03.png)

   Para obtener más información, consulte [esta sección](#monitor-consumption).

## Definición de la carga máxima {#define-the-maximum-load}

Para definir la carga máxima, debe definir las líneas de disponibilidad. Para ello, hay dos opciones disponibles: puede [crear manualmente una o más líneas de disponibilidad](#add-availability-lines-one-by-one) o crear intervalos de disponibilidad. La frecuencia de estos periodos se puede automatizar. [Más información](#add-a-set-of-availability-lines).

### Adición de líneas de disponibilidad una por una {#add-availability-lines-one-by-one}

Para crear una línea de disponibilidad, haga clic en el botón **[!UICONTROL Add]** y seleccione **[!UICONTROL Add an availability line]**. Introduzca el periodo de disponibilidad y la carga disponible.

![Se abrió el cuadro de diálogo Editar línea de disponibilidad desde el botón Agregar, con los campos de cantidad inicial, final e inicial.](assets/campaign_opt_create_capacity_02.png)

Añada tantas líneas como requiera su capacidad de procesamiento.

### Adición de un conjunto de líneas de disponibilidad {#add-a-set-of-availability-lines}

Para definir los periodos de disponibilidad de un tiempo determinado, haga clic en el botón **[!UICONTROL Add]** y seleccione la opción **[!UICONTROL Add a set of availability lines]**. Indique una duración para cada periodo y el número de periodos que desea crear.

Para automatizar la frecuencia de creación de páginas, haga clic en el botón **[!UICONTROL Change]** y defina la programación del periodo.

![Cuadro de diálogo Editar línea de disponibilidad con Agregar un conjunto de líneas de disponibilidad seleccionadas y el botón Cambiar para la programación.](assets/campaign_opt_create_capacity_07.png)

Por ejemplo, defina una programación para crear periodos de disponibilidad para todos los días laborables a una velocidad de 10 llamadas por hora entre 9 a. m. y 5 p. m. Para ello, siga los siguientes pasos:

1. Seleccione el tipo de periodicidad y los días y horas de validez:

   ![Asistente de edición de programación Página de período de validez con fechas Válidas desde y Hasta seleccionadas de un calendario.](assets/campaign_opt_create_capacity_08.png)

1. Indique las fechas de validez:

   ![Asistente de edición de programación. Página de período de validez con la fecha de finalización de validez seleccionada de un calendario.](assets/campaign_opt_create_capacity_09.png)

1. Compruebe la programación antes de aprobarla:

   ![Página de resumen del asistente de edición de programación con la descripción de la programación y la lista de horas de inicio antes de finalizar.](assets/campaign_opt_create_capacity_10.png)

El flujo de trabajo de **[!UICONTROL Forecasting]** crea automáticamente todas las líneas coincidentes.

![Pestaña Capacidad de la regla del centro de llamadas que enumera las líneas de disponibilidad creadas automáticamente por la programación.](assets/campaign_opt_create_capacity_12.png)

>[!NOTE]
>
>Recomendamos la creación de líneas de disponibilidad a través de las importaciones de archivos. Esta pestaña le permite consultar y comprobar las líneas de consumo.

## Exclusión de mensajes al alcanzar el límite de capacidad {#exclude-messages-when-capacity-limit-reached}

Las líneas de disponibilidad solo tienen fines informativos. Para excluir mensajes excesivos, marque la opción **[!UICONTROL Exclude from the target messages in excess of capacity]**. Esto evita que se supere la capacidad. Para la misma población que en el ejemplo anterior, es posible que el consumo y la capacidad restante no superen la cantidad inicial:

![Pestaña Capacidad con Excluir de los mensajes de destino que superen la capacidad seleccionada: 100 consumidos, 50 restantes.](assets/campaign_opt_create_capacity_04.png)

El número de mensajes máximo que se va a procesar se reparte de forma equitativa durante el intervalo de disponibilidad definido. Esto es especialmente relevante para los centros de llamadas, ya que el número máximo de llamadas al día es limitado. En el caso de las entregas por correo electrónico, la opción **[!UICONTROL Do not limit instantaneous delivery capacity]** permite ignorar este intervalo de disponibilidad y enviar los correos al mismo tiempo.

![Pestaña Capacidad con la opción No limitar la capacidad de envío instantánea seleccionada, que muestra 150 consumidos y 0 restantes.](assets/campaign_opt_create_capacity_05.png)

>[!NOTE]
>
>En caso de sobrecarga, los mensajes guardados se seleccionan según la fórmula definida en las propiedades de entrega.

![Pestaña Propiedades de entrega: ficha Tipología con configuración de capacidad: fórmula de importancia y capacidad del canal del centro de llamadas.](assets/campaign_opt_create_capacity_06.png)

## Monitorización del consumo {#monitoring-consumption}

De forma predeterminada, las reglas de capacidad solo tienen fines ilustrativos. Seleccione la opción **[!UICONTROL Exclude messages in excess of capacity from the target]** para evitar que se supere la carga definida. En este caso, los mensajes sobrantes se excluyen automáticamente de las entregas utilizando esta regla de tipología.

Para monitorizar los consumos, consulte los valores mostrados en la columna **[!UICONTROL Consumed]** de la pestaña **[!UICONTROL Capacity]** en la regla de tipología.

![Pestaña Capacidad con la opción de exclusión seleccionada, que muestra 100 consumidos y 50 restantes de 150 cantidades iniciales.](assets/campaign_opt_create_capacity_04.png)

Para consultar las líneas de consumo, haga clic en la pestaña **[!UICONTROL Consumptions]** de la regla.
