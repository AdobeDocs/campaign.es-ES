---
product: campaign
title: Bifurcación (Fork)
description: Descubra más información sobre la actividad del flujo de trabajo Bifurcación (fork)
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 7b94776c-2478-4e12-82a6-c94be12e7e22
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 100%

---

# Bifurcación{#fork}



Puede utilizar la actividad **[!UICONTROL Fork]** para crear varias transiciones salientes y ejecutar varias actividades de forma independiente dentro del mismo flujo de trabajo.

>[!IMPORTANT]
>
>Las transiciones salientes que añada después de una actividad **[!UICONTROL Fork]** no se ejecutan simultáneamente. Este comportamiento puede afectar al rendimiento del flujo de trabajo. Utilice la actividad **[!UICONTROL Fork]** si necesita ejecutar varias actividades de forma independiente. De forma opcional, puede unirse a las actividades salientes antes de la parte posterior del flujo de trabajo.

Para configurar la actividad **[!UICONTROL Fork]** y sus actividades relacionadas, siga estos pasos:

1. Abra la actividad **[!UICONTROL Fork]** y defina el nombre y la etiqueta de las transiciones salientes.

   ![](assets/s_user_segmentation_fork.png)

1. Abra cada transición saliente y configúrela.
1. De forma opcional, para unirse a las transiciones salientes, añada una actividad AND-join. [Más información](and-join.md).

   La parte posterior del flujo de trabajo se ejecuta únicamente al completarse las transiciones salientes unidas.

## Ejemplo: segmentación

En este ejemplo, se envían distintos correos electrónicos a diferentes grupos de población. Después de una consulta se utiliza una actividad **[!UICONTROL Fork]** para realizar dos acciones en paralelo:

* Guardado del resultado de la consulta
* Segmentación del resultado para enviar varias entregas

  ![La actividad de bifurcación sigue la intersección de dos consultas y precede a una actividad de actualización de lista y una actividad de división.](assets/wkf_fork_example.png)

El flujo de trabajo incluye estas actividades:

1. Actividad de **[!UICONTROL Query]**

   Se seleccionan dos grupos de población: mujeres y parisinos.

1. Actividad de **[!UICONTROL Intersection]**

   Se selecciona la intersección de los resultados de la consulta, es decir, mujeres parisinas.

1. Actividad de **[!UICONTROL Fork]**

   La población calculada se guarda y, en paralelo, se segmenta en dos grupos:

   1. Mujeres parisinas de entre 18 y 40 años
   1. Mujeres parisinas mayores de 40 años

1. Actividad de **[!UICONTROL Delivery]**

   Se envía un correo electrónico diferente a cada grupo de población.

## Caso de uso: enviar un correo electrónico de cumpleaños

Se envía un correo electrónico recurrente a una lista de destinatarios en su cumpleaños. Se utiliza una actividad **[!UICONTROL Fork]** para incluir destinatarios nacidos el 29 de febrero de un año bisiesto. [Obtenga más información](send-a-birthday-email.md) acerca de este caso de uso.

![La actividad de bifurcación sigue a una actividad de prueba y precede a dos actividades de consulta.](assets/birthday-workflow_usecase_1.png)

## Caso de uso: automatizar contenido con un flujo de trabajo


A continuación, puede configurar cada transición de salida y, luego, unirlas mediante una actividad [AND-join](and-join.md) si es necesario. De este modo, el resto del flujo de trabajo se ejecutará solo cuando finalicen las transacciones salientes de la actividad **[!UICONTROL Fork]**.

## Temas relacionados

* [Actividad AND-join](and-join.md)
* [Caso de uso: correo electrónico de cumpleaños](send-a-birthday-email.md)
