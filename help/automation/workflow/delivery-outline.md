---
product: campaign
title: Descripción de la entrega
description: Descubra más información sobre la actividad del flujo de trabajo Descripción de la entrega
feature: Workflows, Targeting Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 91%

---

# Descripción del envío{#delivery-outline}



La **descripción de la entrega** permite utilizar una descripción en un flujo de trabajo de la campaña. El esquema debe haberse creado con anterioridad en la campaña.

Para obtener más información sobre los esquemas de entrega en Adobe Campaign, consulte esta sección .

Para configurar la actividad, simplemente se debe seleccionar el esquema que desee y la fecha de contacto planificada. Se pueden agregar reglas de filtrado añadiendo tipologías o reglas tipológicas.

## Ejemplo: Inserción de una oferta mediante un esquema de entrega {#example--inserting-an-offer-via-a-delivery-outline}

La actividad **Descripción de entrega**, disponible en los flujos de trabajo de la campaña, permite presentar ofertas especificadas en una descripción de entrega de la campaña en curso.

>[!NOTE]
>
>El paquete de **Interaction** debe estar instalado.

1. En un flujo de trabajo, añada una actividad de descripción de la entrega antes de añadir una de entrega.
1. En la actividad del esquema de entrega, especifique el que desee utilizar.

   Para obtener más información sobre esquemas de entrega específicos, consulte esta sección .

1. Rellene los campos disponibles en función de la entrega.
1. Hay dos casos posibles:

   * Si desea acceder al motor de oferta, marque la casilla **[!UICONTROL Restrict the number of propositions selected]**. Especifique el espacio de oferta y el número de propuestas que se presentarán en la entrega.

      El motor de oferta tendrá en cuenta las normas de idoneidad y las consideraciones de oferta.

   * Si no selecciona la casilla, todas las ofertas del esquema de entrega se presentarán sin recurrir al motor de oferta.

   La vista previa tiene en cuenta el número de ofertas especificadas en la entrega. Cuando se ejecuta un flujo de trabajo, se tiene en cuenta el número especificado en el esquema de entrega.

   ![](assets/int_compo_offre_wf1.png)
