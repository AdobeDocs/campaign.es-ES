---
product: campaign
title: Consultas con una relación “varios a varios”
description: Aprenda a hacer consultas mediante una relación “varios a varios”
feature: Query Editor
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: c320054d-7f67-4b12-aaa7-785945bf0c18
TQID: 'https://experienceleague.adobe.com/BnWR5Pz41h-CeMuyGKXKBmhRHGcuSShWerJpOWAN7W0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
    internal-label: Query Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 100%
---
# Realización de consultas con una relación “varios a varios” {#querying-using-a-many-to-many-relationship}



En este ejemplo, se desea recuperar los destinatarios no contactados durante los últimos 7 días. Esta consulta se refiere a todas las entregas.

En este ejemplo también muestra el modo de configurar un filtro relacionado con la selección de un elemento de recopilación (o nodo naranja). Los elementos de recopilación están disponibles en la ventana **[!UICONTROL Field to select]**.

* ¿Qué tabla se debe seleccionar?

  La tabla de destinatario (**nms:recipient**)

* Campos que se desea seleccionar para la columna de salida.

  Clave principal, Apellido, Nombre y Correo electrónico.

* ¿En función de qué criterios se filtra la información?

  En función de los registros de entrega de los destinatarios que van desde los 7 días anteriores a la fecha actual.

Siga estos pasos:

1. Abra el editor de consultas genérico y seleccione la tabla de destinatario **[!UICONTROL (nms:recipient)]**.
1. En la ventana **[!UICONTROL Data to extract]** seleccione **[!UICONTROL Primary key]**, **[!UICONTROL First name]**, **[!UICONTROL Last name]** y **[!UICONTROL Email]**.

   ![](assets/query_editor_nveau_33.png)

1. En la ventana de ordenación, ordene los nombres alfabéticamente.

   ![](assets/query_editor_nveau_34.png)

1. En la ventana **[!UICONTROL Data filtering]** seleccione **[!UICONTROL Filtering conditions]**.
1. En la ventana **[!UICONTROL Target element]**, la condición de filtrado para extraer perfiles sin registro de seguimiento para los últimos 7 días implica dos pasos. El elemento que se debe seleccionar es un vínculo de varios a varios.

   * Para empezar, seleccione el elemento de recopilación (nodo naranja) **[!UICONTROL Recipient delivery logs (broadlog)]** de la primera columna **[!UICONTROL Value]**.

     ![](assets/query_editor_nveau_67.png)

     Seleccione el operador **[!UICONTROL do not exist as]**. No es necesario seleccionar un segundo valor en esta línea.

   * El contenido de la segunda condición de filtrado depende de la primera. En este caso, el campo **[!UICONTROL Event date]** se ofrece directamente en la tabla **[!UICONTROL Recipient delivery logs]** ya que hay un vínculo a esta tabla.

     ![](assets/query_editor_nveau_36.png)

     Seleccione **[!UICONTROL Event date]** con el operador **[!UICONTROL greater than or equal to]**. Seleccione el valor **[!UICONTROL DaysAgo (7)]**. Para esto, haga clic en **[!UICONTROL Edit expression]** en el campo **[!UICONTROL Value]**. En la ventana **[!UICONTROL Formula type]**, seleccione **[!UICONTROL Process on dates]** y **[!UICONTROL Current date minus n days]**, dando &quot;7&quot; como valor.

     ![](assets/query_editor_nveau_37.png)

     Se ha configurado la condición de filtro.

     ![](assets/query_editor_nveau_38.png)

1. En la ventana **[!UICONTROL Data formatting]**, cambie los apellidos a mayúscula. En la columna **[!UICONTROL Last name]**, haga clic en la línea **[!UICONTROL Transformation]** y, en el menú desplegable, seleccione **[!UICONTROL Switch to upper case]**.

   ![](assets/query_editor_nveau_39.png)

1. Utilice la función **[!UICONTROL Add a calculated field]** para insertar una columna en la ventana de vista previa de datos.

   En este ejemplo, agregue un campo calculado con los nombres y apellidos de los destinatarios en una sola columna. Haga clic en la función **[!UICONTROL Add a calculated field]**. En la ventana **[!UICONTROL Export calculated field definition]**, introduzca una etiqueta y un nombre interno y elija el tipo de **[!UICONTROL JavaScript Expression]**. A continuación, introduzca la siguiente expresión:

   ```
   var rep = source._firstName+" - "+source._lastName
   return rep
   ```

   ![](assets/query_editor_nveau_40.png)

   Haga clic en **[!UICONTROL OK]**. La ventana **[!UICONTROL Data formatting]** está configurada.

   Para obtener más información sobre la adición de campos calculados, consulte esta sección.

1. El resultado se muestra en la ventana **[!UICONTROL Data preview]**. Los destinatarios que no hayan sido contactados en los últimos 7 días se muestran en orden alfabético. Los nombres se muestran en mayúsculas y se ha creado la columna con el nombre y los apellidos.

   ![](assets/query_editor_nveau_41.png)
