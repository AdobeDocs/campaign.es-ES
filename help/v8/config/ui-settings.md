---
title: Configuración de interfaz de Campaign
description: Aprenda a personalizar la configuración de la interfaz de Campaign
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: fbde111671fb972f6c96ba45eba4c8a88dbcac64
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 47%

---

# Configuración de la interfaz de usuario de Campaign {#ui-settings}

## Unidades predeterminadas {#default-units}

En Adobe Campaign, para los campos que expresan una duración (por ejemplo, un período de validez de los recursos, un plazo de aprobación para una tarea, etc.), los valores se pueden expresar en las siguientes **unidades**:

* **[!UICONTROL s]** para segundos
* **[!UICONTROL mn]** durante minutos
* **[!UICONTROL h]** para horas
* **[!UICONTROL d]** para días

## Personalización del explorador de Campaign{#customize-explorer}

Puede añadir carpetas al explorador de Campaign, crear vistas y asignar permisos.

Obtenga información sobre cómo administrar carpetas y vistas en [esta página](../audiences/folders-and-views.md)

## Administración y personalización de listas {#customize-lists}

En la consola del cliente de Campaign, los datos se muestran en listas. Puede adaptar estas listas a sus necesidades. Por ejemplo, puede añadir columnas, filtrar datos, contar registros, y guardar y compartir su configuración.

Además, puede crear y guardar filtros.  Más información sobre los filtros de [esta página](../audiences/create-filters.md).

### Número de registros {#number-of-records}

De forma predeterminada, Adobe Campaign carga los 200 primeros registros de una lista. Esto significa que la vista no muestra necesariamente todos los registros de la tabla que está viendo. Puede ejecutar un recuento del número de registros en la lista y cargar más registros.

En la parte inferior derecha de la pantalla de la lista, un **counter** muestra cuántos registros se han cargado y la cantidad total de registros en la base de datos (después de aplicar los filtros):

![Mostrar el número total de registros en una lista](assets/number-of-records.png)

Si aparece un signo de interrogación en lugar del número a la derecha, como `240/?`, haga clic en el contador para iniciar el cálculo.

Para cargar y mostrar registros adicionales, haga clic en **[!UICONTROL Continue loading]**. De forma predeterminada, se cargan 200 registros. Para cambiar el número predeterminado de registros que se van a cargar, utilice el icono **[!UICONTROL Configure list]** en la esquina inferior derecha de la lista. En la ventana de configuración de la lista, haga clic en **[!UICONTROL Advanced parameters]** (abajo a la izquierda) y cambie el número de líneas que desea recuperar.

Para cargar todos los registros, haga clic con el botón derecho en la lista y seleccione **[!UICONTROL Load all]**.

>[!CAUTION]
>
>Cuando una lista contiene un gran volumen de registros, la carga completa puede tardar algún tiempo.
>

### Adición y eliminación de columnas {#add-columns}

Para cada lista, la configuración de columna integrada se puede adaptar para mostrar más información u ocultar columnas no utilizadas.

Cuando los datos estén visibles en los detalles de un registro, haga clic con el botón derecho en el campo y seleccione **[!UICONTROL Add in the list]**.

![Agregar un campo en la lista](assets/add-in-the-list.png)

La columna se añade a la derecha de las columnas existentes.

![Agregar una columna de campo](assets/add-a-column.png)

También puede utilizar la pantalla de configuración de la lista para añadir y quitar columnas:

1. En una lista de registros, haga clic en el icono **[!UICONTROL Configure list]** en la sección inferior derecha.
1. Haga doble clic en los campos que desea agregar a la lista **[!UICONTROL Available fields]**: se agregan a la lista **[!UICONTROL Output columns]**.

   ![Pantalla de configuración de lista](assets/list-config-screen.png)


   >[!NOTE]
   >
   >De forma predeterminada, no se muestran los campos avanzados. Para mostrarlos, haga clic en el icono **Mostrar campos avanzados** en la sección inferior derecha de la lista de campos disponibles.
   >
   >Los campos se identifican mediante iconos específicos: Campos SQL, tablas vinculadas, campos calculados, etc. La descripción de cada campo seleccionado se muestra en la lista de campos disponibles.
   >

1. Utilice las flechas arriba/abajo para modificar el **orden de visualización**.

1. Haga clic en **[!UICONTROL OK]** para confirmar la configuración y mostrar el resultado.

Si necesita quitar una columna, selecciónela y haga clic en el icono **Papelera**.

Puede usar el icono **[!UICONTROL Distribution of values]** para ver cómo se reparten los valores del campo seleccionado en la carpeta actual.

![](assets/value-distribution.png)


### Creación de una columna nueva {#create-a-new-column}

Puede crear nuevas columnas para mostrar campos adicionales en la lista.

Para crear una columna, siga estos pasos:

1. En una lista de registros, haga clic en el icono **[!UICONTROL Configure list]** en la sección inferior derecha.
1. Haga clic en el icono **[!UICONTROL Add]** para mostrar un nuevo campo en la lista.
1. Configure el campo que desea añadir en la columna.


### Visualización de datos en subcarpetas {#display-sub-folders-records}

Las listas pueden mostrar:

* Todos los registros contenidos en la carpeta seleccionada (predeterminado)
* Todos los registros contenidos en la carpeta seleccionada y sus subcarpetas

Para cambiar de un modo de visualización a otro, haga clic en **[!UICONTROL Display sub-levels]** en la barra de herramientas de Campaign.

### Cómo guardar una configuración de lista {#saving-a-list-configuration}

Las configuraciones de lista se definen localmente para cada usuario. Cuando se borra la memoria caché local, las configuraciones locales se desactivan.

De forma predeterminada, los parámetros de configuración se aplican a todas las listas con el tipo de carpeta correspondiente. Al modificar la forma en que se muestra la lista de destinatarios desde una carpeta, esta configuración se aplica a todas las demás carpetas de destinatarios.

Puede guardar más de una configuración para aplicarla a diferentes carpetas del mismo tipo. La configuración se guarda con las propiedades de la carpeta que contienen los datos y se puede volver a aplicar.

Para guardar una configuración de lista para que se pueda reutilizar, siga los pasos a continuación:

1. En Explorer, haga clic con el botón derecho en la carpeta que contiene los datos mostrados.
1. Seleccione **[!UICONTROL Properties]**.
1. Haga clic en **[!UICONTROL Advanced settings]** y, a continuación, especifique un nombre en el campo **[!UICONTROL Configuration]**.
1. Haga clic en **[!UICONTROL OK]** y luego en **[!UICONTROL Save]**.

A continuación, puede aplicar esta configuración a cualquier otra carpeta del mismo tipo. Más información sobre las carpetas de [esta página](../audiences/folders-and-views.md).

### Exportación de una lista {#exporting-a-list}

Para exportar datos de una lista, debe utilizar un asistente de exportación. Para acceder a él, seleccione los elementos que desea exportar de la lista, haga clic con el botón derecho del ratón y seleccione **[!UICONTROL Export...]**.

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>Los elementos de una lista no se deben exportar mediante la función Copiar/Pegar.

### Ordenación de una lista {#sorting-a-list}

Las listas pueden contener una gran cantidad de datos. Puede clasificar estos datos o aplicar filtros simples o avanzados. La clasificación le permite mostrar los datos en orden ascendente o descendente. Los filtros permiten definir y combinar criterios para mostrar solo los datos seleccionados.

Haga clic en el encabezado de la columna para aplicar un orden ascendente o descendente, o para cancelar la clasificación de datos. El estado de clasificación activo y el orden de clasificación se indican mediante una flecha azul antes de la etiqueta de columna. Un guion rojo antes de la etiqueta de columna significa que la ordenación se aplica a los datos indexados de la base de datos. Este método de clasificación se utiliza para optimizar los trabajos de ordenación.

También puede configurar la ordenación o combinar criterios de clasificación. Para realizar esto, siga los pasos a continuación:

1. Haga clic en **[!UICONTROL Configure list]** en la parte inferior derecha de la lista.
1. En la ventana de configuración de la lista, haga clic en la pestaña **[!UICONTROL Sorting]**.
1. Seleccione los campos que desea ordenar y la dirección de clasificación (ascendente o descendente).
1. La prioridad de ordenación se define mediante el orden de las columnas de clasificación. Para cambiar la prioridad, utilice los iconos adecuados para cambiar el orden de las columnas.

   La prioridad de ordenación no afecta a la visualización de las columnas de la lista.

1. Haga clic en **[!UICONTROL Ok]** para confirmar esta configuración y mostrar el resultado en la lista.


## Recursos adicionales

* **[Empiece con la interfaz de usuario de Campaign](../start/campaign-ui.md)**. Descubra cómo acceder a la interfaz de Adobe Campaign y explorarla.
* **[Trabajar con enumeraciones](../dev/enumerations.md)**: estandarice los valores de los campos con listas desplegables predefinidas para que la entrada de datos sea más rápida y coherente.
