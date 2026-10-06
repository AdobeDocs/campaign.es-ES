---
product: campaign
title: Exclusión
description: Descubra más información sobre la actividad del flujo de trabajo Exclusión
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8ea831e2-8e6e-4ef0-ac05-f27ebf89ccb9
TQID: 'https://experienceleague.adobe.com/N3G0NbmUjk9fbgjKW957QneAHZ7Oy12seBK-AfO6puM'
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
source-wordcount: '358'
ht-degree: 100%
---
# Exclusión{#exclusion}



Una actividad de tipo **exclusión** permite crear un objetivo basado en un objetivo principal del que se extraen uno o más objetivos.

Para configurar esta actividad, introduzca su etiqueta y seleccione el grupo de destinatarios principal: la población del conjunto principal le permite construir el resultado. Se excluirán los perfiles compartidos por el conjunto principal y al menos una de las actividades de entrada.

![](assets/s_user_segmentation_exclu.png)

>[!NOTE]
>
>Para obtener más información sobre la configuración y el uso de la actividad de exclusión, consulte [Exclusión de una población (Exclusión)](targeting-workflows.md#excluding-a-population--exclusion-).

Seleccione la opción **[!UICONTROL Generate complement]** si desea utilizar la población restante. El complemento contendrá la población entrante principal menos la población saliente. A continuación, se agregará una transición de salida adicional a la actividad de la siguiente manera:

![](assets/s_user_segmentation_exclu_compl.png)

## Ejemplos de exclusión {#exclusion-examples}

En el ejemplo siguiente, se busca compilar una lista de destinatarios que tengan entre 18 y 30 años, al tiempo que se excluyen los residentes de París.

1. Inserte y abra una actividad de tipo **[!UICONTROL Exclusion]** que siga dos consultas. La primera consulta se dirige a los destinatarios que viven en París. La segunda consulta se aplica a los objetivos que tengan entre 18 a 30 años.
1. Introduzca el conjunto principal. En este caso, el conjunto principal es la consulta de **18-30 años de edad.** Los elementos pertenecientes al segundo conjunto se excluirán del resultado final.
1. Marque la opción **[!UICONTROL Generate complement]** si desea explotar los datos que quedan después de la exclusión. En este caso, el complemento está compuesto por destinatarios de entre 18 y 30 años que viven en París.
1. Apruebe la configuración de exclusión y, a continuación, inserte una actividad de lista de actualización en el resultado. También puede insertar una actualización de lista adicional al complemento donde sea necesario.
1. Ejecución de un flujo de trabajo. En este ejemplo, el resultado está compuesto por destinatarios de entre 18 y 30 años, pero los que viven en París se excluyen y envían al complemento.

   ![](assets/exclusion_example.png)

## Parámetros de entrada {#input-parameters}

* tableName
* esquema

Cada evento entrante debe especificar un objetivo definido por estos parámetros.

## Parámetros de salida {#output-parameters}

* tableName
* esquema
* recCount

Este conjunto de tres valores identifica el destino resultante de la exclusión. **[!UICONTROL tableName]** es el nombre de la tabla que registra los identificadores de destinatario, **[!UICONTROL schema]** es el esquema de la población (normalmente, nms:recipient) y **[!UICONTROL recCount]** es el número de elementos de la tabla.

La transición asociada al complemento tiene los mismos parámetros.
