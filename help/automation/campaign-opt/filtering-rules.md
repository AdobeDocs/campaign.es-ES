---
product: campaign
title: Configuración de reglas de filtrado
description: Obtenga información sobre cómo configurar las reglas de filtrado
feature: Typology Rules
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 98%

---

# Reglas de filtrado{#filtering-rules}

Las reglas de filtrado permiten definir los mensajes que deben excluirse según los criterios definidos en una consulta. Estas reglas están vinculadas a una dimensión objetivo.

Las reglas de filtrado se pueden vincular a otros tipos de reglas (control, presión, etc.) en tipologías o agrupadas en una tipología dedicada de **filtrado.** [Más información](#create-and-use-a-filtering-typology).

## Creación de una regla de filtrado {#create-a-filtering-rule}

Por ejemplo, puede filtrar los suscriptores del boletín informativo para evitar que las comunicaciones se envíen a destinatarios menores de edad.

Para definir este filtro, aplique los siguientes pasos:

1. Cree una regla de tipología de **[!UICONTROL Filtering]** aplicable a todos los canales de comunicación.

   ![](assets/campaign_opt_create_filter_01.png)

1. Cambie la dimensión de segmentación predeterminada y seleccione las suscripciones (**nms:subscription**).

   ![](assets/campaign_opt_create_filter_02.png)

1. Cree el filtro mediante el enlace **[!UICONTROL Edit the query from the targeting dimension...]**.

   ![](assets/campaign_opt_create_filter_03.png)

1. Vincule esta regla a una tipología de campaña y guárdela.

   ![](assets/campaign_opt_create_filter_04.png)

Cuando se utiliza esta regla en una entrega, se excluye automáticamente a los suscriptores menores de edad. Un mensaje específico indica la aplicación de la regla:

![](assets/campaign_opt_create_filter_05.png)

## Condicionamiento de una regla de filtrado {#condition-a-filtering-rule}

Puede restringir el campo de aplicación de la regla de filtrado en función de la entrega relacionado o la descripción de la entrega.

Para ello, vaya a la pestaña **[!UICONTROL General]** en la regla de tipología, seleccione el tipo de restricción que desea aplicar y cree el filtro, como se muestra a continuación:

![](assets/campaign_opt_create_filter_06.png)

En este caso, incluso si la regla está vinculada a todas las entregas, solo se aplica a los que coincidan con los del filtro definido.

>[!NOTE]
>
>Las reglas de tipologías y filtrado se pueden utilizar en un flujo de trabajo en la actividad **[!UICONTROL Delivery outline]**. [Más información](../workflow/delivery-outline.md).

## Creación y uso de una tipología de filtrado {#create-and-use-a-filtering-typology}

Puede crear tipologías de **[!UICONTROL Filtering]**: solo contienen reglas de filtrado.

![](assets/campaign_opt_create_typo_filtering.png)

Estas tipologías específicas se pueden vincular a una entrega cuando se selecciona el destino: en el asistente de envíos, haga clic en el vínculo **[!UICONTROL To]** y, a continuación, haga clic en la pestaña **[!UICONTROL Exclusions]**.

![](assets/campaign_opt_apply_typo_filtering.png)

A continuación, seleccione el filtro que se aplica a la entrega. Para ello, haga clic en el botón **[!UICONTROL Add]** y seleccione las tipologías que desea aplicar.

También puede vincular reglas de filtrado directamente mediante esta pestaña, sin que se agrupen en una tipología. Para ello, utilice la sección inferior de la ventana.

![](assets/campaign_opt_select_typo_filtering.png)

>[!NOTE]
>
>En la ventana de selección solo están disponibles las reglas de filtrado y de tipologías.
>
>Estas configuraciones se pueden definir en la plantilla de envío para que se apliquen automáticamente a todas las entregas nuevas creadas con la plantilla.

## Reglas de exclusión de envío predeterminadas {#default-deliverability-exclusion-rules}

Hay dos reglas de filtrado disponibles de forma predeterminada: **[!UICONTROL Exclude addresses]** ( **[!UICONTROL addressExclusions]** ) y **[!UICONTROL Exclude domains]** ( **[!UICONTROL domainExclusions]** ). Durante el análisis del correo electrónico, estas reglas comparan las direcciones de correo de los destinatarios con las direcciones o nombres de dominio prohibidos incluidos en una lista de supresión global encriptada que se administra en la instancia de envío. Si se encuentra una coincidencia, el mensaje no se envía a ese destinatario.

El objetivo de esto es evitar que se incluya el servicio en una lista de bloqueados de actividad maliciosa, especialmente a través de Spamtrap. Por ejemplo, si se utiliza un Spamtrap para suscribirse a través de uno de sus formularios web, se envía un mensaje de correo electrónico de confirmación automáticamente a ese Spamtrap y esto hace que incluya su dirección lista de bloqueados automáticamente.

>[!NOTE]
>
>Las direcciones y los nombres de dominio contenidos en la lista de supresión global están ocultos. En los registros de análisis de envío solo se indica el número de destinatarios excluidos.
