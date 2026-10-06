---
product: campaign
title: Descripción de la entrega
description: Descubra más información sobre la actividad del flujo de trabajo Descripción de la entrega
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
TQID: 'https://experienceleague.adobe.com/-uyRqPAXzP-l05tmEfq4ZcJizCiGpTfY0qu-6tQ8cU0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 100%
---
# Descripción del envío{#delivery-outline}

La **descripción de la entrega** permite utilizar una descripción en un flujo de trabajo de la campaña. El esquema debe haberse creado con anterioridad en la campaña.

Para configurar la actividad, simplemente se debe seleccionar el esquema que desee y la fecha de contacto planificada. Se pueden agregar reglas de filtrado añadiendo tipologías o reglas tipológicas.

## Ejemplo: Inserción de una oferta mediante un esquema de entrega {#example--inserting-an-offer-via-a-delivery-outline}

La actividad **Descripción de entrega**, disponible en los flujos de trabajo de la campaña, permite presentar ofertas especificadas en una descripción de entrega de la campaña en curso.

>[!NOTE]
>
>El paquete de **Interaction** debe estar instalado.

1. En un flujo de trabajo, añada una actividad de descripción de la entrega antes de añadir una de entrega.
1. En la actividad del esquema de entrega, especifique el que desee utilizar.
1. Rellene los campos disponibles en función de la entrega.
1. Hay dos casos posibles:

   * Si desea acceder al motor de oferta, marque la casilla **[!UICONTROL Restrict the number of propositions selected]**. Especifique el espacio de oferta y el número de propuestas que se presentarán en la entrega.

     El motor de oferta tendrá en cuenta las reglas de elegibilidad y las consideraciones de oferta.

   * Si no selecciona la casilla, todas las ofertas del esquema de entrega se presentarán sin recurrir al motor de oferta.

   La vista previa tiene en cuenta el número de ofertas especificadas en la entrega. Cuando se ejecuta un flujo de trabajo, se tiene en cuenta el número especificado en el esquema de entrega.

   ![](assets/int_compo_offre_wf1.png)
