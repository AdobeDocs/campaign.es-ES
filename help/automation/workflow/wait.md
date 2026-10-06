---
product: campaign
title: Espera
description: Descubra más información sobre la actividad del flujo de trabajo Espera
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: a9bcb214-5c87-4b26-804a-22b868905022
TQID: 'https://experienceleague.adobe.com/pCmFiYzA61DTXdDZCO14diygPbfuvZkXIbKVgbtXmQQ'
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 100%
---
# Espera{#wait}



Una actividad **Wait** activa su transición después de un retraso de tiempo de entre unos segundos y varios meses. Una tarea de espera no bloquea la ejecución de otras tareas; el flujo de trabajo puede ejecutar tareas en paralelo mientras esta tarea está pendiente.

Puede introducir la etiqueta y esperar el tiempo utilizando el editor, como en el ejemplo siguiente:

![](assets/edit_wait.png)

En el campo **[!UICONTROL Duration]**, el valor se puede expresar en la unidad que elija: (según la configuración regional del operador):

* Si no se especifica la configuración regional: **s** para segundos, **m** para minutos, **h** para horas, **d** para días, **y** para años. En el momento de la aprobación, el valor se convierte automáticamente en la unidad más legible.

  La unidad predeterminada es el día (**d**).

* Mientras que si, por ejemplo, la configuración regional se establece en &quot;Francés&quot;: **s** para segundos, **mn** para minutos, **h** para horas, **j** para días, **m** para meses, **a** para años. En el momento de la aprobación, el valor se convierte automáticamente a la unidad más legible, como en el ejemplo anterior **90s** se convirtió a **1mn 30s**.

  La unidad predeterminada es el día (**d**).
