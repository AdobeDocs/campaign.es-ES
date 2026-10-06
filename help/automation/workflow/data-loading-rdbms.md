---
product: campaign
title: Carga de datos (RDBMS)
description: Descubra más información sobre la actividad del flujo de trabajo Carga de datos (RDBMS)
feature: Workflows, Data Management Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 2d650573-f630-4aba-bd40-2db88ef1c346
TQID: 'https://experienceleague.adobe.com/3FkutZSFu-yv9yuqmqQoxVrGaEVJrVuErmEC95JbVTM'
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
  - id: 97f7b899-98c8-5133-9446-bfaf99a51b9f
    internal-label: Data Management Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 100%
---
# Carga de datos (RDBMS){#data-loading-rdbms}



La actividad **[!UICONTROL Data loading (RDBMS)]** permite acceder a esta base de datos externa directamente y recopilar solamente los datos necesarios para el objetivo.

Para mejorar el rendimiento, recomendamos utilizar la actividad de consulta (donde se pueden utilizar los datos de una base de datos externa). Para obtener más información, consulte [Acceso a una base de datos externa (FDA)](accessing-an-external-database-fda.md).

La operación es la siguiente:

1. Seleccione el origen de los datos de la lista e introduzca el nombre de la tabla que contiene los datos que se van a extraer.

   ![](assets/s_advuser_wf_sgbd_sample_1.png)

   El nombre de la tabla introducida en el campo correspondiente se utiliza como plantilla para recopilar datos en la base de datos externa. El nombre de la tabla procesada por el flujo de trabajo se puede calcular o transmitir mediante la transición de entrada de la actividad de carga de datos. Para seleccionar la tabla que se va a utilizar, haga clic en **[!UICONTROL Advanced..]**. vínculo y seleccione la opción **[!UICONTROL Specified in the transition]** o **[!UICONTROL Explicit]**.

   ![](assets/s_advuser_wf_sgbd_sample_5.png)

1. Haga clic en el vínculo **[!UICONTROL Select the columns to extract...]** para elegir los datos que se deben recopilar en la base de datos.

   ![](assets/s_advuser_wf_sgbd_sample_2.png)

1. Puede definir un filtro en estos datos. Para ello, haga clic en el vínculo **[!UICONTROL Edit query....]**.

   Los datos recopilados de esta manera se pueden utilizar en todo el ciclo de vida del flujo de trabajo.
