---
product: campaign
title: Extracción de datos (archivo)
description: Descubra más información sobre la actividad del flujo de trabajo Extracción de datos (archivo).
feature: Workflows, Data Management Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8510e879-2862-491f-bc52-ca8f56105932
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 100%

---

# Extracción de datos (archivo){#extraction-file}

Puede extraer datos de una tabla de flujo de trabajo en un archivo externo mediante la actividad **[!UICONTROL Data extraction (file)]**.

>[!CAUTION]
>
>Esta actividad siempre debe tener una transición entrante que contenga los datos que se extraerán.

Para configurar la extracción de datos, siga estos pasos:

1. Especifique el nombre del archivo de salida: este nombre puede contener variables insertadas mediante el botón de personalización a la derecha del campo.
1. Haga clic en **[!UICONTROL Edit the file format...]** para seleccionar los datos que desea extraer.

   ![](assets/s_advuser_extract_file_param.png)

   La opción **[!UICONTROL Handle groupings (GROUP BY + HAVING)]** añade un paso adicional para filtrar el resultado final del acumulado, por ejemplo, en un tipo de orden de compra determinado, clientes que hayan hecho una orden más de 10 veces, etc.

1. Si es necesario, puede añadir nuevas columnas al archivo de salida, como, por ejemplo, calcular o procesar resultados. Para hacer esto, haga clic en el icono **[!UICONTROL Add]**.

   ![](assets/s_advuser_extract_file_add_col.png)

   En la línea adicional, haga clic en el icono **[!UICONTROL Edit expression]** para definir el contenido de la nueva columna.

   ![](assets/s_advuser_extract_file_add_exp.png)

   A continuación, tendrá acceso a la ventana de selección. Haga clic **[!UICONTROL Advanced selection]** para elegir el proceso que se aplicará a los datos.

   ![](assets/s_advuser_extract_file_advanced_selection.png)

   Elija la fórmula deseada de la lista.

   ![](assets/s_advuser_extract_file_agregate_values.png)

Puede definir un proceso posterior que se va a ejecutar durante la extracción de datos, permitiéndole comprimir o cifrar los archivos. Para ello, se debe agregar el comando deseado en la pestaña **[!UICONTROL Script]** de la actividad.

![](assets/postprocessing_dataextraction.png)

## Lista de funciones acumuladas {#list-of-aggregate-functions}

A continuación, se muestra una lista de funciones acumuladas disponibles:

* **[!UICONTROL Count]** para contar todos los valores no nulos del campo que se van a acumular, incluidos los valores duplicados (del campo acumulado).

  **[!UICONTROL Distinct]** para contar el número total de valores diferentes y no nulos del campo acumulado (los valores duplicados se excluyen antes del cálculo).

* **[!UICONTROL Sum]** para calcular la suma de los valores de un campo numérico.
* **[!UICONTROL Minimum value]** para calcular los valores mínimos de un campo (numérico o de otro tipo),
* **[!UICONTROL Maximum value]** para calcular los valores máximos de un campo (numérico o de otro tipo),
* **[!UICONTROL Average]** para calcular el promedio de los valores de un campo numérico,
