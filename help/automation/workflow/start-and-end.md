---
product: campaign
title: Inicio y final (Start y End)
description: Descubra más información sobre las actividades de flujo de trabajo de Inicio y final (Start y End)
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 1de622bc-967b-403b-86e0-2ad32cb432e3
TQID: https://experienceleague.adobe.com/Y6nuELN3qjtuXhruC9MgmyqxzptNTJgfZ0XLGleQ3A4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 135
ht-degree: 100%

---

# Inicio y final{#start-and-end}



Las actividades **[!UICONTROL Start]** y **[!UICONTROL End]** permiten marcar de forma gráfica el inicio y el final de un flujo de trabajo. Estas actividades no tienen impacto funcional y, por tanto, son opcionales.

* **[!UICONTROL Start]**

  La ejecución de un flujo de trabajo comienza con actividades sin una transición entrante y actividades del tipo inicial.

  ![](assets/s_user_segmentation_start_stop.png)

* **[!UICONTROL End]**

  Puede configurar la actividad **[!UICONTROL End]** para interrumpir todas las tareas que estén en curso. Para ello, haga doble clic en la actividad para mostrar sus propiedades y marque la opción apropiada.

  ![](assets/s_user_segmentation_end.png)

  Los datos de la tabla de trabajo se eliminan automáticamente cuando se habilita la actividad final. Si no es necesario y para evitar cargas innecesarias, puede optar por deshabilitar la transición en la última salida de actividad. Por ejemplo, en una salida de envío, si no hay ningún proceso programado, anule la selección de la opción correspondiente como se muestra a continuación:

  ![](assets/s_advuser_delivery_option_no_output.png)
