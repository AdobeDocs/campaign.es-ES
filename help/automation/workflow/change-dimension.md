---
product: campaign
title: Cambiar la dimensión en un flujo de trabajo
description: Aprenda a utilizar la actividad de la dimensión Cambiar
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 71f36413-377a-4be6-921c-9e794fe882fd
TQID: 'https://experienceleague.adobe.com/BkGTNKy7N35h3jO5-Ao2x2-nClcv96wqT2AqIsAXlSA'
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
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 47%
---
# Dimensión cambiante{#change-dimension}

Utilice la actividad **[!UICONTROL Change dimension]** para cambiar la dimensión de segmentación mientras crea una audiencia. Esta actividad desplaza el eje según la plantilla de datos y la dimensión de entrada. Por ejemplo, cambia de la dimensión &quot;contratos&quot; a la dimensión &quot;clientes&quot;.

También puede utilizar esta actividad para definir las columnas adicionales del nuevo destinatario y los criterios de anulación de duplicación de datos.

>[!IMPORTANT]
>
>Tenga en cuenta que las actividades **[!UICONTROL Change Dimension]** y **[!UICONTROL Change Data source]** no deben agregarse en una fila. Si necesita usar ambas actividades consecutivamente, asegúrese de incluir una actividad **[!UICONTROL Enrichement]** entre ellas. Esto garantiza una ejecución adecuada y evita posibles conflictos o errores.

Para configurar la actividad **[!UICONTROL Change dimension]**, siga los siguientes pasos:

1. Seleccione la nueva dimensión de segmentación mediante el campo **[!UICONTROL Change dimension]**.

   ![Cambie el campo de dimensión de la actividad con el selector de campo abierto y las suscripciones seleccionadas como la nueva dimensión](assets/s_user_change_dimension_param1.png)

1. Durante el cambio de dimensión, se pueden mantener todos los elementos o seleccionar los que desea conservar en la salida. En el ejemplo siguiente, el número máximo de duplicados se establece en 2.

   ![Opción Limita el número de elementos en el nuevo documento de segmentación seleccionado con el campo Límite establecido en 2](assets/s_user_change_dimension_limit.png)

   Cuando decide mantener un solo registro, se muestra una colección en el esquema de trabajo: Esta colección representa todos los registros que no van a ser objetivo en el resultado final (ya que solo se guarda un registro). Al igual que todas las demás colecciones, este permite calcular las agregaciones o recuperar información en columnas.

   Por ejemplo: si se cambia la dimensión **[!UICONTROL Customers]** a la dimensión **[!UICONTROL Recipients]**, es posible dirigirse a los clientes de un almacén específico, al mismo tiempo que se añade el número de compras realizadas.

1. Si elige no conservar toda esta información, puede configurar el modo de gestión del duplicado.

   ![Cuadro de diálogo de deduplicación que enumera los campos de correo electrónico y número de cuenta con las flechas que establecen su prioridad](assets/s_user_change_dimension_param2.png)

   Las flechas azules permiten definir la prioridad de procesamiento duplicada.

   En el ejemplo anterior, los destinatarios se deduplicarán en su dirección de correo electrónico primero, luego, si es necesario, en su número de cuenta.

1. La pestaña **[!UICONTROL Result]** permite añadir información adicional.

   Por ejemplo, se puede recuperar el municipio en función del código postal utilizando una función de tipo **Substring**. Para ello:

   * Haga clic en el vínculo **[!UICONTROL Add data...]** y seleccione **[!UICONTROL Data linked to the filtering dimension]**.

     ![Pestaña Resultado Agregar vínculo de datos al abrir el Asistente para datos adicionales con datos vinculados a la dimensión de filtrado seleccionada](assets/wf_change-dimension_sample_01.png)

     >[!NOTE]
     >
     >Para obtener información sobre cómo crear y administrar columnas adicionales, consulte [Agregar datos](query.md#adding-data).

   * Seleccione la dimensión de segmentación anterior (antes del cambio de eje) y, en el subárbol **[!UICONTROL Zip Code]** del destinatario, seleccione **[!UICONTROL Location]** y haga clic en **[!UICONTROL Edit expression]**.

     ![Asistente para datos adicionales con código postal desde el subárbol de ubicación agregado como columna de salida y Editar expresión](assets/wf_change-dimension_sample_02.png)

   * Haga clic en **[!UICONTROL Advanced selection]** y elija **[!UICONTROL Edit the formula using an expression]**.

     ![Botón de selección avanzada que abre el tipo de fórmula con Editar la fórmula usando una expresión seleccionada](assets/wf_change-dimension_sample_03.png)

   * Utilice las funciones ofrecidas en la lista y especifique el cálculo que se va a realizar.

     ![Editor de expresiones con la fórmula Subcadena del código postal del carácter 1 con la longitud 2 y la lista de funciones](assets/wf_change-dimension_sample_04.png)

   * Finalmente, introduzca la etiqueta de la columna que acaba de crear.

     ![Columnas de salida con la etiqueta County y la expresión Substring(zip/Postcode, 1, 2)](assets/wf_change-dimension_sample_05.png)

1. Ejecute el flujo de trabajo para ver el resultado de esta configuración. Compare los datos de las tablas antes y después de la actividad de dimensión cambiante y compare la estructura de las tablas de flujo de trabajo, como se muestra en los ejemplos siguientes:

   ![Mostrar la opción de destino en la transición antes de cambiar dimensión, con sus datos y esquema en Ver población](assets/wf_change-dimension_sample_06.png)

   ![Mostrar la opción de destino después de la dimensión Cambiar, mostrando los datos con la columna Condado y el nuevo esquema](assets/wf_change-dimension_sample_07.png)
