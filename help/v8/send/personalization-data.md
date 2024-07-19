---
title: Fuentes de datos de Personalization
description: Descubra qué fuentes se pueden utilizar para la personalización
feature: Personalization
role: User
level: Beginner
exl-id: 711256e2-ab77-404a-b052-6793a85da193
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 38%

---

# Fuentes de datos de Personalization{#personalization-data}

Los datos de Personalization se pueden recuperar de varios tipos de fuentes: fuente de datos de la base de datos de Campaign, fuente de datos de archivo externo o fuente de datos de la base de datos externa.

## Fuente de datos de Campaign database

En el caso más común, los datos de personalización se almacenan en la base de datos. Por ejemplo, &quot;campos personalizados de destinatario&quot; son todos los campos definidos en la tabla de destinatarios, campos estándar (normalmente: apellidos, nombre, dirección, ciudad, fecha de nacimiento, etc.) o campos personalizados.

![Campos personalizados de campaña en un correo electrónico](assets/perso-campaign-datasource.png)


## Fuente de datos de archivo externo

Puede utilizar un archivo externo que contenga todos los campos definidos en las columnas. Este archivo se utiliza como entrada durante una definición de envío de mensaje. Puede elegir insertar esos perfiles en la base de datos o no.

Para seleccionar el archivo que se usará como origen de datos, busque el vínculo Para en la ventana de creación de mensajes y seleccione la opción **Defined in an external file**. Una vez cargado el archivo, acceda a los datos del destinatario en las opciones de personalización, desde la entrada **Fields from the file**.

![Datos de Personalization de un archivo](assets/perso-from-file.png)


## Fuente de datos FDA

Los datos de Personalization se pueden extraer de una tabla externa mediante [Acceso de datos federado](../connect/fda.md).  Si desea personalizar los envíos utilizando datos de la base de datos externa, recopile los datos para utilizarlos en un flujo de trabajo para que estén disponibles en una tabla temporal.

Para ello, agregue una actividad **Query** al flujo de trabajo de objetivos y use el vínculo **Add data...** para seleccionar la base de datos externa. El proceso detallado está disponible en [esta sección](../../automation/workflow/query.md#adding-data).

A continuación, utilice los datos de la tabla temporal para personalizar su envío. Una vez configurada la actividad de consulta, acceda a los datos externos en las opciones de personalización, desde la entrada **Target extension**.

![Datos de Personalization de una base de datos externa](assets/perso-external-db.png)

Al utilizar datos externos a los que se accede en FDA, se recomienda preprocesar la personalización de mensajes en un flujo de trabajo dedicado mediante la opción **Preparar los datos de personalización con un flujo de trabajo**, como se detalla a continuación.

### Optimización de la personalización {#optimize-personalization}

Puede optimizar la personalización mediante una opción dedicada: **[!UICONTROL Prepare the personalization data with a workflow]**, disponible en la pestaña **[!UICONTROL Analysis]** de las propiedades de entrega.

Durante el análisis de envío, esta opción crea y ejecuta automáticamente un flujo de trabajo que almacena todos los datos vinculados con el objetivo en una tabla temporal, incluidos los datos de tablas vinculadas en FDA.

Marcar esta opción puede mejorar el rendimiento del análisis de envío cuando se procesan muchos datos, especialmente si los datos de personalización proceden de una tabla externa a través de FDA. [Más información](../connect/fda.md).

Para utilizar esta opción, siga los pasos a continuación:

1. Cree una campaña.
1. En la pestaña **[!UICONTROL Targeting and workflows]** de la campaña, agregue una actividad **Consulta** al flujo de trabajo.
1. Agregue una actividad **[!UICONTROL Email delivery]** al flujo de trabajo y ábrala.
1. Vaya a la pestaña **[!UICONTROL Analysis]** de la **[!UICONTROL Delivery properties]** y seleccione la opción **[!UICONTROL Prepare the personalization data with a workflow]**.
1. Configure la entrega e inicie el flujo de trabajo para iniciar el análisis.

Una vez finalizado el análisis, los datos de personalización se almacenan en una tabla temporal a través de un flujo de trabajo técnico temporal que se crea sobre la marcha durante el análisis.

Este flujo de trabajo no es visible desde la interfaz de Adobe Campaign. Solo pretende ser un medio técnico para almacenar y gestionar rápidamente los datos de personalización.

Una vez completado el análisis, vaya al flujo de trabajo **[!UICONTROL Properties]** y seleccione la pestaña **[!UICONTROL Variables]**. Se puede ver el nombre de la tabla temporal que puede utilizar para realizar una llamada SQL con el fin de mostrar los ID que contiene.

## Datos de Personalization en un flujo de trabajo

Cuando se crea una entrega en el contexto de un flujo de trabajo, se pueden utilizar los datos de la tabla de flujo de trabajo temporal. Los datos almacenados en la tabla de trabajo temporal del flujo de trabajo están disponibles para tareas de personalización. Los datos se pueden utilizar en los campos personalizados.

Estos datos se agrupan en el menú **[!UICONTROL Target extension]**. Para obtener más información, consulte [esta sección](../../automation/workflow/use-workflow-data.md#target-data).
