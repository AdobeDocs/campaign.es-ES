---
title: Configuración de interfaz de Campaign
description: Aprenda a personalizar la configuración de la interfaz de Campaign
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: 2f7496a0376776d35cf88b0e81365f6e414655fd
workflow-type: tm+mt
source-wordcount: '1848'
ht-degree: 40%

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

En la consola del cliente de Campaign, los datos se muestran en listas. Puede adaptar estas listas a sus necesidades. Por ejemplo, puede agregar columnas, filtrar datos, contar registros, guardar y compartir su configuración.

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




## Trabajo con enumeraciones {#enumerations}

Una enumeración (también conocida como &quot;lista desglosada&quot;) es una lista de valores sugeridos por el sistema para rellenar campos. Utilice enumeraciones para estandarizar los valores de estos campos, ayudar con la entrada de datos o utilizar en las consultas.

La lista de valores aparece como una lista desplegable desde la que puede seleccionar el valor que se va a introducir en el campo. La lista desplegable también permite la entrada predictiva: introduzca las primeras letras y la aplicación rellena el resto.

Los valores de este tipo de campo se definen y la administración general de estos campos (adición o eliminación de un valor) se realiza a través del nodo **[!UICONTROL Administration > Platform > Enumerations]** del árbol.

![Enumeraciones de acceso](assets/enumerations-menu.png)

### Tipos de enumeraciones {#types-of-enum}

Las enumeraciones se almacenan en la carpeta **[!UICONTROL Administration > Platform > Enumerations]** del explorador.

Pueden ser: Abierta, Sistema, Emoticono o Cerrada.

* Una enumeración **Open** permite a los usuarios agregar nuevos valores directamente en los campos basándose en esta enumeración.
* Una enumeración **Closed** tiene una lista fija de valores que sólo pueden modificarse desde la carpeta **[!UICONTROL Administration > Platform > Enumerations]** del explorador.
* Se usa una enumeración **Emoticon** para actualizar la lista de emoticonos. Más información
* Una enumeración **System** está asociada a los campos del sistema y se incluye con un nombre interno.

Hay opciones específicas disponibles para las enumeraciones **Abrir** y **Cerrado**:

* **Enumeración simple** es el tipo estándar predeterminado.
* La enumeración **Limpieza de alias** se usa para armonizar los valores de enumeración almacenados en la base de datos. [Más información](#alias-cleansing)
* **Reservado para el agrupamiento** es una opción que le permite vincular valores de cubo a esta enumeración. [Más información](../reporting/gs-cubes.md)


### Limpieza de alias {#alias-cleansing}

En los campos de enumeración, puede seleccionar un valor o introducir un valor personalizado que no esté disponible en la lista desplegable. Se pueden agregar valores personalizados a los valores de enumeraciones existentes, como uno nuevo: en este caso, se debe seleccionar la opción **[!UICONTROL Open]**. Estos valores personalizados se pueden limpiar con las funciones de limpieza de alias. Por ejemplo, si un usuario introduce `Adob` en lugar de `Adobe`, el proceso de limpieza de alias puede reemplazarlo automáticamente por el término correcto.

>[!CAUTION]
>
>La limpieza de datos es un proceso esencial que afecta a los datos de la base de datos. Adobe Campaign realiza actualizaciones de datos masivas que pueden dar lugar a la eliminación de algunos valores. Por lo tanto, esta operación queda reservada para usuarios expertos.

Habilite la opción **[!UICONTROL Alias cleansing]** para usar las capacidades de limpieza de datos en una enumeración. Cuando se selecciona esta opción, la pestaña **[!UICONTROL Alias]** aparece en la parte inferior de la ventana.

Cuando un usuario introduce un valor que no existe en una enumeración de Limpieza de alias, se agrega a la lista **Valores**. Puede [crear alias a partir de estos valores](#convert-to-alias) o [crear nuevos alias desde cero](#create-alias).

#### Creación de un alias{#create-alias}

Para crear un alias, siga estos pasos:

1. Haga clic en el botón **[!UICONTROL Add]** de la ficha **[!UICONTROL Alias]**.
1. Introduzca el alias que desea convertir y seleccione el valor que se aplicará en la lista desplegable.

   ![Crear un alias nuevo](assets/new-alias.png)

1. Haga clic en **[!UICONTROL Ok]** y confirme.

1. Guarde los cambios. El reemplazo de valores se realiza mediante el flujo de trabajo **Limpieza de alias**, que se ejecuta todas las noches. Consulte [Ejecución de la limpieza de datos](#running-data-cleansing).

Para todos los campos basados en esta enumeración, cuando un usuario introduce el valor **Adobe** en un campo &quot;compañía&quot; (en la consola del cliente de Adobe Campaign, en un formulario web), se reemplazará automáticamente por el valor **Adobe**.

#### Convertir un valor incorrecto en un alias{#convert-to-alias}

También puede convertir un valor de enumeración existente en un alias. Para realizar esto:

1. En la lista de valores de una enumeración, haga clic con el botón secundario y busque **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![Convertir un valor en un alias](assets/convert-into-aliases.png)

1. Seleccione los valores que desea convertir en alias y haga clic en **[!UICONTROL Next]**.
1. Haga clic en **[!UICONTROL Start]** para ejecutar la conversión.

   Una vez finalizada la ejecución, se agregan alias a la lista, en la ficha **Alias**. Puede asociar un valor correcto para reemplazar las entradas incorrectas. Para realizar esto:

1. Seleccione un valor para limpiar.
1. Haga clic en el botón **Detalle...**.
1. Seleccione el nuevo valor en la lista desplegable.

   ![Crear un alias nuevo](assets/define-new-alias.png)


>[!NOTE]
>
>Puede realizar un seguimiento de las apariciones de un alias en la columna **[!UICONTROL Hits]** de la subpestaña **[!UICONTROL Alias]**. Puede mostrar el número de veces que se introdujo este valor.  [Más información](#calculate-entry-occurrences).

#### Ejecución de limpieza de datos {#running-data-cleansing}

La limpieza de datos se realiza mediante el flujo de trabajo técnico **[!UICONTROL Alias cleansing]**. Se ejecuta a diario de forma predeterminada.

La limpieza también se puede activar mediante el vínculo **[!UICONTROL Cleanse values...]**.

El vínculo **[!UICONTROL Advanced parameters...]** permite establecer la fecha de comienzo a partir de la que se tienen en cuenta los valores recopilados.

Haga clic en el botón **[!UICONTROL Start]** para ejecutar la limpieza de datos.

##### Monitorización de ocurrencias {#calculate-entry-occurrences}

La subpestaña **[!UICONTROL Alias]** de una enumeración puede mostrar el número de apariciones de un alias entre todos los valores introducidos. Esta información es una estimación y se muestra en la columna **[!UICONTROL Hits]**.

>[!CAUTION]
>
>El cálculo de las apariciones de las entradas de un alias puede llevar mucho tiempo.
>

Se puede ejecutar el cálculo de visitas manualmente mediante el vínculo **[!UICONTROL Cleanse values...]**. Para ello, haga clic en el vínculo **[!UICONTROL Advanced parameters...]** y seleccione las opciones.

* **[!UICONTROL Update the number of alias hits]**: esto permite actualizar las visitas que ya se han calculado, en función de la fecha ingresada.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: permite ejecutar el cálculo en toda la plataforma de Adobe Campaign.

Asimismo, se puede crear un flujo de trabajo dedicado para que el cálculo se ejecute automáticamente durante un periodo determinado, por ejemplo, una vez por semana.

Para ello, cree una copia del flujo de trabajo **[!UICONTROL Alias cleansing]**, cambie el planificador y utilice la siguiente configuración en la actividad **[!UICONTROL Enumeration value cleansing]**:

* **-updateHits** para actualizar el número de visitas de alias,
* **-updateHits:full** para volver a calcular todas las visitas de alias.
