---
product: campaign
title: AND-join
description: AND-join
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: c70a106d-3518-4eac-9944-6f7c93d85bac
TQID: 'https://experienceleague.adobe.com/1ChXl3Rlm93ftFFaD7Z-PcoO7CwUcxRHm2JdCFzIOZs'
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
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 96%
---
# AND-join{#and-join}



Una unión activa su transición saliente solo cuando se activan todas las transiciones entrantes, es decir, cuando terminan todas las actividades anteriores. Esto le permite asegurarse de que algunas actividades han finalizado antes de continuar ejecutándose el flujo de trabajo.

Por ejemplo, puede utilizar una actividad AND-join en el contexto de la creación de contenido y la automatización de entrega de envíos para asegurarse de que un envío se inicie solo cuando se hayan completado los pasos de consultas de destinatario y actualizaciones de contenido. Hay un caso de uso específico en

![](assets/and-join-usage.png)

>[!NOTE]
>
>Tenga en cuenta que las transiciones entrantes configuradas con diferentes dimensiones de segmentación no se pueden unir mediante una actividad **[!UICONTROL AND-join]**.

La población enviada de la actividad se determina seleccionando un conjunto principal entre las transiciones entrantes de la actividad.

La transición saliente solo puede contener una de las poblaciones de transición entrantes. Si la actividad no está configurada, la transición saliente seleccionará de forma aleatoria una de las poblaciones entrantes.

>[!CAUTION]
>
>En el caso de las actividades de tipo **AND-join**, las variables de eventos se combinan, pero si se define el mismo evento variable dos veces, se genera un conflicto y el valor se mantiene indeterminado. Para obtener más información, consulte [esta sección](javascript-scripts-and-templates.md#event-variables).
