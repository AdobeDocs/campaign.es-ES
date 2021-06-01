---
product: Adobe Campaign
title: Espacios de oferta de interacción de campaña
description: Obtenga información sobre cómo crear espacios de oferta
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 39%

---

# Creación de espacios de oferta{#creating-offer-spaces}

El contenido del catálogo de ofertas se configura en espacios de oferta. De forma predeterminada, el contenido puede incluir los campos siguientes: **[!UICONTROL Title]**, **[!UICONTROL Destination URL]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]** y **[!UICONTROL Text content]**. La secuencia de campos se configura en el espacio de oferta.

Como **administrador técnico**, puede crear espacios de oferta en el entorno Design . Debe tener acceso a la subcarpeta del espacio de oferta. Una vez creados, estos espacios de oferta se duplican automáticamente en el entorno Live durante la aprobación de la oferta.

La renderización HTML se crea mediante una función de renderización. La secuencia de los campos definidos en la función de renderización debe ser idéntica a la secuencia configurada en el contenido.

![](assets/offer_space_create_009.png)

Para crear un nuevo espacio de oferta, siga los pasos a continuación:

1. En la lista de espacios de oferta, haga clic en **[!UICONTROL New]**.

   ![](assets/offer_space_create_001.png)

1. Seleccione el canal que desee utilizar y cambie la etiqueta del espacio de oferta.

   ![](assets/offer_space_create_002.png)

1. Marque la opción **[!UICONTROL Enable unitary mode]**

1. Vaya a la ventana **[!UICONTROL Content field]** y haga clic en **[!UICONTROL Add]**.

   ![](assets/offer_space_create_003.png)

1. Vaya al nodo **[!UICONTROL Content]** y seleccione los campos en el siguiente orden: **[!UICONTROL Title]**, luego **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]**, y **[!UICONTROL Destination URL]**.

   ![](assets/offer_space_create_004.png)

1. Marque la opción **[!UICONTROL Required]** para que cada campo sea obligatorio.

   >[!NOTE]
   >
   >Esta opción se utiliza en la vista previa y hace que los espacios de oferta no sean válidos al publicar si falta uno de los campos obligatorios en la oferta. Sin embargo, si una oferta ya está en directo en un espacio de oferta, estos criterios no se tienen en cuenta.

   ![](assets/offer_space_create_005.png)

1. Haga clic en **[!UICONTROL Edit functions]** para crear una función de renderización.

   Estas funciones se utilizan para generar representaciones de oferta en un espacio de oferta. Existen varios formatos posibles: HTML o texto.

   **Nota** : El formato XML está restringido a interacciones entrantes que no están disponibles temporalmente. [Obtenga más información](../start/capability-matrix.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. Vaya a la pestaña **[!UICONTROL HTML rendering]** y seleccione **[!UICONTROL Overload the HTML rendering function]**.
1. Inserte la función de renderización.

   ![](assets/offer_space_create_007.png)

## Estados de propuesta de oferta {#offer-proposition-statuses}

El estado de la propuesta de oferta varía en función de las interacciones con la población de destino. El módulo Interacción de campaña incluye un conjunto de valores que se pueden aplicar a la propuesta de oferta a lo largo de su ciclo de vida. Debe configurar la plataforma para que el estado cambie cuando se cree y acepte la propuesta de oferta.

>[!NOTE]
>
>La actualización de estado es un proceso **asíncrono**. Se lleva a cabo mediante el flujo de trabajo de seguimiento, que se activa cada hora.

### Lista de estado de oferta {#status-list}

Los estados de oferta disponibles son:

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

Estos valores no se aplican de forma predeterminada: deben configurarse.

>[!NOTE]
>
>El estado de una propuesta de oferta se cambia automáticamente a “Presented” si la oferta está vinculada a una entrega con el estado “Sent”.

### Estado de la oferta cuando se crea la propuesta {#configuring-the-status-when-the-proposition-is-created}

Cuando una propuesta de oferta se **crea**, se actualiza su estado.

En el entorno **[!UICONTROL Design]**, para cada espacio de oferta, configure el estado que se aplicará cuando se cree una propuesta, según la información que desee mostrar en los informes de oferta.

Para realizar esto, siga los pasos a continuación:

1. Vaya a la pestaña **[!UICONTROL Storage]** del espacio deseado.
1. Seleccione el estado que se aplicará a la propuesta cuando se cree.

   ![](assets/offer_update_status_001.png)

### Estado de la oferta cuando se acepta la propuesta {#configuring-the-status-when-the-proposition-is-accepted}

Una vez **accepted** una propuesta de oferta, utilice uno de los valores proporcionados de forma predeterminada para configurar el nuevo estado de la propuesta. La actualización se aplica cuando un destinatario hace clic en un vínculo de la oferta.

Para realizar esto, siga los pasos a continuación:

1. Vaya a la pestaña **[!UICONTROL Storage]** del espacio deseado.
1. Seleccione el estado que desea aplicar a la propuesta cuando se acepte.

   ![](assets/offer_update_status_002.png)

<!--
**Inbound interaction**

The **[!UICONTROL Storage]** tab lets you define statuses for **proposed** and **accepted** offer propositions only. For inbound interaction, the status of offer propositions should be specified directly in the URL for calling the offer engine, rather than through the interface. This way, you will be able to specify which status to apply in other cases, for example if an offer proposition is rejected.

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

For instance, the proposition (identifier **40004**) that matches the **Home insurance** offer displayed on the **Neobank** site contains the following URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

As soon as a visitor clicks the offer, and therefore the URL, the **[!UICONTROL Accepted]** status (value **3**) is applied to the proposition and the visitor is redirected to a new page of the **Neobank** site to take out the insurance contract.

>[!NOTE]
>
>If you want to specify another status in the url (for example if an offer proposition is rejected), use the value corresponding to the desired status. Example: **[!UICONTROL Rejected]** = "5", **[!UICONTROL Presented]** = "1" and so on.
>
>Statuses and their values can be retrieved in the **[!UICONTROL Offer propositions (nms)]** data schema. For more on this, refer to [this page](../../configuration/using/data-schemas.md).

**Outbound interaction**
-->

Se puede aplicar automáticamente el estado **[!UICONTROL Interested]** a una propuesta de oferta cuando el envío contiene un vínculo. Simplemente añada el valor **_urlType=&quot;11&quot;** al vínculo:

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## Vista previa de oferta por espacio {#offer-preview-per-space}

En la pestaña **[!UICONTROL Preview]** , puede ver las ofertas para las que el destinatario es elegible mediante un método elegido. En el siguiente ejemplo, el destinatario es elegible para las tres propuestas de oferta por correo electrónico.

![](assets/offer_space_overview_002.png)

Si un destinatario no es elegible para ninguna oferta, esto se muestra en la vista previa.

![](assets/offer_space_overview_001.png)

<!--
The preview can ignore contexts when they are restricted to a space. This is the case when the interaction schema has been extended to add fields referenced in a space using an inbound channel (for more on this, refer to Extension example.
-->
