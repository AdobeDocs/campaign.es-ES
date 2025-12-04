---
title: Diseño de consultas en Campaign v8
description: Obtenga información sobre cómo crear consultas en la consola del cliente de Campaign
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: edd495a377559007dad7158c9ab4a4917d89ae73
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 29%

---

# Base de datos de Query Campaign

Las consultas se crean utilizando campos de la tabla seleccionada o utilizando una fórmula.

Los pasos para crear una consulta en Adobe Campaign son los siguientes:

1. [Seleccione la tabla de trabajo](#step-1---choose-a-table).
1. [Seleccione los datos que desea extraer](#step-2---choose-data-to-extract).
1. [Defina el modo de clasificación de datos](#step-3---sort-data).
1. [Definir opciones de filtrado de datos](#step-4---filter-data).
1. [Configurar el formato de datos](#step-5---format-data).
1. [Vista previa de los resultados de la consulta](#step-6---preview-data).

Todos estos pasos están disponibles en [editor de consultas genérico](query-editor.md). Cuando se crea una consulta en otro contexto, pueden faltar algunos pasos. Para obtener más información acerca de las consultas, consulte también la [documentación de la actividad de consulta del flujo de trabajo](../../automation/workflow/query.md).


## Paso 1: Seleccionar una tabla {#step-1---choose-a-table}

Para consultar la base de datos de Campaign, abra **[Generic query editor](query-editor.md)** y seleccione la tabla que contiene los datos que desea consultar en la ventana **[!UICONTROL Document type]**.

![](assets/query_editor_nveau_21.png)

Si es necesario, filtre los datos mediante el campo de filtro o el botón **[!UICONTROL Filters]**.

## Paso 2: Selección de los datos que desea extraer {#step-2---choose-data-to-extract}

En la pantalla **[!UICONTROL Data to extract]**, elija los campos que desea incluir en la salida. Estos campos definen las columnas que se muestran en los resultados.

Por ejemplo, puede seleccionar **[!UICONTROL Age]**, **[!UICONTROL Primary key]**, **[!UICONTROL Email domain]** y **[!UICONTROL City]**. El resultado se estructurará según esta selección. Para ajustar el orden de las columnas, utilice las flechas azules del lado derecho de la ventana.

![](assets/query_editor_nveau_01.png)

Puede modificar una expresión agregando una fórmula o aplicando un proceso a una función de agregado. Para editar una expresión, haga clic en el campo de columna **[!UICONTROL Expression]** y seleccione **[!UICONTROL Edit expression]**.

![](assets/query_editor_nveau_97.png)

Puede agrupar los datos mostrados en las columnas de salida. Para ello, seleccione **[!UICONTROL Yes]** en la columna **[!UICONTROL Group]** de la ventana **[!UICONTROL Data to extract]**. Los resultados se agregarán en función del eje de agrupación seleccionado. Para ver un ejemplo de una consulta que usa agrupación, vea [esta sección](../../automation/workflow/query-delivery-info.md).

![](assets/query_editor_nveau_56.png)

* La opción **[!UICONTROL Handle groupings (GROUP BY + HAVING)]** le permite agrupar resultados y aplicar condiciones a esos grupos. Se aplica a todos los campos de las columnas de salida. Por ejemplo, se puede utilizar para agrupar valores de una columna de salida y luego filtrar los resultados para recuperar únicamente información específica, como los destinatarios de entre 35 y 50 años.

  Para obtener más información, consulte [esta sección](../../automation/workflow/query-grouping-management.md).

La opción **[!UICONTROL Remove duplicate rows (DISTINCT)]** elimina filas idénticas de la salida (deduplicar). Por ejemplo, si selecciona **Apellidos**, **Nombre** y **Correo electrónico** como columnas de salida, cualquier registro con los mismos valores en los tres campos se considerará duplicado. Solo se mantendrá una instancia en los resultados, lo que garantiza que cada contacto aparezca solo una vez.

## Paso 3: Ordenar los datos {#step-3---sort-data}

La ventana **[!UICONTROL Sorting]** permite ordenar el contenido de las columnas. Utilice las flechas para modificar el orden de la columna:

* La columna **[!UICONTROL Sorting]** permite un orden simple y organiza el contenido de la columna de la A a la Z o en orden ascendente.
* **[!UICONTROL Descending sort]** organiza el contenido de la Z a la A y en orden descendente. Esto resulta útil para ver las ventas de registro, por ejemplo: las cifras más altas se muestran en la parte superior de la lista.

En este ejemplo, los datos se ordenan en orden ascendente según la edad del destinatario.

![](assets/query_editor_nveau_57.png)

## Paso 4: Filtrar los datos {#step-4---filter-data}

El editor de consultas permite filtrar los datos para reducir los resultados. Los filtros disponibles dependen de la tabla que esté consultando.

![](assets/query_editor_nveau_09.png)

Después de seleccionar **[!UICONTROL Filtering conditions]**, se abre la sección **[!UICONTROL Target elements]**. Aquí puede definir las reglas para filtrar los datos que se van a recopilar.

* Para crear un nuevo filtro, elija los campos, operadores y valores necesarios para generar la condición. También puede combinar varias condiciones, como se explica [en esta página](filter-conditions.md).

* Para reutilizar un filtro existente, haga clic en el botón **[!UICONTROL Add]**, seleccione **[!UICONTROL Predefined filter]** y elija el filtro que desee.

  ![](assets/query_editor_15.png)

Los filtros creados en **[!UICONTROL Generic query editor]** se pueden reutilizar en otras aplicaciones de consulta, y lo contrario también es verdadero. Para guardar un filtro para usarlo más adelante, haga clic en el icono **[!UICONTROL Save]**.

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

Después de configurar los filtros de restricción, se abre la ventana **[!UICONTROL Data formatting]**. En esta ventana, puede reorganizar las columnas de salida, transformar los datos y ajustar el uso de mayúsculas en las etiquetas de las columnas. También puede aplicar fórmulas al resultado final creando un campo calculado.

>[!NOTE]
>
>Para obtener más información sobre los tipos de campos calculados, consulte [Crear campos calculados](filter-conditions.md#creating-calculated-fields).

Las columnas no seleccionadas están ocultas en la ventana de vista previa de datos.

![](assets/query_editor_nveau_10.png)

La columna **[!UICONTROL Transformation]** permite cambiar una etiqueta de columna a mayúsculas o minúsculas. Seleccione la columna y haga clic en la columna **[!UICONTROL Transformation]**. Puede elegir:

* **[!UICONTROL Switch to lower case]**,
* **[!UICONTROL Switch to upper case]**,
* **[!UICONTROL First letter in upper case]**.

![](assets/query_editor_nveau_42.png)

## Paso 6: Previsualización de datos {#step-6---preview-data}

La ventana **[!UICONTROL Data preview]** marca la etapa final del proceso de consulta. Haga clic en **[!UICONTROL Start the preview of the data]** para revisar los resultados, que pueden mostrarse en columnas o en formato XML. Para examinar la consulta SQL subyacente, abra la ficha **[!UICONTROL Generated SQL queries]**. Este paso le permite verificar que la consulta se comporta como se espera antes de utilizarla más adelante.

En este ejemplo, los datos se ordenan de forma ascendente según la edad del destinatario.

![](assets/query_editor_nveau_11.png)

>[!NOTE]
>
>Como en todas las listas disponibles en la consola, de forma predeterminada, solo se muestran las 200 primeras líneas en la ventana **[!UICONTROL Data preview]**. Para cambiar esto, ingrese un número en el cuadro **[!UICONTROL Lines to display]** y haga clic en **[!UICONTROL Start the preview of the data]**. [Más información](../config/ui-settings.md#manage-and-customize-lists)



**Temas relacionados**

* [Actividad de consulta de flujo de trabajo](../../automation/workflow/query.md)
* [Consulta de la tabla de destinatarios](../../automation/workflow/querying-recipient-table.md)
* [Condiciones de filtrado](filter-conditions.md)