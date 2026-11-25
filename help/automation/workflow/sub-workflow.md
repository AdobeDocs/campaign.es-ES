---
product: campaign
title: Subflujo de trabajo
description: Descubra más información sobre la actividad del subflujo de trabajo
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: c530fb4e-d21e-4059-88e1-77a8d33a7832
TQID: 'https://experienceleague.adobe.com/XS5rd13a3naqU6284JA3zTwHzZuNx1Efql-C-Ud-oV8'
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
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 84%
---
# Subflujo de trabajo{#sub-workflow}



La actividad **[!UICONTROL Sub-workflow]** permite activar la ejecución de otro flujo de trabajo y recuperar el resultado. Esta actividad permite utilizar flujos de trabajo complejos mientras se utiliza una interfaz simplificada.

Puede activar varios subflujos de trabajo en un solo flujo de trabajo. Los subflujos de trabajo se ejecutan de forma sincrónica.

En el ejemplo siguiente, un flujo de trabajo principal llama a un subflujo de trabajo mediante saltos. Para obtener más información sobre los objetos gráficos de tipo salto, consulte [Salto (puntos iniciales y finales)](jump-start-point-and-end-point.md).

1. Cree un flujo de trabajo que utilizará como subflujo de trabajo en otro flujo de trabajo.
1. Inserte una actividad **[!UICONTROL Jump (end point)]** con una prioridad de 1 al principio del flujo de trabajo. Si tiene varios saltos del tipo &quot;llegada&quot;, Adobe Campaign utiliza el salto de &quot;llegada&quot; con el número más bajo.
1. Inserte una actividad **[!UICONTROL Jump (start point)]** con una prioridad de 2 al final del flujo de trabajo. Si tiene varios saltos del tipo &quot;inicio&quot;, Adobe Campaign utiliza el salto &quot;inicio&quot; con el número más alto.

   ![Diagrama de subflujo de trabajo que comienza con Jump (punto final) 1 y termina con Jump (punto inicial) 2 alrededor de las consultas y una Union.](assets/subworkflow_jumps.png)

   >[!NOTE]
   >
   >Si la actividad de subflujo de trabajo hace referencia a un flujo de trabajo con varias actividades **[!UICONTROL Jump]**, se ejecuta el subflujo de trabajo entre el salto de tipo &quot;llegada&quot; con el número más bajo y el salto de tipo &quot;inicio&quot; con el número más alto.
   >
   >Para que el subflujo de trabajo se ejecute correctamente, solo debe haber un único salto de tipo &quot;llegada&quot; con el número más bajo y un único salto de tipo de &quot;inicio&quot; con el número más alto.

1. Complete y guarde este &quot;subflujo de trabajo&quot;.
1. Cree un flujo de trabajo principal.
1. Inserte una actividad **[!UICONTROL Sub-workflow]** y ábrala.
1. Seleccione el flujo de trabajo que desee utilizar en la lista desplegable **[!UICONTROL Workflow template]**.

   ![Actividad de subflujo de trabajo con la lista desplegable Plantilla de flujo de trabajo que enumera los flujos de trabajo disponibles, Flujo de trabajo secundario (WKF55) seleccionado.](assets/subworkflow_selection.png)

1. También puede agregar un script de configuración para alterar el flujo de trabajo al que se hace referencia.
1. Haga clic **[!UICONTROL Ok]**. Se crea automáticamente una transición saliente con la etiqueta de la actividad **[!UICONTROL Jump (start point)]** del flujo de trabajo seleccionado.

   ![Flujo de trabajo principal con subflujo de trabajo de llamada y una transición saliente denominada Jump (start point) 2.](assets/subworkflow_outbound.png)

1. Ejecute el flujo de trabajo.

Una vez ejecutado, el flujo de trabajo llamado como subflujo de trabajo permanece en estado **[!UICONTROL Being edited]**, lo que significa lo siguiente:

* No puede hacer clic con el botón derecho en las transiciones para mostrar el destino.
* No se puede mostrar el recuento de poblaciones intermedias.
* Los registros de subflujo de trabajo se muestran en el flujo de trabajo principal.

  ![Pestaña Auditoría del flujo de trabajo principal que muestra mensajes de registro de subflujo de trabajo para la consulta de resultados.](assets/subworkflow_logs.png)

>[!NOTE]
>
>Si se produce algún error en el subflujo de trabajo, el flujo de trabajo principal se pausa y se crea una copia del subflujo de trabajo.

## Parámetros de entrada (opcional) {#input-parameters--optional-}

* tableName
* esquema

Cada evento entrante debe especificar un objetivo definido por estos parámetros.

## Parámetros de salida {#output-parameters}

* tableName
* esquema
* recCount

Este conjunto de tres valores identifica la población objetivo de la consulta. **[!UICONTROL tableName]** es el nombre de la tabla que registra los identificadores de destinatario, **[!UICONTROL schema]** es el esquema de la población (normalmente, nms:recipient) y **[!UICONTROL recCount]** es el número de elementos de la tabla.

* targetSchema: Este valor es el esquema de la tabla de trabajo. Este parámetro es válido para todas las transiciones con **[!UICONTROL tableName]** y **[!UICONTROL schema]**.
