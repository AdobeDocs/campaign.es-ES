---
title: Configuración de la interfaz de Campaign
description: Obtenga información sobre cómo personalizar la configuración de la interfaz de Campaign
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 1c879c7803c346d4b602089a22c2639eb83e82be
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 33%

---

# Configuración de la interfaz de usuario de Campaign {#ui-settings}

## Enumeraciones {#enumerations}

Una enumeración (también conocida como &quot;lista desglosada&quot;) es una lista de valores sugeridos por el sistema para rellenar campos. Utilice las enumeraciones para estandarizar los valores de estos campos, ayudar con la entrada de datos o utilizar dentro de las consultas.

La lista de valores aparece como una lista desplegable desde la que puede seleccionar el valor que se va a introducir en el campo. La lista desplegable también permite la entrada predictiva: introduzca las primeras letras y la aplicación rellenará el resto.

Los valores de este tipo de campo se definen y la administración general de estos campos (adición o eliminación de un valor) se realiza a través del nodo **[!UICONTROL Administration > Platform > Enumerations]** del árbol.

![Enumeraciones de acceso](assets/enumerations-menu.png)

### Tipos de enumeraciones {#types-of-enum}

Las enumeraciones se almacenan en la variable **[!UICONTROL Administration > Platform > Enumerations]** carpeta del explorador.

Pueden ser: Abierto, Sistema, Emoticono o Cerrado.

* Un **Apertura** la enumeración permite a los usuarios añadir nuevos valores directamente en los campos basados en esta enumeración.
* A **Cerrado** la enumeración tiene una lista fija de valores que solo se pueden modificar desde el **[!UICONTROL Administration > Platform > Enumerations]** carpeta del explorador.
* Un **Emoticono** para actualizar la lista de emoticonos. Más información
* A **Sistema** la enumeración está asociada a los campos del sistema y viene con un nombre interno.

Para **Apertura** y **Cerrado** , hay disponibles opciones específicas:

* **Enumeración simple** es el tipo estándar predeterminado.
* **Limpieza de alias** para armonizar los valores de enumeración almacenados en la base de datos. [Más información](#alias-cleansing)
* **Reservado para agrupamiento** es una opción que le permite vincular valores de cubo a esta enumeración. [Más información](../reporting/gs-cubes.md)


### Alias cleansing {#alias-cleansing}

En los campos de enumeración, puede seleccionar un valor o introducir un valor personalizado que no esté disponible en la lista desplegable. Los valores personalizados se pueden agregar a los valores de enumeraciones existentes, como uno nuevo; en este caso, la variable **[!UICONTROL Open]** debe estar seleccionada. Estos valores personalizados se pueden limpiar mediante funciones de limpieza de alias. Por ejemplo, si un usuario introduce `Adob` en lugar de `Adobe`, el proceso de limpieza de alias puede reemplazarlo automáticamente por el término correcto.

>[!CAUTION]
>
>La limpieza de datos es un proceso esencial que afecta a los datos de la base de datos. Adobe Campaign realiza actualizaciones de datos masivas que pueden dar lugar a la eliminación de algunos valores. Por lo tanto, esta operación queda reservada para usuarios expertos.

Active la variable **[!UICONTROL Alias cleansing]** para utilizar las funciones de limpieza de datos de una enumeración. Cuando se selecciona esta opción, la pestaña **[!UICONTROL Alias]** aparece en la parte inferior de la ventana.

Cuando un usuario introduce un valor que no existe en una enumeración de Limpieza de alias, se agrega al **Valores** lista. Puede [crear alias a partir de estos valores](#convert-to-alias)o [crear nuevos alias desde cero](#create-alias).

#### Creación de un alias{#create-alias}

Para crear un alias, siga estos pasos:

1. Haga clic en **[!UICONTROL Add]** del botón **[!UICONTROL Alias]** pestaña .
1. Introduzca el alias que desea convertir y seleccione el valor que se aplicará en la lista desplegable.

   ![Crear un nuevo alias](assets/new-alias.png)

1. Haga clic en **[!UICONTROL Ok]** y confirme.

1. Guarde los cambios. La sustitución de valores se realiza mediante la función **Limpieza de alias** flujo de trabajo que se ejecuta cada noche. Consulte [Ejecución de la limpieza de datos](#running-data-cleansing).

Para todos los campos basados en esta enumeración, cuando un usuario introduce el valor **Adobe** en un campo &quot;empresa&quot; (en la consola de Adobe Campaign, en un formulario web), se sustituye automáticamente por el valor **Adobe**.

#### Convertir un valor incorrecto en un alias{#convert-to-alias}

También puede convertir un valor de enumeración existente en un alias. Para realizar esto:

1. En la lista de valores de una enumeración, haga clic con el botón derecho y busque **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![Convertir un valor en un alias](assets/convert-into-aliases.png)

1. Seleccione los valores que desea convertir en alias y haga clic en **[!UICONTROL Next]**.
1. Haga clic en **[!UICONTROL Start]** para ejecutar la conversión.

   Una vez finalizada la ejecución, se añaden alias a la lista, en la variable **Alias** pestaña . Puede asociar un valor correcto para reemplazar entradas incorrectas. Para realizar esto:

1. Seleccione un valor para limpiar.
1. Haga clic en el **Detalle...** botón.
1. Seleccione el nuevo valor en la lista desplegable.

   ![Crear un nuevo alias](assets/define-new-alias.png)


>[!CAUTION]
>
>Puede realizar un seguimiento de las ocurrencias de un alias en la variable **[!UICONTROL Hits]** en la columna **[!UICONTROL Alias]** subpestaña . Puede mostrar el número de veces que se introdujo este valor.  [Más información](#calculate-entry-occurrences).

#### Ejecución de limpieza de datos {#running-data-cleansing}

La limpieza de datos se realiza mediante el flujo de trabajo técnico **[!UICONTROL Alias cleansing]**. Se ejecuta a diario de forma predeterminada.

La limpieza también se puede activar mediante el **[!UICONTROL Cleanse values...]** vínculo.

El vínculo **[!UICONTROL Advanced parameters...]** permite establecer la fecha de comienzo a partir de la que se tienen en cuenta los valores recopilados.

Haga clic en el botón **[!UICONTROL Start]** para ejecutar la limpieza de datos.

##### Ocurrencias del monitor {#calculate-entry-occurrences}

La variable **[!UICONTROL Alias]** la subpestaña de una enumeración puede mostrar el número de apariciones de un alias entre todos los valores introducidos. Esta información es una estimación y se muestra en la columna **[!UICONTROL Hits]**.

>[!CAUTION]
>
>El cálculo de las apariciones de las entradas de un alias puede llevar mucho tiempo.

Se puede ejecutar el cálculo de visitas manualmente mediante el vínculo **[!UICONTROL Cleanse values...]**. Para ello, haga clic en el botón **[!UICONTROL Advanced parameters...]** vincular y seleccionar opciones.

* **[!UICONTROL Update the number of alias hits]**: esto permite actualizar las visitas que ya se han calculado, en función de la fecha ingresada.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: permite ejecutar el cálculo en toda la plataforma de Adobe Campaign.

Asimismo, se puede crear un flujo de trabajo dedicado para que el cálculo se ejecute automáticamente durante un periodo determinado, por ejemplo, una vez por semana.

Para ello, cree una copia del flujo de trabajo **[!UICONTROL Alias cleansing]**, cambie el planificador y utilice la siguiente configuración en la actividad **[!UICONTROL Enumeration value cleansing]**:

* **-updateHits** para actualizar el número de visitas de alias,
* **-updateHits:full** para volver a calcular todas las visitas de alias.
