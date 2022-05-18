---
title: Creación de filtros en Adobe Campaign
description: Obtenga información sobre cómo filtrar los datos y guardar filtros en Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 873578f6-6af9-4d0c-8df3-cce320fc6a4e
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1667'
ht-degree: 33%

---

# Creación y administración de filtros{#create-filters}

El filtrado de datos es el proceso por el que se selecciona una parte menor del conjunto de datos, solo aquellos registros que coinciden con determinados criterios y se utiliza ese subconjunto para acciones específicas (actualizaciones, creación de audiencias) o análisis.

Al explorar la campaña desde el **[!UICONTROL Explorer]**, los datos se muestran en listas. Puede utilizar filtros integrados existentes para acceder a un subconjunto específico de estos datos: direcciones en cuarentena, destinatarios no dirigidos, un intervalo de edad específico o una fecha de creación, por ejemplo.

También puede crear sus propios filtros, guardarlos para usarlos en el futuro o compartirlos con otros usuarios de Campaign.

La configuración del filtro permite seleccionar datos de una lista **[!UICONTROL dynamically]**: cuando se modifican los datos, se actualizan los datos filtrados.

>[!NOTE]
>
>Los ajustes de configuración de la interfaz de usuario se definen localmente en el dispositivo. A veces puede ser necesario limpiar estos datos, especialmente si surgen problemas al actualizarlos. Para ello, utilice el menú **[!UICONTROL File > Clear the local cache]**.

Los siguientes tipos de filtro están disponibles en Adobe Campaign:

## Filtros predefinidos{#predefined-filters}

Los filtros predefinidos están disponibles en el **Filtros** sobre cada lista.

Por ejemplo, para los perfiles, están disponibles los siguientes filtros integrados:

![](assets/built-in-filters.png)

Puede acceder a los detalles de filtros en la **[!UICONTROL Profiles and Targets > Pre-defined filters]** del explorador.

>[!NOTE]
>
>Para las demás listas de datos, los filtros predefinidos se almacenan en la variable  **[!UICONTROL Administration > Configuration > Predefined filters]** nodo .

Seleccione un filtro para mostrar su definición.

![](assets/predefined-filter-list.png)

Utilice la última pestaña para previsualizar los datos filtrados.

![](assets/built-in-filter-preview.png)


Los filtros predefinidos integrados son:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>Consulta</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Abierto<br /> </td> 
   <td> Selecciona los destinatarios que han abierto una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abierto pero sin clic<br /> </td> 
   <td> Selecciona los destinatarios que han abierto una entrega, pero no han hecho clic en un vínculo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatarios inactivos<br /> </td> 
   <td> Selecciona destinatarios que no han abierto una entrega en X meses.<br /> </td> 
  </tr> 
  <tr> 
   <td> Última actividad por tipo de dispositivo<br /> </td> 
   <td> Selecciona los destinatarios que han hecho clic o abierto la entrega Y con el dispositivo X en los últimos Z días.<br /> </td> 
  </tr> 
  <tr> 
   <td> Última actividad por tipo de dispositivo (seguimiento).<br /> </td> 
   <td> Selecciona los destinatarios que han hecho clic o abierto la entrega Y con el dispositivo X en los últimos Z días.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatarios no específicos<br /> </td> 
   <td> Selecciona los destinatarios que nunca se han identificado a través del canal Y en los meses X.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatarios muy activos<br /> </td> 
   <td> Selecciona destinatarios que han hecho clic en una entrega por lo menos X veces en los últimos Y meses.<br /> </td> 
  </tr> 
  <tr> 
 <td> Dirección de correo electrónico incluida en la lista de bloqueados<br /> </td> 
    <td> Selecciona destinatarios cuya dirección de correo electrónico se encuentra en la de lista de bloqueados.<br/> </td>
  </tr> 
  <tr> 
   <td> Dirección de correo en cuarentena<br /> </td> 
   <td> Selecciona destinatarios cuya dirección de correo está en cuarentena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Direcciones de correo duplicadas en la carpeta<br /> </td> 
   <td> Selecciona destinatarios cuya dirección de correo está duplicada en la carpeta.<br /> </td> 
  </tr> 
  <tr> 
   <td> No se ha abierto ni se ha hecho clic<br /> </td> 
   <td> Selecciona los destinatarios que no han abierto ninguna entrega ni han hecho clic en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nuevos destinatarios (días)<br /> </td> 
   <td> Selecciona los destinatarios creados en los últimos X días.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nuevos destinatarios (minutos)<br /> </td> 
   <td> Selecciona los destinatarios creados en los últimos X minutos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nuevos destinatarios (meses)<br /> </td> 
   <td> Selecciona los destinatarios creados en los últimos X meses.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por suscripción<br /> </td> 
   <td> Selecciona los destinatarios por suscripción.<br /> </td> 
  </tr> 
  <tr> 
   <td> Al hacer clic en un vínculo específico<br /> </td> 
   <td> Selecciona los destinatarios que hicieron clic en una URL determinada de una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por comportamiento tras la entrega<br /> </td> 
   <td> Selecciona los destinatarios según su comportamiento tras recibir una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por fecha de creación<br /> </td> 
   <td> Selecciona los destinatarios por fecha de creación, durante un periodo que abarca desde X meses (fecha actual menos n meses) hasta Y meses (fecha actual menos n meses).<br /> </td> 
  </tr> 
  <tr> 
   <td> Por lista<br /> </td> 
   <td> Selecciona los destinatarios por lista.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por número de clics<br /> </td> 
   <td> Selecciona los destinatarios que hicieron clic en una entrega en los últimos X meses.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por número de mensajes recibidos<br /> </td> 
   <td> Selecciona los destinatarios según el número de mensajes recibidos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por número de aperturas<br /> </td> 
   <td> Selecciona los destinatarios que abrieron entre X e Y entregas durante la cantidad de tiempo Z.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por nombre o email<br /> </td> 
   <td> Selecciona los destinatarios según su nombre o correo electrónico.<br /> </td> 
  </tr> 
  <tr> 
   <td> Por intervalo de edad<br /> </td> 
   <td> Selecciona los destinatarios según su edad.<br /> </td> 
  </tr> 
 </tbody> 
</table>


### Filtros predeterminados{#default-filters}

Los campos encima de cada lista permiten utilizar la variable **filtro predeterminado predefinido** para esta lista. Para la lista de destinatarios, puede filtrar por el nombre y la dirección de correo electrónico de forma predeterminada.

![](assets/filter-recipient-name.png)


>[!NOTE]
>
>El carácter **%** sustituye cualquier cadena de caracteres. Por ejemplo, introduzca `%@gmail.com` en el campo Correo electrónico para mostrar todos los perfiles con una dirección de Gmail. Entrar `%@L` en el campo Last name para mostrar todos los perfiles con una L en su apellido.

Para cambiar el filtro predeterminado de una lista de destinatarios, vaya a la **[!UICONTROL Profiles and Targets > Predefined filters]** nodo .

Para el resto de tipos de datos, configure el filtro predeterminado mediante el nodo **[!UICONTROL Administration > Configuration > Predefined filters]**.

Siga estos pasos:

1. Seleccione el filtro que desea utilizar de forma predeterminada.
1. Haga clic en la pestaña **[!UICONTROL Parameters]** y seleccione **[!UICONTROL Default filter for the associated document type]**.

   ![](assets/change-default-filter.png)

1. Desmarque la misma opción para el filtro predefinido actual.
1. Haga clic en **[!UICONTROL Save]** para aplicar el filtro.
1. Vaya a la carpeta Destinatario y haga clic en el botón **[!UICONTROL Remove this filter]** a la derecha del filtro actual: el nuevo filtro predeterminado está disponible.
   ![](assets/updated-default-filter.png)


## Filtros rápidos{#quick-filters}

Uso y combinación **Filtros rápidos** para definir filtros en campos específicos.

Una vez añadidos, los campos de filtro rápido se muestran encima de la lista de datos, uno tras otro. Pueden eliminarse de forma independiente.

Los filtros rápidos son específicos de cada operador y se reinician cada vez que el operador borra la caché de su consola de cliente.

Si necesita reutilizar un filtro, cree un **filtro avanzado** y guárdelo. [Más información](#advanced-filters).

Para crear un **filtro rápido**, siga los pasos:

1. Haga clic con el botón derecho en el campo que desee filtrar y seleccione **[!UICONTROL Filter on this field]**.

   ![](assets/quick-filter-on-this-field.png)

   Los campos de filtro predeterminados se muestran encima de la lista.

   ![](assets/quick-filter-above-list.png)

1. Seleccione las opciones de filtro.
1. Si es necesario, utilice el icono gris en el lado derecho de un filtro para eliminarlo.
1. Puede combinar filtros para restringir el filtro.

   ![](assets/add-filter-above-the-list.png)


Si necesita filtrar en un campo que no está disponible en el formulario, en las columnas y filtrar en esa columna. Para ello,

1. Haga clic en el icono **[!UICONTROL Configure list]**.

   ![](assets/configure-list.png)

1. Seleccione la columna que desea mostrar, por ejemplo, la edad de los destinatarios, y haga clic en **Ok**.

   ![](assets/add-age-column.png)

1. Haga clic con el botón derecho en la columna **Age** de la lista de destinatarios y seleccione **[!UICONTROL Filter on this column]**.

   ![](assets/age-filter-on-this-column.png)

   A continuación, puede seleccionar las opciones de filtrado de edad. Agregue otro filtro a la edad para definir un intervalo.

   ![](assets/filter-on-age.png)

## Filtros avanzados{#advanced-filters}

Combinación de criterios complejos en **Filtros avanzados**. Utilice estos filtros para crear una consulta compleja o una combinación de consultas sobre los datos. Estos filtros se pueden guardar y compartir con otros usuarios de Campaign.

### Creación de un filtro avanzado{#create-adv-filters}

Para crear un **filtro avanzado**, haga clic en **[!UICONTROL Filters]** y seleccione **[!UICONTROL Advanced filter...]**.

![](assets/adv-filter.png)

También puede hacer clic con el botón derecho del ratón en la lista de datos y seleccionar **[!UICONTROL Advanced filter...]**.

Defina las condiciones de filtrado. En el siguiente ejemplo, se filtrarán los destinatarios cuyo número de cuenta no empiece por NL y que residan en París o Los Ángeles.

1. Haga clic en el **[!UICONTROL Edit expression]** del **[!UICONTROL Expression]** para abrir el Navegador.

   ![](assets/edit-exp.png)

1. Seleccione el campo para filtrar.
1. Seleccione el operador que se aplicará en la lista desplegable.

   ![](assets/select-operator.png)

1. Seleccione un valor esperado de la columna **[!UICONTROL Value]**. Puede combinar varios filtros para restringir la consulta. Para añadir una condición de filtro, haga clic en **[!UICONTROL Add]**.

   ![](assets/add-an-exp.png)

   >[!NOTE]
   >
   >Puede asignar una jerarquía a las expresiones o cambiar el orden de las expresiones de consulta mediante las flechas de la barra de herramientas.

1. Hay tres operadores disponibles para combinar expresiones:  **Y**, **O**, **Except**. Haga clic en la flecha para cambiar a **O**.

   ![](assets/select-or-operator.png)

1. Haga clic en **[!UICONTROL Ok]** para crear el filtro y aplicarlo a la lista actual.

El filtro aplicado se muestra encima de la lista.

![](assets/adv-filter-link.png)

Para editar o modificar este filtro, haga clic en su vínculo de descripción en azul, encima de la lista.


### Guardar un filtro avanzado{#save-adv-filters}

Puede guardar un filtro avanzado como un  [filtro predefinido](#predefined-filters), para poder reutilizarla y compartirla con los demás usuarios de Campaign.

Para guardar un filtro avanzado, siga los pasos a continuación:

1. Haga clic en la descripción del filtro para editarlo.
1. Haga clic en el **[!UICONTROL Save as filter]** en la sección superior derecha de la ventana.

   ![](assets/save-as-filter.png)

1. Introduzca un nombre para este filtro y guárdelo.

   ![](assets/application-filter-save.png)

El filtro se agrega al [filtros predefinidos](#predefined-filters). Se puede actualizar desde este nodo.

![](assets/added-to-predefined-filters.png)

>[!NOTE]
>
>Puede añadir un acceso directo para el filtro para activarlo desde el teclado.



Este filtro también está disponible en los filtros predefinidos de la lista de destinatarios.

![](assets/access-to-new-predefined-filter.png)



### Utilizar un filtro para definir un segmento {#filter-as-segment}

Puede usar y combinar filtros para crear un segmento de población objetivo.

Una vez guardados, los filtros avanzados están disponibles al seleccionar la población objetivo de un mensaje, en la **[!UICONTROL User filters]** para obtener más información.

![](assets/adv-filter-target-type.png)


>[!NOTE]
>
>Utilice la variable **[!UICONTROL Exclude recipients from this segment]** para dirigirse solo a los contactos que no coincidan con los criterios del filtro.


### Uso de funciones para crear filtros avanzados{#use-functions-adv-filters}

Para realizar funciones de filtrado avanzadas, utilice funciones para definir el contenido del filtro. El editor de filtros avanzado aprovecha todas las capacidades del editor de consultas de Campaign.

Aprenda a crear consultas avanzadas en la documentación de Adobe Campaign Classic v7. Por ejemplo:

* Obtenga información sobre cómo dirigirse a atributos de destinatarios simples en [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html?lang=en#example--targeting-on-simple-recipient-attributes){target=&quot;_blank&quot;}.
* Obtenga información sobre cómo filtrar por destinatarios no contactados durante los últimos 7 días en [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html){target=&quot;_blank&quot;}.
* Obtenga información sobre cómo recuperar la lista de operadores que se puede filtrar con cuentas activas en [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/creating-a-filter.html){target=&quot;_blank&quot;}.
* Obtenga información sobre cómo crear una audiencia de correo electrónico de cumpleaños en  [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=en#identifying-recipients-whose-birthday-it-is){target=&quot;_blank&quot;}.


### Parámetros avanzados para filtros predefinidos {#param-for-data-filters}

Los parámetros avanzados están disponibles para los filtros predefinidos. Para acceder a ellas, vaya a la **[!UICONTROL Parameters]** del filtro.

* Para mostrar el filtro de forma predeterminada para todas las listas basadas en este tipo de documento, seleccione la opción **[!UICONTROL Default filter for the associated document type]** .

   Por ejemplo, la variable **[!UICONTROL By name or login]** filtro se aplica a los operadores Esta opción está seleccionada, por lo que el filtro siempre se muestra en todas las listas de operadores.

* Para que un filtro esté disponible para todos los operadores de campaña, seleccione la opción  **[!UICONTROL Filter shared with other operators]** .

* Para definir un formulario para seleccionar los criterios de filtrado, seleccione la  **[!UICONTROL Use parameter entry form]** . Este formulario debe introducirse en formato XML en la variable **[!UICONTROL Form]** pestaña . Por ejemplo, el filtro predefinido integrado **[!UICONTROL Recipients who have opened]**, disponible en la lista de destinatarios, muestra un campo de filtro que le permite seleccionar la entrega a la que se aplica el filtro.

![](assets/predefined-filters-parameters.png)


* El vínculo **[!UICONTROL Advanced parameters]** permite definir ajustes adicionales.

   * Puede asociar una tabla SQL con el filtro para que sea común a todos los editores que compartan la tabla.
   * Para evitar que cualquier usuario anule el filtro, seleccione la opción **[!UICONTROL Do not restrict the filter]** . Por ejemplo, esta opción está activa para los filtros &quot;Destinatarios de una entrega&quot; y &quot;Destinatarios de entregas pertenecientes a una carpeta&quot; que están disponibles en el asistente de entregas. Estos filtros no se pueden sobrecargar.
