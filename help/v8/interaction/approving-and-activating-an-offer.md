---
product: campaign
title: Aprobación y activación de una oferta
description: Aprobación y activación de una oferta
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: managing-an-offer-catalog
exl-id: cf7649fe-f62a-4dfa-a19e-9c1ca545e3e3
TQID: 'https://experienceleague.adobe.com/f0zYxpc5-71Ci-4Q485v4rRdD1xHs6tKLkl7vrITMP0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 72%
---
# Aprobación y activación de una oferta{#approving-and-activating-an-offer}



Una vez finalizado el contenido de la oferta, es necesario aprobarla para que se duplique en el entorno en vivo y se distribuya. La aprobación se refiere al contenido de la oferta y sus requisitos.

El banner del panel de control de oferta indica si la oferta debe ir a través del ciclo de aprobación o no.

![Banner del panel de ofertas que indica que la oferta está pendiente de aprobación, con el botón Aprobación.](assets/offer_validate_001.png)

## Aprobación del contenido de la oferta {#approving-offer-content}

La aprobación del contenido de la oferta implica seleccionar la representación que desea poner a disposición del entorno en directo.

El contenido de una oferta tiene una representación por espacio. Dado que cada espacio de oferta tiene su propia estructura y sus propias funciones de procesamiento, la representación de la oferta puede variar.

Puede optar por aprobar el contenido de la oferta en algunos espacios disponibles y rechazarlo en otros.

>[!IMPORTANT]
>
>Una vez aprobado el contenido y la idoneidad de una oferta, el flujo de trabajo de la publicación (notificación de la oferta) se ejecuta automáticamente. La oferta está activa y disponible en todos los espacios activados.

Para aprobar el contenido de la oferta, siga estos pasos:

1. Haga clic en el botón **[!UICONTROL Approval]** y seleccione **[!UICONTROL Approve content]** en la ventana emergente.

   ![Menú de aprobación con Aprobar contenido seleccionado, abriendo la acción en el cuadro de diálogo de oferta.](assets/offer_validate_002.png)

1. En la lista desplegable, seleccione las representaciones que desea seguir editando o las que desee publicar en el entorno en directo y, a continuación, haga clic en **[!UICONTROL Content approval]**.

   ![Acción en el cuadro de diálogo de oferta: elija Continuar editando o Habilitar, agregue un comentario y haga clic en Aprobar contenido.](assets/offer_validate_003.png)

   Una vez aprobado el contenido de la oferta, la información se actualiza en la tabla del panel de control de ofertas.

   ![Panel de ofertas después de la aprobación: la representación muestra Habilitado y la sección Aprobaciones muestra Contenido aprobado.](assets/offer_validate_004.png)

   >[!NOTE]
   >
   >La mención **[!UICONTROL Content approved]** no significa que todas las representaciones de oferta se hayan habilitado y aprobado. Indica que se ha alcanzado el proceso de aprobación del contenido, aunque no todas las ofertas se hayan habilitado o aprobado.

## Aprobación de los requisitos para la oferta {#approving-offer-eligibility}

La aprobación de los requisitos de oferta implica aceptar o rechazar los pesos de la oferta y las reglas de elegibilidad también configuradas en la oferta o heredadas de las reglas creadas en la categoría principal.

>[!IMPORTANT]
>
>Una vez aprobado el contenido y la idoneidad de una oferta, el flujo de trabajo de la publicación (notificación de la oferta) se ejecuta automáticamente. La oferta está activa y disponible en todos los espacios activados.

* La lista completa de reglas puede verse haciendo clic en **[!UICONTROL Schedule and eligibility rules]**.

  ![Lista de reglas de horario e elegibilidad con ponderaciones e intervalos de fechas, abierta desde el cuadro de diálogo de aprobación.](assets/offer_validate_005.png)

* Para cambiar las reglas de elegibilidad, haga clic en **[!UICONTROL Reject]** y luego en **[!UICONTROL Eligibility approval]**.

  ![Cuadro de diálogo de aprobación de elegibilidad con la opción Rechazar seleccionada, un comentario y el botón de aprobación de elegibilidad.](assets/offer_validate_007.png)

  Los distintos estados se actualizan en el panel de control de ofertas.

  ![Tablero después del rechazo: se rechazó el banner de aprobación de idoneidad, el botón Enviar idoneidad, se rechazó la idoneidad.](assets/offer_validate_006.png)

* Para aceptar la idoneidad de la oferta, haga clic en **[!UICONTROL Approve eligibility]**.

  ![Botón Enviar elegibilidad abriendo la acción en el cuadro de diálogo de oferta con las opciones Aprobar y Rechazar.](assets/offer_validate_008.png)

  Apruebe la idoneidad, añada un comentario si es necesario y haga clic en **[!UICONTROL Eligibility approval]**.

  ![Cuadro de diálogo de aprobación de elegibilidad con Aprobar seleccionado, un comentario introducido y el botón de aprobación de elegibilidad.](assets/offer_validate_009.png)

  Los distintos estados se actualizan en el panel de control de ofertas.

  ![Panel que muestra la oferta pendiente de implementación en el entorno en vivo, con Elegibilidad aprobada y Contenido aprobado.](assets/offer_validate_010.png)

## Seguimiento de la aprobación {#approval-tracking}

El seguimiento de la aprobación está disponible en el tablero de ofertas. Haga clic en **[!UICONTROL Hide/display logs]** para acceder.

![Panel de ofertas con los registros de aprobación mostrados después de hacer clic en Ocultar/mostrar registros, enumerar acción, tipo y aprobador.](assets/offer_validate_012.png)

>[!NOTE]
>
>El seguimiento también está disponible en la pestaña **[!UICONTROL Audit]** de la oferta, con detalles de los comentarios de los revisores.

## Reinicio de la aprobación {#restart-the-approval}

Una vez lanzada la aprobación, puede ser relanzada. Para ello, siga estas instrucciones:

1. Haga clic **[!UICONTROL Content approved]** en el panel de control de ofertas.
1. En la ventana **[!UICONTROL Edit]** que aparece, seleccione la aprobación para reiniciar y, a continuación, haga clic en **[!UICONTROL Re-initialize approval to submit it again]**.
1. Confirme haciendo clic en **[!UICONTROL Ok]**.

![El diario de aprobaciones está en la ventana de edición con el vínculo Reinicializar aprobación para enviarla de nuevo.](assets/offer_validate_013.png)

## Publicación de la oferta {#publishing-the-offer}

Una vez que el contenido y la idoneidad de una oferta se hayan aprobado, la oferta se publica mediante un flujo de trabajo que se ejecuta automáticamente para cada oferta cuyo ciclo de aprobación haya finalizado. El flujo de trabajo de **[!UICONTROL Offer notification]** también se ejecuta cada hora para sincronizar (si es necesario) los espacios y las categorías que contiene el catálogo de ofertas desde el entorno de diseño al entorno en vivo.

El panel de control de la oferta disponible en el entorno de diseño contiene información sobre la publicación, incluido el nombre de la oferta coincidente del entorno en directo.

![Diseño del tablero de ofertas: titular de la fecha de implementación, ofrece un vínculo en línea con el estado Publicado y una representación en directo en línea.](assets/offer_golive_001.png)

Para mostrar la oferta disponible en el entorno en directo, haga clic en la etiqueta de oferta: la oferta en directo tiene un panel de control que contiene toda la información relevante.

![Vínculo al tablero de ofertas en directo, que muestra el estado En línea, su entorno y su programación y reglas de elegibilidad.](assets/offer_golive_002.png)

## Desactivación de una oferta {#disabling-an-offer}

Una vez aprobada la oferta, puede desactivarla.

Para ello, vaya al panel de control de una oferta en línea o de una oferta esperando para conectarse y, a continuación, haga clic en **[!UICONTROL Disable offer]**.

También puede deshabilitar directamente una categoría si accede a la pestaña **[!UICONTROL Eligibility]** y activa la casilla **[!UICONTROL Enabled]**.

>[!NOTE]
>
>Cuando se elimina una oferta en un entorno de diseño, se desactiva automáticamente en el entorno en línea relacionado. Tras un periodo de retención de propuestas, las ofertas desactivadas se eliminan del entorno en línea.

![Panel de ofertas pendiente de implementación, con el botón Deshabilitar oferta usado para desactivar la oferta.](assets/offer_preview_deactivate.png)
