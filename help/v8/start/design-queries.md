---
title: Diseño de consultas en Campaign v8
description: Obtenga información sobre cómo crear consultas
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: 56d5628312ea3dedf9335dd0933811e4bf66eb97
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 85%

---

# Base de datos de Query Campaign

Las consultas se crean utilizando campos de la tabla seleccionada o utilizando una fórmula.

Los pasos para crear una consulta en Adobe Campaign son los siguientes:

1. Seleccione la tabla de trabajo. Consulte [Paso 1: Elija una tabla](#step-1---choose-a-table).
1. Seleccionar los datos que desea extraer. Consulte [Paso 2: Selección de los datos que desea extraer &#x200B;](#step-2---choose-data-to-extract).
1. Definir la secuencia de ordenación de datos. Consulte [Paso 3: Ordenar datos](#step-3---sort-data).
1. Filtrar los datos. Consulte [Paso 4: Filtrar datos](#step-4---filter-data).
1. Formatear los datos. Consulte [Paso 5: Formato de datos](#step-5---format-data).
1. Mostrar el resultado. Consulte [Paso 6: Vista previa de datos](#step-6---preview-data).

>[!NOTE]
>
>* Todos estos pasos están disponibles en [editor de consultas genérico](query-editor.md). Cuando se crea una consulta en otro contexto, se pueden obviar algunos pasos.
>
>* Para obtener más información sobre las consultas y cómo crearlas, consulte la [documentación del flujo de trabajo de Campaign](../../automation/workflow/query.md).

Para consultar la base de datos de Campaign, abra **[Generic query editor](query-editor.md)** y siga estos pasos:

## Paso 1: Seleccionar una tabla {#step-1---choose-a-table}

Seleccione la tabla que contiene los datos que desea consultar en la ventana **[!UICONTROL Document type]**. Si es necesario, filtre los datos mediante el campo de filtro o el botón **[!UICONTROL Filters]**.

![](assets/query_editor_nveau_21.png)

## Paso 2: Selección de los datos que desea extraer {#step-2---choose-data-to-extract}

En la ventana **[!UICONTROL Data to extract]**, seleccione los datos que desea mostrar: estos campos conforman las columnas de salida.

Por ejemplo, seleccione **[!UICONTROL Age]**, **[!UICONTROL Primary key]**, **[!UICONTROL Email domain]** y **[!UICONTROL City]**. Los resultados se organizan en función de esta selección. Utilice las flechas azules a la derecha de la ventana para cambiar el orden de las columnas.

![](assets/query_editor_nveau_01.png)

Puede editar una expresión insertando una fórmula en ella o ejecutando un proceso en una función de acumulación. Para ello, haga clic en el campo de columna **[!UICONTROL Expression]** y seleccione **[!UICONTROL Edit expression]**.

![](assets/query_editor_nveau_97.png)

Puede agrupar datos de columnas de salida: para ello, marque **[!UICONTROL Yes]** en la columna **[!UICONTROL Group]** de la ventana **[!UICONTROL Data to extract]**. Esta función genera un resultado en torno al eje de agrupación activado. En [esta sección](../../automation/workflow/query-delivery-info.md) puede consultar un ejemplo de consulta con agrupación.

![](assets/query_editor_nveau_56.png)

* La función **[!UICONTROL Handle groupings (GROUP BY + HAVING)]** permite &quot;agrupar por&quot; y seleccionar lo que se ha agrupado. Esta función se aplica a todos los campos de la columna de salida. Por ejemplo, esta opción permite agrupar todas las opciones de una columna de salida y recuperar un tipo específico de información, como los destinatarios entre 35 y 50.

  Para obtener más información, consulte [esta sección](../../automation/workflow/query-grouping-management.md).

* La función **[!UICONTROL Remove duplicate rows (DISTINCT)]** permite deduplicar resultados idénticos obtenidos en la columna de salida. Por ejemplo, si realiza un censo seleccionando los campos Apellido, Nombre y Correo electrónico en la columna de salida, se eliminan los que tengan datos idénticos, ya que esto significa que el mismo contacto se ha introducido varias veces en la base de datos: solo se tiene en cuenta un resultado.

## Paso 3: Ordenar los datos {#step-3---sort-data}

La ventana **[!UICONTROL Sorting]** permite ordenar el contenido de las columnas. Utilice las flechas para modificar el orden de la columna:

* La columna **[!UICONTROL Sorting]** permite un orden simple y organiza el contenido de la columna de la A a la Z o en orden ascendente.
* **[!UICONTROL Descending sort]** organiza el contenido de la Z a la A y en orden descendente. Esto resulta útil para ver las ventas de registro, por ejemplo: las cifras más altas se muestran en la parte superior de la lista.

En este ejemplo, los datos se ordenan en orden ascendente según la edad del destinatario.

![](assets/query_editor_nveau_57.png)

## Paso 4: Filtrar los datos {#step-4---filter-data}

El editor de consultas permite filtrar los datos para restringir la búsqueda.

Los filtros ofrecidos dependen de la tabla en la que se encuentre la consulta.

![](assets/query_editor_nveau_09.png)

Una vez seleccionadas las **[!UICONTROL Filtering conditions]**, puede acceder a la sección **[!UICONTROL Target elements]**: esto permite definir cómo desea filtrar los datos que se recopilen.

* Para crear un nuevo filtro, seleccione los campos, operadores y valores necesarios para la creación de la fórmula que se debe comprobar para seleccionar los datos. También puede combinar varias condiciones como se detalla [en esta página](filter-conditions.md).
* Para utilizar filtros guardados anteriormente, abra la lista desplegable haciendo clic en el botón **[!UICONTROL Add]**, luego en **[!UICONTROL Predefined filter]** y luego seleccione el que desee.

  ![](assets/query_editor_15.png)

* Los filtros creados en el **[!UICONTROL Generic query editor]** están disponibles en otras aplicaciones de consulta y viceversa. Para guardar un filtro, haga clic en el icono **[!UICONTROL Save]**.

  >[!NOTE]
  >
  >Para obtener más información sobre la creación y el uso de los filtros, consulte [Filtrado de opciones](filter-conditions.md).

Como se muestra en el ejemplo siguiente, para recuperar todos los destinatarios de habla inglesa, seleccione: &quot;idioma del destinatario **igual a** EN&quot;.

![](assets/query_editor_nveau_89.png)

>[!NOTE]
>
>Puede acceder directamente a una opción escribiendo la siguiente fórmula en el campo **Valor**: **$(opciones:OPTION_NAME)**.

Haga clic en la pestaña **[!UICONTROL Preview]** para ver el resultado de la condición de filtrado. En este caso, todos los destinatarios de habla inglesa se muestran con su nombre, nombre de pila y dirección de correo electrónico.

![](assets/query_editor_nveau_98.png)

Los usuarios familiarizados con el lenguaje SQL pueden hacer clic en **[!UICONTROL Generate SQL query]** para ver la consulta en SQL.

![](assets/query_editor_nveau_99.png)

## Paso 5: Formato de datos {#step-5---format-data}

Una vez configurados los filtros de restricción, se muestra la ventana **[!UICONTROL Data formatting]**. Esta ventana permite reorganizar las columnas de salida, transformar los datos y cambiar las mayúsculas y minúsculas de las etiquetas de columna. También permite aplicar una fórmula al resultado final mediante un campo calculado.

>[!NOTE]
>
>Para obtener más información sobre los tipos de campos calculados, consulte [Crear campos calculados](filter-conditions.md#creating-calculated-fields).

Las columnas no seleccionadas no se muestran en la ventana de previsualización de datos.

![](assets/query_editor_nveau_10.png)

La columna **[!UICONTROL Transformation]** permite cambiar una etiqueta de columna a mayúsculas o minúsculas. Seleccione la columna y haga clic en la columna **[!UICONTROL Transformation]**. Puede elegir:

* **[!UICONTROL Switch to lower case]**,
* **[!UICONTROL Switch to upper case]**,
* **[!UICONTROL First letter in upper case]**.

![](assets/query_editor_nveau_42.png)

## Paso 6: Previsualización de datos {#step-6---preview-data}

La ventana **[!UICONTROL Data preview]** es el último paso. Haga clic en **[!UICONTROL Start the preview of the data]** para obtener el resultado de la consulta. Está disponible en columnas o en formato XML. Haga clic en la pestaña **[!UICONTROL Generated SQL queries]** para ver la consulta en formato SQL.

En este ejemplo, los datos se ordenan de forma ascendente según la edad del destinatario.

![](assets/query_editor_nveau_11.png)

>[!NOTE]
>
>De forma predeterminada, solo se muestran las 200 primeras líneas en la ventana **[!UICONTROL Data preview]**. Para cambiar esto, introduzca un número en el cuadro **[!UICONTROL Lines to display]** y haga clic en **[!UICONTROL Start the preview of the data]**.



**Temas relacionados**

* [Actividad de consulta de flujo de trabajo](../../automation/workflow/query.md)
* [Consulta de la tabla de destinatarios](../../automation/workflow/querying-recipient-table.md)
* [Condiciones de filtrado](filter-conditions.md)