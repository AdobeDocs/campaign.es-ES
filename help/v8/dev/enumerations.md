---
title: Administración de enumeraciones
description: Aprenda a trabajar con enumeraciones
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: 428de72e0459b95a6db0b06ec8541d0475b72fdd
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 51%

---

# Administración de enumeraciones {#manage-enumerations}

Una enumeración (también denominada lista desglosada) es una lista predefinida de valores que puede utilizar para rellenar determinados campos. Las enumeraciones ayudan a estandarizar los valores de los campos, lo que hace que la entrada de datos sea más coherente y simplifica las consultas.

Cuando están disponibles, los valores aparecen en una lista desplegable. Puede seleccionar un valor directamente o empezar a escribir: la entrada predictiva sugiere valores coincidentes y los completa automáticamente.

![](assets/enum_values.png)

Algunos campos de la consola se configuran con enumeraciones. Si una enumeración es **open**, también puede agregar nuevos valores directamente en el campo.

## Acceso a enumeraciones

Los valores utilizados en estos campos se administran de forma centralizada. Puede agregarlas, editarlas, actualizarlas o eliminarlas del árbol del Explorador, en **Administración** `>` **Plataforma** `>` **Enumeraciones**.

* La sección superior ofrece una lista de campos para los que se ha definido una enumeración.
* La sección inferior enumera los valores disponibles.

Cuando una enumeración es **[!UICONTROL Open]**, los usuarios pueden introducir un nuevo valor directamente en el campo correspondiente de la interfaz de usuario.

Cuando una enumeración es **[!UICONTROL Closed]**, los nuevos valores solo se pueden agregar desde el menú **Enumeración**.

## Añadir un nuevo valor

Para crear un nuevo valor de enumeración, haga clic en el botón **[!UICONTROL Add]**.

![](assets/enumeration_screen.png)

Introduzca la etiqueta del valor.


## Limpieza de alias {#alias-cleansing}

En los campos de enumeración, puede introducir valores que no sean valores de enumeración. Pueden almacenarse tal cual o se puede ejecutar una limpieza.

>[!CAUTION]
>
>La limpieza de datos es un proceso esencial que afecta a los datos de la base de datos. Adobe Campaign realiza actualizaciones de datos masivas que pueden dar lugar a la eliminación de algunos valores. Por lo tanto, esta operación queda reservada para usuarios expertos.

Por tanto, el valor introducido:

* Se agrega a los valores de lista desglosada: en este caso se debe seleccionar la opción **[!UICONTROL Open]**,
* o reemplazado automáticamente por su alias correspondiente: en este caso, este caso debe definirse en la ficha **[!UICONTROL Alias]** de la lista desglosada,
* o se debe almacenar en la lista de alias: se le asigna un alias más adelante.

### Creación de un alias {#creating-an-alias}

La opción **[!UICONTROL Alias cleansing]** permite utilizar un alias para la lista desglosada seleccionada. Cuando se selecciona esta opción, la pestaña **[!UICONTROL Alias]** aparece en la parte inferior de la ventana.

Para crear un alias, siga estos pasos:

1. Examine la enumeración para actualizar y haga clic en **[!UICONTROL Add]**.

   ![](assets/enumeration_alias_create.png)

1. Introduzca el alias que desea convertir y el valor que se va a aplicar y haga clic en **[!UICONTROL Ok]**.

1. Compruebe los parámetros antes de confirmar esta operación.

>[!CAUTION]
>
>Una vez confirmado este paso, es posible que los valores anteriores no se recuperen: se sustituyen.

Por lo tanto, cuando un usuario introduce el valor **NEILSEN** en un campo &quot;compañía&quot; (en la consola de Adobe Campaign o en un formulario), se reemplaza automáticamente por el valor **NIELSEN Ltd**. El flujo de trabajo **Limpieza de alias** realiza el reemplazo del valor. Consulte [Ejecución de la limpieza de datos](#running-data-cleansing).

![](assets/enumeration_alias_use.png)

### Conversión de valores en alias {#values-into-aliases}

Puede convertir los valores existentes en alias. Para ello, siga estos pasos:

1. Haga clic con el botón derecho en la lista de valores y elija **[!UICONTROL Convert values into aliases...]**.

1. Elija los valores que desea convertir y haga clic en **[!UICONTROL Next]**.

1. Haga clic en **[!UICONTROL Start]** para ejecutar la conversión.

Una vez finalizada la ejecución, el alias se añade a la lista de alias.

### Recuperación de visitas de alias {#alias-hits}

Cuando los usuarios escriben valores que no están incluidos en la enumeración, se almacenan en la ficha **[!UICONTROL Alias]**.

El flujo de trabajo técnico **Limpieza de alias** recupera estos valores cada noche para actualizar la enumeración. Consulte [Ejecución de la limpieza de datos](#running-data-cleansing)

Si es necesario, la columna **[!UICONTROL Hits]** puede mostrar el número de veces que se ingresó este valor. Sin embargo, el cálculo de este valor puede consumir tiempo y memoria. Para obtener más información, consulte [Cálculo de ocurrencias de entrada](#calculating-entry-occurrences).

### Ejecución de limpieza de datos {#run-data-cleansing}

La limpieza de datos se realiza mediante el flujo de trabajo técnico **[!UICONTROL Alias cleansing]**. Las configuraciones definidas para las enumeraciones se aplican durante la ejecución. Consulte [Flujo de trabajo de limpieza de alias](#alias-cleansing-workflow).

La limpieza se puede activar mediante el vínculo **[!UICONTROL Cleanse values...]**.

El vínculo **[!UICONTROL Advanced parameters...]** permite establecer la fecha de comienzo a partir de la que se tienen en cuenta los valores recopilados.

Haga clic en el botón **[!UICONTROL Start]** para ejecutar la limpieza de datos.

### Cálculo de las ocurrencias de entrada {#entry-occurrences}

La subpestaña **[!UICONTROL Alias]** de una lista desglosada puede mostrar el número de apariciones de un alias entre todos los valores introducidos. Esta información es una estimación y se muestra en la columna **[!UICONTROL Hits]**.

>[!CAUTION]
>
>El cálculo de las apariciones de las entradas de un alias puede llevar mucho tiempo. Por eso se debe tener precaución al utilizar esta función.

Se puede ejecutar el cálculo de visitas manualmente mediante el vínculo **[!UICONTROL Cleanse values...]**. Para ello, haga clic en el vínculo **[!UICONTROL Advanced parameters...]** y seleccione las opciones deseadas.

* **[!UICONTROL Update the number of alias hits]**: esto permite actualizar las visitas que ya se han calculado, en función de la fecha ingresada.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: permite ejecutar el cálculo en toda la plataforma de Adobe Campaign.

Asimismo, se puede crear un flujo de trabajo dedicado para que el cálculo se ejecute automáticamente durante un periodo determinado, por ejemplo, una vez por semana.

Para ello, cree una copia del flujo de trabajo **[!UICONTROL Alias cleansing]**, cambie el planificador y utilice la siguiente configuración en la actividad **[!UICONTROL Enumeration value cleansing]**:

* **-updateHits** para actualizar el número de visitas de alias,
* **-updateHits:full** para volver a calcular todas las visitas de alias.

### Flujo de trabajo de limpieza de alias {#alias-cleansing-workflow}

El flujo de trabajo de **Limpieza de alias** ejecuta la limpieza de los valores de las enumeraciones. Se ejecuta a diario de forma predeterminada.

Se accede a través del nodo **[!UICONTROL Administration > Production > Technical workflows]**.


