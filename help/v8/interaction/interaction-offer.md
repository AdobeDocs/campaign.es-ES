---
title: Oferta de interacción de campaña
description: Obtenga información sobre cómo crear una oferta
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 4dc2008d-681c-4a79-8fc8-c270c9224ab9
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 59%

---

# Creación de una oferta

Para crear una oferta, siga los pasos a continuación:

1. Vaya a la ficha **[!UICONTROL Campaigns]** y haga clic en el vínculo **[!UICONTROL Offers]**.

1. Haga clic en el botón **[!UICONTROL Create]**.

1. Cambie la etiqueta y seleccione la categoría a la que debe pertenecer la oferta.

1. Haga clic en **[!UICONTROL Save]** para crear la oferta.

   La oferta está disponible en la plataforma y se puede configurar su contenido.

## Configuración de idoneidad

Ahora puede usar la ficha **[!UICONTROL Eligibility]** para definir:

* El periodo de elegibilidad de la oferta. [Más información](#eligibility-period)
* Filtros en la población de destinatarios de la oferta. [Más información](#filters-on-the-target)
* La ponderación de la oferta. [Más información](#offer-weight)

### Período de idoneidad de oferta{#eligibility-period}

En la pestaña **[!UICONTROL Eligibility]** de la oferta, defina el periodo de elegibilidad de la oferta. utilice las listas desplegables para seleccionar una fecha de inicio y una de finalización en el calendario.

![](assets/offer_eligibility_create_002.png)

Fuera de este periodo, la oferta no se selecciona. Si también se han configurado las fechas de idoneidad para la categoría de oferta, se aplica el periodo más restrictivo.

### Añadir filtros en el destinatario {#filters-on-the-target}

En la pestaña **[!UICONTROL Eligibility]** de la oferta, aplique filtros al destino de la oferta.

Para ello, haga clic en el vínculo **[!UICONTROL Edit query]** y seleccione el filtro que desee aplicar.

![](assets/offer_eligibility_create_003.png)

Si ya se han creado filtros predefinidos, puede seleccionarlos de la lista de filtros de usuario. [Más información](interaction-predefined-filters.md)

![](assets/offer_eligibility_create_004.png)

### Definición de la ponderación de la oferta {#offer-weight}

Para permitir que el motor decida entre varias ofertas para las que el objetivo es apto, se debe asignar una o más ponderaciones a la oferta. Asimismo, se puede aplicar filtros al destino si es necesario o restringir el espacio de oferta al que se aplicará la ponderación. Se prefiere una oferta con una ponderación más significativa sobre una oferta con menos ponderación.

Se puede configurar múltiples ponderaciones para la misma oferta, por ejemplo, para distinguir subperiodos, objetivos específicos o incluso un espacio de oferta.

Por ejemplo, una oferta puede tener una ponderación de A para los contactos de 18 a 25 años de edad y una ponderación de B para los contactos que se encuentran por encima de dicho rango. Si una oferta es apta para todos los verano, también puede tener una ponderación de A en julio y un ponderación de B en agosto.

>[!NOTE]
>
>La ponderación asignada se puede modificar de forma temporal de acuerdo con los parámetros de la categoría a la que pertenece la oferta. [Más información](interaction-offer-catalog.md#creating-offer-categories)

Para crear una ponderación en una oferta, siga los siguientes pasos:

1. En la ficha **[!UICONTROL Eligibility]** de la oferta, haga clic en **[!UICONTROL Add]**.

   ![](assets/offer_weight_create_001.png)

1. Cambie la etiqueta y asigne un peso. El valor predeterminado es 1.

   ![](assets/offer_weight_create_006.png)

   >[!CAUTION]
   >
   >Si no se introduce ningún peso (0), el objetivo no se considera apto para la oferta.

1. Si desea que el peso se aplique durante un periodo determinado, defina las fechas de idoneidad.

   ![](assets/offer_weight_create_002.png)

1. Si es necesario, limite el peso a un espacio de oferta específico.

   ![](assets/offer_weight_create_003.png)

1. Aplicar un filtro a un destino.

   ![](assets/offer_weight_create_004.png)

1. Haga clic en **[!UICONTROL OK]** para guardar la ponderación.

   ![](assets/offer_weight_create_005.png)

   >[!NOTE]
   >
   >Si un objetivo es apto para múltiples pesos para una oferta seleccionada, el motor mantiene el mejor peso (más alto). Al llamar al motor de oferta, se selecciona una oferta por un máximo de una vez por contacto.

### Resumen de las reglas de idoneidad para la oferta {#a-summary-of-offer-eligibility-rules}

Una vez completada la configuración, se encontrará disponible un resumen de las reglas de elegibilidad en el panel de ofertas.

Para visualizarlo, haga clic en el vínculo **[!UICONTROL Schedule and eligibility rules]**.

![](assets/offer_eligibility_create_005.png)

## Creación del contenido de la oferta {#creating-the-offer-content}

Utilice la ficha **[!UICONTROL Content]** para definir el contenido de la oferta.

![](assets/offer_content_create_001.png)

1. Defina los distintos parámetros del contenido de la oferta.

   * **[!UICONTROL Title]**: especifique el título que desea que aparezca en la oferta. Advertencia: esto no hace referencia a la etiqueta de la oferta, la cual se define en la pestaña **[!UICONTROL General]**.
   * **[!UICONTROL Destination URL]**: especifique la dirección URL de la oferta. Debe comenzar con &quot;http://&quot; o &quot;https://&quot;.
   * **[!UICONTROL Image URL]**: especifique una dirección URL o una ruta de acceso a la imagen de la oferta.
   * **[!UICONTROL HTML content]** / **[!UICONTROL Text content]**: introduzca el cuerpo de la oferta en la pestaña que desee. Para generar un seguimiento, el **[!UICONTROL HTML content]** debe estar compuesto por elementos HTML que se puedan incluir en un elemento de tipo `<div>` Por ejemplo, el resultado de un elemento en la página HTML estará seguido por:`<table>`

   ```
      <div> 
       <table>
        <tr>
         <th>Month</th>
         <th>Savings</th>   
        </tr>   
        <tr>    
         <td>January</td>
         <td>$100</td>   
        </tr> 
       </table> 
      </div>
   ```

   Aprenda a definir la dirección URL de aceptación en [esta sección](interaction-offer-spaces.md#configuring-the-status-when-the-proposition-is-accepted).

   ![](assets/offer_content_create_002.png)

   Para buscar los campos requeridos tal y como estaban definidos durante la configuración del espacio de oferta, haga clic en el vínculo **[!UICONTROL Content definitions]** para mostrar la lista. [Más información](interaction-offer-spaces.md)

   ![](assets/offer_content_create_003.png)

   En este ejemplo, la oferta debe incluir un título, una imagen, contenido HTML y una dirección URL de destino.

## Previsualización de la oferta {#previewing-the-offer}

Una vez configurado el contenido de la oferta, se puede obtener una vista previa de la oferta tal y como aparecerá para su destinatario.

Para ello, haga lo siguiente:

1. Seleccione la pestaña **[!UICONTROL Preview]**.

   ![](assets/offer_preview_create_001.png)

1. Seleccione la representación de la oferta que desee ver.

   ![](assets/offer_preview_create_002.png)

1. Si ha personalizado el contenido de la oferta, seleccione el objetivo de la oferta para ver la personalización.

<!--

## Create a hypothesis on an offer {#creating-a-hypothesis-on-an-offer}

You can create hypotheses on your offer propositions. This lets you determine the impact of your offers on purchases carried out for the product concerned.

>[!NOTE]
>
>These hypotheses are carried out via Response Manager. Please check your license agreement.

Hypotheses carried out on an offer proposition are referenced in their **[!UICONTROL Measure]** tab.

Creating hypotheses is detailed in [this page](../../campaign/using/about-response-manager.md).

-->

## Aprobar y activar una oferta{#approve-offers}

Ahora puede aprobar y activar la oferta para que esté disponible en el entorno **Live**.

Para obtener más información, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html#approving-offer-content){target="_blank"}.

## Administración de presentación de ofertas{#offer-presentation}

Campaign permite controlar el flujo de propuestas de ofertas utilizando las reglas de presentación. Estas reglas, que son específicas de la interacción de Campaign, son **reglas de tipología**. Permiten excluir ofertas basadas en el historial de propuestas que ya se hayan hecho a un destinatario. Se las menciona en el entorno.

Para obtener más información, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/managing-offer-presentation.html#managing-offers){target="_blank"}.

## Simulación de oferta

El módulo de **Simulation** permite probar la distribución de ofertas pertenecientes a una categoría o a un entorno antes de enviar la propuesta a los destinatarios.

La simulación tiene en cuenta los contextos y las reglas de idoneidad aplicadas anteriormente a las ofertas y sus reglas de presentación. Esto permite probar y perfeccionar varias versiones de la propuesta de oferta sin utilizar realmente una por encima o por debajo del objetivo, ya que la simulación no tiene ningún impacto en los destinatarios a los que va dirigida.

Para obtener más información sobre la simulación de ofertas, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/simulating-offers/about-offers-simulation.html){target="_blank"}.
