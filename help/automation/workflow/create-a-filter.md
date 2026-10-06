---
product: campaign
title: Creación de un filtro
description: Aprenda a crear un filtro al realizar consultas
feature: Query Editor, Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8e6fd9b4-77c4-4af8-921b-c3fe104fa5bc
TQID: 'https://experienceleague.adobe.com/3EkEMTJs1-sdM9wSTYorHWO-emO3Nz5nugrWDU4h5pM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
    internal-label: Query Editor
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 77%
---
# Creación de un filtro {#creating-a-filter}

Los filtros disponibles en Adobe Campaign se definen mediante condiciones de filtrado que se crean con el mismo modo de funcionamiento que al crear consultas en [Query editor](../../v8/start/query-editor.md).

El nodo **[!UICONTROL Administration > Configuration > Predefined filters]** contiene todos los filtros predeterminados. Algunos de ellos se utilizan en listas y vistas generales. Más información sobre [filtros predefinidos integrados](../../v8/audiences/create-filters.md).

Por ejemplo, la lista de operadores puede filtrarse con **[!UICONTROL Active accounts]**:

![](assets/query_editor_filter_sample_1.png)

El filtro coincidente contiene la consulta en el valor **[!UICONTROL Account disabled]** del esquema **[!UICONTROL Operators]**:

![](assets/query_editor_filter_sample_2.png)

En la misma lista, el filtro **[!UICONTROL By login or label]** permite filtrar los datos de la lista en función del valor introducido en el campo de filtro:

![](assets/query_editor_filter_sample_3.png)

Se crea de la siguiente manera:

![](assets/query_editor_filter_sample_4.png)

Para hacer coincidir las condiciones de filtrado, la cuenta de operador debe comprobar una de las siguientes condiciones:

* Su etiqueta contiene los caracteres introducidos en el campo de entrada,
* El nombre del operador contiene los caracteres introducidos en el campo de entrada,
* El contenido del área de descripción contiene los caracteres introducidos en el campo de entrada.

>[!NOTE]
>
>La función **[!UICONTROL Upper]** permite desactivar la función que distingue entre mayúsculas y minúsculas.

La columna **[!UICONTROL Taken into account if]** permite definir los criterios de aplicación para estas condiciones de filtrado. En este caso, los caracteres **$(/tmp/@text)** representan el contenido del campo de entrada vinculado al filtro:

![](assets/query_editor_filter_sample_5.png)

Aquí, **$(/tmp/@text)=&#39;agency&#39;**

La expresión **$(/tmp/@text)!=&#39;&#39;** aplica cada condición cuando el campo de entrada no está vacío.
