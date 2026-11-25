---
product: campaign
title: Respuestas de formularios web
description: Respuestas de formularios web
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 5d48bb27-1884-47f1-acb7-dff5113565bc
TQID: 'https://experienceleague.adobe.com/WPVKOgF2ilspLhbrTd-s6x8MEX254boeoSzJsgZVaTE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 76%
---
# Respuestas de formularios web{#web-forms-answers}


## Campos de almacenamiento de respuestas {#response-storage-fields}

Las respuestas a los formularios se pueden guardar en un campo de la base de datos o temporalmente en una variable local. El modo de almacenamiento de las respuestas se elige durante la creación del campo. Se puede editar mediante el vínculo **[!UICONTROL Edit storage...]**.

Para cada campo de entrada de un formulario, están disponibles las siguientes opciones de almacenamiento:

![Campo de entrada Apellidos con el vínculo Editar almacenamiento y el cuadro de diálogo Almacenamiento que muestra las opciones Editar un destinatario y Variable.](assets/s_ncs_admin_survey_select_storage.png)

* **[!UICONTROL Edit a recipient]**

  Se puede seleccionar un campo de la base de datos: las respuestas de los usuarios se almacenan en este campo. Para cada usuario, solo se guarda el último valor introducido: se añade a su perfil. Consulte [Almacenamiento de datos en la base de datos](#storing-data-in-the-database).

* **[!UICONTROL Variable]**

  Si no desea almacenar información en la base de datos, puede utilizar una variable. Las variables locales se pueden declarar en sentido ascendente. Consulte [Almacenamiento de datos en una variable local &#x200B;](#storing-data-in-a-local-variable).

### Almacenamiento de información en la base de datos {#storing-data-in-the-database}

Para guardar la información en un campo existente de la base de datos, haga clic en el icono **[!UICONTROL Edit expression]** y selecciónela en la lista de campos disponibles.

![Cuadro de diálogo de almacenamiento con la expresión Edit que abre el selector de campo, donde Apellido (@lastName) está seleccionado.](assets/s_ncs_admin_survey_storage_type1.png)

>[!NOTE]
>
>El documento de referencia predeterminado es el esquema **nms:recipient**. Para verla o elegir una nuevo, seleccione el formulario en la lista y haga clic en el botón **[!UICONTROL Properties]**.

### Almacenamiento de datos en una variable local {#storing-data-in-a-local-variable}

Puede utilizar variables locales para que, aun cuando los datos no estén almacenados en la base de datos, se puedan reutilizar en la página o en otras páginas, por ejemplo, para colocar condiciones en la visualización de un campo o para personalizar un mensaje.

Esto significa que se puede utilizar el valor de un campo sin guardar para autorizar la visualización de un grupo de opciones en la página. En la página siguiente, el tipo de vehículo no se almacena en la base de datos:

![Tipo de cuadro combinado de coche con el almacenamiento establecido en la variable typeV y el vínculo Editar almacenamiento.](assets/s_ncs_admin_survey_no_storage_variable.png)

Se almacena en una variable que se debe seleccionar cuando se crea la casilla desplegable o a través del vínculo **[!UICONTROL Edit storage...]**.

![Cuadro de diálogo de almacenamiento con la opción Variable y un listado desplegable Tipo de automóvil, Camión móvil y Vehículo personal.](assets/s_ncs_admin_survey_no_storage_variable2.png)

Puede mostrar las variables existentes y crear variables nuevas mediante el vínculo **[!UICONTROL Edit variables...]**. Haga clic en el botón **[!UICONTROL Add]** para crear una variable nueva.

![Editar lista de variables y cuadro de diálogo Variable con la etiqueta Energía del automóvil y el nombre, escriba Texto para agregar una variable.](assets/s_ncs_admin_survey_add_a_variable.png)

La variable añadida está disponible en la lista de variables locales cuando se crean los campos de entrada de la página.

>[!NOTE]
>
>Para cada formulario, se pueden crear variables de subida. Para ello, seleccione el formulario y haga clic en el botón **[!UICONTROL Properties]**. La pestaña **[!UICONTROL Variables]** contiene las variables locales del formulario.

**Ejemplo de almacenamiento local con condicionamiento**

En el ejemplo anterior, el contenedor que incluye los datos sobre los vehículos privados solo se muestra si la opción **[!UICONTROL Private]** está seleccionada en la lista desplegable, como se indica en la condición de visibilidad:

![Condición de visibilidad del contenedor de coche personal: tipo de coche igual a Personal.](assets/s_ncs_admin_survey_add_a_condition.png)

Si el usuario selecciona un vehículo privado, el formulario web ofrece las siguientes opciones:

![Página de formulario de reserva de vehículo que muestra la lista desplegable Tipo de vehículo con Seleccionar, Compacto, Intermedio y Estándar.](assets/s_ncs_admin_survey_no_storage_conda.png)

El contenedor que contiene los datos sobre los vehículos comerciales se muestra si se selecciona la opción Profesional, tal como expresa la condición de visibilidad:

![Condición de visibilidad del contenedor de camión/furgoneta: el origen es igual al del camión.](assets/s_ncs_admin_survey_view_a_condition.png)

Esto significa que, si el usuario selecciona un vehículo comercial, el formulario ofrece las siguientes opciones:

![Formulario de reserva de auto con camioneta en movimiento seleccionada y una lista desplegable de Clase Minibus, Recogida, Camioneta de carga y Camión 20.](assets/s_ncs_admin_survey_no_storage_condb.png)

## Uso de información recopilada {#using-collected-information}

Para cada formulario, las respuestas proporcionadas pueden reutilizarse en los campos o en las etiquetas. Se deben utilizar las siguientes sintaxis:

* Para el contenido almacenado en un campo de la base de datos:

  ```html
  <%=ctx.recipient.@field name%
  ```

* Para el contenido almacenado en una variable local:

  ```html
  <%= ctx.vars.variable name %
  ```

* Para el contenido almacenado en un campo de texto de HTML:

  ```html
  <%== HTML field name %
  ```

  >[!NOTE]
  >
  >A diferencia de los demás campos para los que los caracteres `<%=` se sustituyen por caracteres de escape, el contenido HTML se guarda tal cual con la sintaxis `<%==`.

## Almacenamiento de respuestas de formularios web {#saving-web-forms-answers}

Para guardar la información recopilada en las páginas de un formulario, se debe colocar un cuadro de almacenamiento en el diagrama.

![Diagrama de formulario web con las actividades Página de bienvenida, Suscribirse, Almacenamiento y Finalizar; se resaltó el cuadro de almacenamiento.](assets/s_ncs_admin_survey_save_box.png)

Este cuadro se puede utilizar de dos formas:

* Si se accede al formulario web a través de un vínculo enviado en un correo electrónico y si el usuario que accede a la aplicación ya está en la base de datos, se puede seleccionar la opción **[!UICONTROL Update the preloaded record]**. Para obtener más información, consulte [Envío de un formulario por correo electrónico](publishing-a-web-form.md#delivering-a-form-via-email).

  En este caso, Adobe Campaign utiliza la clave principal cifrada del perfil de usuario, un identificador único asignado a cada perfil mediante Adobe Campaign. Se debe configurar la información para precargarla mediante el cuadro de precarga. Para obtener más información, consulte [Precarga de los datos del formulario](publishing-a-web-form.md#pre-loading-the-form-data).

  >[!CAUTION]
  >
  >Esta opción anula los datos del usuario, incluso la dirección de correo electrónico si hay un campo en el que pueda introducirla. No se puede utilizar para crear perfiles nuevos y requiere el uso de un cuadro de precarga en el formulario.

* Para enriquecer los datos de los destinatarios en la base de datos, edite el cuadro de almacenamiento y seleccione la clave de reconciliación. Para uso interno (normalmente un sistema intranet) o para un formulario utilizado para crear perfiles nuevos, se pueden seleccionar los campos de reconciliación. El cuadro ofrece todos los campos de la base de datos utilizados en las distintas páginas de la aplicación web:

  ![Cuadro de diálogo de actividad de almacenamiento con el árbol de opciones de reconciliación de los campos Destinatarios y el campo Carpeta de búsqueda.](assets/s_ncs_admin_survey_save_box_edit.png)

De forma predeterminada, los datos se importan en la base de datos mediante una operación **[!UICONTROL Update or insertion]**: si existe en la base de datos, el elemento se actualiza (por ejemplo, la newsletter seleccionada o la dirección de correo electrónico ingresada). Si no existe, se añade la información.

Sin embargo, se puede cambiar este comportamiento. Para ello, seleccione la raíz del elemento y la operación que desea ejecutar en la lista desplegable:

![Lista de operaciones de actividad de almacenamiento: sólo reconciliación, actualizar o insertar, insertar, actualizar y eliminar.](assets/s_ncs_admin_survey_save_operation.png)

Puede seleccionar una carpeta de búsqueda para la reconciliación y una carpeta de creación de nuevos perfiles. Si estos campos están vacíos, los perfiles se buscan y se crean en la carpeta predeterminada del operador.

>[!NOTE]
>
>Las operaciones posibles son: **[!UICONTROL Simple reconciliation]**, **[!UICONTROL Update or insertion]**, **[!UICONTROL Insertion]**, **[!UICONTROL Update]**, **[!UICONTROL Deletion]**.\
>La carpeta predeterminada de un operador es la primera carpeta para la que el operador tiene permiso de escritura.\
>Consulte [esta sección](https://experienceleague.adobe.com/es/docs/campaign-classic/using/getting-started/permissions/access-management){target="_blank"}.
