---
product: campaign
title: Adición de un campo calculado de tipo Enumeración
description: Aprenda cómo añadir un campo calculado de tipo Enumeración
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 4fe2ae81-faa6-4777-a332-70c451bca75b
TQID: 'https://experienceleague.adobe.com/SC-bh-Ms6cMAg0YV14vjf0wA-Ijw-D4MY-s4kqWXZiQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 75%
---
# Adición de un campo calculado de tipo Enumeración {#adding-an-enumeration-type-calculated-field}

Aquí se desea crear una consulta con un campo calculado de tipo **[!UICONTROL Enumerations]**. Este campo genera una columna adicional en la ventana de vista previa de datos. Esta columna especifica los valores numéricos devueltos como resultado de cada destinatario (0, 1 y 2). Se asigna un género a cada valor de la nueva columna: “Hombre” para “1”, “Mujer” para “2” o “No indicado” si el valor es igual a “0”.

* ¿Qué tabla se debe seleccionar?

  La tabla del destinatario (nms:recipient)

* ¿Campos que se desea seleccionar en la columna de salida?

  Apellidos, Nombre, Género

* ¿Con qué criterios se va a filtrar la información?

  El lenguaje del destinatario.

Siga estos pasos:

1. Abra [Generic query editor](../../v8/start/query-editor.md) y seleccione la tabla de destinatarios (**[!UICONTROL nms:recipient]**).
1. En la ventana **[!UICONTROL Data to extract]**, seleccione **[!UICONTROL Last name]**, **[!UICONTROL First name]** y **[!UICONTROL Gender]**.

   ![Datos para extraer la ventana con Apellidos, Nombre y Género en la lista Columnas de salida.](assets/query_editor_nveau_73.png)

1. En la ventana **[!UICONTROL Sorting]**, haga clic en **[!UICONTROL Next]**: en este ejemplo, no es necesario ordenar.
1. En **[!UICONTROL Data filtering]**, seleccione **[!UICONTROL Filtering conditions]**.
1. En la ventana **[!UICONTROL Target element]**, defina una condición de filtro para recopilar los destinatarios que hablan en inglés.

   ![Ventana del elemento de destino con la condición de filtro Idioma (@language) igual a EN.](assets/query_editor_nveau_74.png)

1. En la ventana **[!UICONTROL Data formatting]**, haga clic en **[!UICONTROL Add a calculated field]**.

   ![Ventana de formato de datos con el botón Agregar un campo calculado resaltado.](assets/query_editor_nveau_75.png)

1. En la ventana **[!UICONTROL Type]**, vaya a la ventana **[!UICONTROL Export calculated field definition]** y seleccione **[!UICONTROL Enumerations]**.

   Defina la columna a la que debe hacer referencia el nuevo campo calculado. Para ello, en el menú desplegable **[!UICONTROL Gender]**, seleccione **[!UICONTROL Source column]** en la columna: los valores de destino coinciden con la columna **[!UICONTROL Gender]**.

   ![Definición de campo calculada con Type establecido en Enumerations y Source establecido en Gender.](assets/query_editor_nveau_76.png)

   Defina los valores de **Origen** y **Destino**: el valor de destino facilita la lectura del resultado de la consulta. Esta consulta debe devolver el género del destinatario y el resultado será 0, 1 o 2.

   Para que se introduzca cada línea “origen-destino”, en **[!UICONTROL Add]**, haga clic en **[!UICONTROL List of enumeration values]**:

   * En la columna **[!UICONTROL Source]**, introduzca el valor de origen de cada género (0, 1, 2) en una nueva línea.
   * En la columna **[!UICONTROL Destination]**, introduzca los valores: “No indicado” para la línea “0”, “Hombre” para la línea “1” y “Mujer” para la línea “2”.

   Seleccione la función **[!UICONTROL Keep the source value]**.

   Haga clic en **[!UICONTROL OK]** para aprobar el campo calculado.

   ![Valores de enumeración que asignan el origen 0, 1 y 2 a No indicado, Hombre y Mujer; mantenga seleccionado el valor de origen.](assets/query_editor_nveau_77.png)

1. En la ventana **[!UICONTROL Data formatting]**, haga clic en **[!UICONTROL Next]**.
1. En la ventana de vista previa, **[!UICONTROL start the preview of the data]**.

   La columna adicional define el género de 0, 1 y 2:

   * 0 para “No indicado”,
   * 1 para “Masculino”,
   * 2 para “Femenino”.

   ![Vista previa de los datos con las columnas de especificaciones de Género y Género, por ejemplo 1 con Hombre y 0 con No indicado.](assets/query_editor_nveau_78.png)

   Por ejemplo, si no introduce el género “2” en **[!UICONTROL List of enumeration values]** y la función **[!UICONTROL Generate a warning and continue]** del campo **[!UICONTROL In other cases]** está seleccionada, aparece un registro de advertencia. Este registro indica que no se ha introducido el género “2” (Femenino). Se muestra en el campo **[!UICONTROL Logs generated during export]** de la ventana de vista previa de datos.

   ![La vista previa de datos con una fila 2 de sexo marcado y el valor 2 de enumeración de registro no existe para el @gender de columna.](assets/query_editor_nveau_79.png)

   Tomemos otro ejemplo y digamos que el valor de la enumeración “2” no se ingresó. Seleccione la función **[!UICONTROL Generate an error and reject the line]**: todos los destinatarios cuyo sexo sea “2” generarán anomalías y el resto de la información de la línea (nombre y apellido, etc.) no se exportará. Se muestra un registro de error en el campo **[!UICONTROL Logs generated during export]** de la ventana de vista previa de datos. Este registro indica que no se ha introducido el valor de enumeración “2”.

   ![Vista previa de datos con iconos de error en las filas de género 2 rechazadas y el valor de enumeración de registro 2 no existe.](assets/query_editor_nveau_80.png)
