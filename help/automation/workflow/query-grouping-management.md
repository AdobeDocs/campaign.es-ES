---
product: campaign
title: Consultas mediante la administración de agrupación
description: Obtenga información sobre cómo realizar consultas mediante la administración de agrupación
feature: Query Editor
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 6fc4ef67-5d75-4c8c-8bcc-41e3ed155ca2
TQID: 'https://experienceleague.adobe.com/-OBJg0XeJowHsyunWoCdl6K434cs-p08xMFRKJmz--4'
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
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 74%
---
# Realización de consultas mediante la administración de agrupación {#querying-using-grouping-management}



En este ejemplo, se desea ejecutar una consulta para buscar todos los dominios de correo electrónico que han sido objetivos más de 30 veces durante las entregas anteriores.

* ¿Qué tabla se debe seleccionar?

  La tabla del destinatario (nms:recipient)

* ¿Campos que se van a seleccionar en las columnas de salida?

  Dominio de correo electrónico y clave principal (con recuento).

* ¿Agrupación de datos?

  En función del dominio de correo electrónico con un recuento de claves principales por encima de 30. Esta operación se lleva a cabo con la opción **[!UICONTROL Group by + Having]**. **[!UICONTROL Group by + Having]** permite agrupar los datos (“Group by”) y realizar una selección de lo que se ha agrupado (“Having”).

Para crear este ejemplo, aplique los pasos siguientes:

1. Abra el **[!UICONTROL Generic query editor]** y seleccione la tabla de destinatarios (**nms:recipient**).

   ![Pantalla de tipo de documento del editor de consultas genérico con Destinatarios (nms) seleccionados.](assets/query_editor_02.png)

1. En la ventana **[!UICONTROL Data to extract]**, seleccione los campos **[!UICONTROL Email domain]** y **[!UICONTROL Primary key]**. Ejecute un recuento en el campo **[!UICONTROL Primary key]**.

1. Marque la casilla **[!UICONTROL Handle groupings (GROUP BY + HAVING)]**.

   ![Datos para extraer la pantalla con las columnas Dominio de correo electrónico y recuento (clave principal), Gestión de agrupaciones (GROUP BY + HAVING) verificada.](assets/query_editor_nveau_29.png)

1. En la ventana **[!UICONTROL Sorting]**, ordene los dominios de correo electrónico en orden descendente. Para ello, seleccione **[!UICONTROL Yes]** en la columna **[!UICONTROL Descending sort]**. Haga clic **[!UICONTROL Next]**.

   ![Pantalla de ordenación con dominio de correo electrónico ordenado, que muestra las columnas de ordenación Ordenar y Descendente.](assets/query_editor_nveau_70.png)

1. En **[!UICONTROL Data filtering]**, seleccione **[!UICONTROL Filtering conditions]**. Vaya a la ventana **[!UICONTROL Target elements]** y haga clic en **[!UICONTROL Next]**.
1. En la ventana **[!UICONTROL Data grouping]**, seleccione la opción **[!UICONTROL Email domain]** haciendo clic en **[!UICONTROL Add]**.

   Esta ventana de agrupamiento de datos solo se muestra si se ha marcado la casilla **[!UICONTROL Handle groupings (GROUP BY + HAVING]**.

   ![Pantalla de agrupación de datos que enumera el dominio de correo electrónico (@domain) como columna de grupo para la cláusula GROUP BY.](assets/query_editor_blocklist_04.png)

1. En la ventana **[!UICONTROL Grouping condition]**, indique un recuento de clave principal mayor que 30, ya que solo se desea que los dominios de correo electrónico que han sido objetivos más de 30 veces sean devueltos como resultados.

   Esta ventana aparece cuando se ha marcado la casilla **[!UICONTROL Manage groupings (GROUP BY + HAVING)]**: aquí es donde se filtra el resultado de la agrupación (HAVING).

   ![Pantalla de condición de agrupación con count(primary key) mayor que 30 para la cláusula HAVING.](assets/query_editor_blocklist_05.png)

1. En la ventana **[!UICONTROL Data formatting]**, haga clic en **[!UICONTROL Next]**: aquí no es necesario ningún formato.
1. En la ventana de vista previa de datos, haga clic en **[!UICONTROL Launch data preview]**: aquí se devuelven tres dominios de correo electrónico que han sido objetivos más de 30 veces.

   ![La pantalla de vista previa de datos devuelve dos dominios de correo electrónico una vez iniciada la vista previa.](assets/query_editor_blocklist_06.png)
