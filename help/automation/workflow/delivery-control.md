---
product: campaign
title: Control de entregas
description: Descubra más información sobre la actividad del flujo de trabajo Control de entregas
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 09fe638d-5e1c-49d1-9196-6300c1e56703
TQID: https://experienceleague.adobe.com/C-BZfQ-iFGx5GJu1iEfUci-IJa6zBHQYkQe0Rii4agw
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 100%

---

# Control de entregas{#delivery-control}

Una acción del tipo **Delivery control** permite iniciar, pausar o detener una entrega.

El envío puede ser especificado en la transición, una entrega seleccionado de manera explícita o una entrega calculado por un script. Para obtener más información, consulte [Entrega](delivery.md).

![](assets/edit_diffusion_act.png)

Si selecciona **[!UICONTROL Start]**, la actividad realizará todos los pasos necesarios para iniciar la entrega (cálculo del objetivo, preparación del contenido, envío). Si ya se han realizado algunos de estos pasos por una actividad de flujo de trabajo anterior, no se volverán a realizar. Por ejemplo, si la estimación del objetivo ya fue realizada por una actividad de tipo **[!UICONTROL Delivery]** (consulte [](delivery.md)), la actividad **[!UICONTROL Act on the delivery]** iniciará los pasos restantes (preparación y envío del contenido).

Estas son las opciones disponibles:

* **[!UICONTROL Generate an outbound transition]**

  Crea una transición saliente que se activará al final de la ejecución. Puede elegir si desea o no recuperar el objetivo de la entrega saliente.

* **[!UICONTROL Processing errors]**

  Consulte [Errores de procesamiento](monitor-workflow-execution.md#processing-errors).

## Parámetros de entrada {#input-parameters}

* deliveryId

  Identificador de envío, si la acción seleccionada es **[!UICONTROL Specified in the transition]**.
