---
product: campaign
title: Filtro de destinatarios duplicados
description: Obtenga información sobre cómo filtrar destinatarios duplicados
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
TQID: https://experienceleague.adobe.com/jwnm0saAGOFD4FjCniKHBm6xDd8H2QggSy3UvrMAb-E
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 147
ht-degree: 100%

---

# Filtro de destinatarios duplicados {#filtering-duplicated-recipients}



En este ejemplo, deseamos filtrar los destinatarios que aparecen dos veces o más en una entrega para recuperar perfiles duplicados.

Para crear este ejemplo, aplique los pasos siguientes:

1. Arrastre y suelte una actividad **[!UICONTROL Query]** en un flujo de trabajo y ábrala.
1. Haga clic en **[!UICONTROL Edit query]** y configure las dimensiones de objetivo y filtrado en **[!UICONTROL Recipients]**.

   ![](assets/query_recipients_1.png)

1. Defina la siguiente condición de filtro para segmentar al destinatario que existe en el registro de envíos. Elija **Registro de destinatarios de envío (broadlog)** en la columna **Expresión**, elija **existe como** en la columna **Operador**.

   ![](assets/query_recipients_2.png)

1. Defina la siguiente condición de filtro para dirigir su envío. En la columna Expresión, elija **[!UICONTROL Internal name]** y luego, en la columna Operador, **[!UICONTROL equal to]** .
1. En la columna de valor, agregue el nombre interno de la entrega segmentado.

   ![](assets/query_recipients_3.png)

1. Con un operador **[!UICONTROL AND]**, repita las mismas operaciones para segmentar otros envíos.

   ![](assets/query_recipients_4.png)

La transición saliente contiene los destinatarios duplicados dirigidos en las entregas.
