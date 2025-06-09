---
product: campaign
title: Configuración de reglas de filtrado
description: Obtenga información sobre cómo configurar las reglas de filtrado
feature: Typology Rules
exl-id: 17507cdf-211f-4fa2-abb9-33d4f6dc47bb
source-git-commit: 1fb93efac4fee4965213f8b42f518f2c10638e20
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 77%

---

# Reglas de filtrado{#filtering-rules}

Utilice reglas de filtrado para seleccionar los mensajes que desea excluir según los criterios definidos en una consulta. Estas reglas están vinculadas a una dimensión objetivo.

Las reglas de filtrado se pueden vincular a otros tipos de reglas (control, presión, etc.) en tipologías o agrupadas en una tipología dedicada de **filtrado.** [Más información](#create-and-use-a-filtering-typology).

## Creación de una regla de filtrado {#create-a-filtering-rule}

Por ejemplo, puede filtrar los suscriptores del boletín informativo para evitar que las comunicaciones se envíen a destinatarios menores de edad.

Para definir este filtro, aplique los siguientes pasos:

1. Vaya a la carpeta **[!UICONTROL Administration > Campaign management > Typology management > Typology rules]** del explorador de Campaign y haga clic en el icono **Nuevo** para crear una regla de tipología.
1. Cree una regla de tipología de **[!UICONTROL Filtering]** aplicable a todos los canales.

   ![](assets/campaign_opt_create_filter_01.png)

1. En la ficha **Filter**, cambie la dimensión de segmentación predeterminada a **Subscriptions** (**nms:subscription**).

   ![](assets/campaign_opt_create_filter_02.png)

1. Cree el filtro mediante el enlace **[!UICONTROL Edit the query from the targeting dimension...]**.

   ![](assets/campaign_opt_create_filter_03.png)

1. Filtre por la edad del destinatario y guarde la condición de filtrado.

   ![](assets/campaign_opt_create_filter_03b.png)

1. En la ficha **Tipologías**, vincule esta regla a una tipología de campaña y guárdela.

   ![](assets/campaign_opt_create_filter_04.png)

Cuando se utiliza esta regla en una entrega, se excluye automáticamente a los suscriptores menores de edad. Un mensaje específico indica cuándo se aplica la regla:

![](assets/campaign_opt_create_filter_05.png)

## Condicionamiento de una regla de filtrado {#condition-a-filtering-rule}

Puede restringir el campo de aplicación de la regla de filtrado en función de la entrega relacionado o la descripción de la entrega.

Para ello, vaya a la pestaña **[!UICONTROL General]** de la regla de tipología, seleccione el tipo de restricción que desea aplicar y cree el filtro.
<!--
![](assets/campaign_opt_create_filter_06.png)
-->


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
>

## Reglas de exclusión de envío predeterminadas {#default-deliverability-exclusion-rules}

Hay dos reglas de filtrado disponibles de forma predeterminada: **[!UICONTROL Exclude addresses]** ( **[!UICONTROL addressExclusions]** ) y **[!UICONTROL Exclude domains]** ( **[!UICONTROL domainExclusions]** ). Durante el análisis del correo electrónico, estas reglas comparan las direcciones de correo de los destinatarios con las direcciones o nombres de dominio prohibidos incluidos en una lista de supresión global cifrada que se administra en la instancia de envío. Si se encuentra una coincidencia, el mensaje no se envía a ese destinatario.

El objetivo de esto es evitar que se incluya el servicio en una lista de bloqueados de actividad maliciosa, especialmente a través de Spamtrap. Por ejemplo, si se utiliza un Spamtrap para suscribirse a través de uno de sus formularios web, se envía un mensaje de correo electrónico de confirmación automáticamente a ese Spamtrap y esto hace que incluya su dirección lista de bloqueados automáticamente.

>[!NOTE]
>
>Las direcciones y los nombres de dominio contenidos en la lista de supresión global están ocultos. En los registros de análisis de envío solo se indica el número de destinatarios excluidos.
