---
product: campaign
title: Enriquecimiento de correo electrónico con campos de datos personalizados
description: Descubra cómo enriquecer correos electrónicos con campos de datos personalizados
feature: Workflows
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 2bb3443c-37d8-4d49-9be1-81217f56823c
TQID: 'https://experienceleague.adobe.com/Mgo8JMtAXLW86GgkEsoVTtMSfUUKPsp-G9lL0p9JBg8'
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
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 65%
---
# Enriquecimiento de correo electrónico con campos de datos personalizados{#email-enrichment-with-custom-date-fields}



En este ejemplo, deseamos enviar un correo electrónico con campos de datos personalizados a los destinatarios que celebran su cumpleaños este mes. El correo electrónico incluirá un cupón válido una semana antes y después de su cumpleaños.

Es necesario segmentar a los destinatarios de una lista que celebran su cumpleaños este mes con una actividad **[!UICONTROL Split]**. A continuación, con la actividad **[!UICONTROL Enrichment]**, el campo de datos personalizados actuará como fecha de validez en el mensaje de correo electrónico para la oferta especial del cliente.

![Flujo de trabajo: lectura de lista, división con subconjunto en enriquecimiento, envío por correo electrónico y complemento hasta el final.](assets/uc_enrichment.png)

Para crear este ejemplo, aplique los pasos siguientes:

1. En la pestaña **[!UICONTROL Targeting and workflows]** de la campaña, arrastre y coloque una actividad **[!UICONTROL Read list]** para segmentar la lista de destinatarios.
1. La lista que se desea procesar se puede especificar explícitamente, calcularse por una secuencia de comandos o localizarse dinámicamente, según las opciones seleccionadas y los parámetros definidos aquí.

   ![Actividad de lista de lectura con la lista especificada explícitamente y la sección de filtrado de Source.](assets/uc_enrichment_1.png)

1. Agregue una actividad **[!UICONTROL Split]** para diferenciar a los destinatarios que celebren su cumpleaños este mes de otros destinatarios.
1. Para dividir la lista, en la categoría **[!UICONTROL Filtering of selected records]**, seleccione **[!UICONTROL Add a filtering condition on the inbound population]**. A continuación, haga clic en **[!UICONTROL Edit]**.

   ![Dividir subconjuntos ficha con Agregar una condición de filtrado en la población entrante y el vínculo Editar resaltado.](assets/uc_enrichment_2.png)

1. Seleccione **[!UICONTROL Filtering conditions]** y haga clic en el botón **[!UICONTROL Edit expression]** para filtrar el mes del cumpleaños del destinatario.

   ![Ventana del elemento de destino con el botón Editar expresión resaltado junto al campo Expresión.](assets/uc_enrichment_3.png)

1. Haga clic en **[!UICONTROL Advanced Selection]** y luego **[!UICONTROL Edit the formula using an expression]** y agregue la siguiente expresión: Month(@birthDate).
1. En la columna **[!UICONTROL Operator]**, seleccione **[!UICONTROL equal to]**.
1. Para filtrar más la condición, agregue el mes **[!UICONTROL Value]** de la fecha actual: Month(GetDate()).

   Esto consulta a los destinatarios cuyo mes de cumpleaños corresponda al mes actual.

   ![Condición del elemento de destino: mes de la fecha de nacimiento igual al mes de la fecha actual más 14 días.](assets/uc_enrichment_4.png)

1. Haga clic en **[!UICONTROL Finish]**. A continuación, en la pestaña **[!UICONTROL General]** de su actividad **[!UICONTROL Split]**, haga clic en **[!UICONTROL Generate complement]** en la categoría **[!UICONTROL Results]**.

   Con el resultado **[!UICONTROL Complement]**, puede añadir una actividad de envío o actualizar una lista. Aquí, agregamos una actividad **[!UICONTROL End]**.

   ![Dividir ficha General con la opción Generar complemento activada en la sección Resultados.](assets/uc_enrichment_6.png)

Ahora necesita configurar su actividad **[!UICONTROL Enrichment]**:

1. Agregue una actividad **[!UICONTROL Enrichment]** al subconjunto para añadir los campos de fecha personalizados.

   ![Flujo de trabajo con una actividad Enrichment agregada a la transición Subset de la actividad Split.](assets/uc_enrichment_7.png)

1. Abra la actividad **[!UICONTROL Enrichment]**. En la categoría **[!UICONTROL Complementary information]**, haga clic en **[!UICONTROL Add data]**.

   ![Actividad de enriquecimiento con el vínculo de datos Agregar resaltado en la sección Información complementaria.](assets/uc_enrichment_8.png)

1. Seleccione **[!UICONTROL Data linked to the filtering dimension]** luego **[!UICONTROL Data of the filtering dimension]**.
1. Haga clic en el botón **[!UICONTROL Add]**.

   ![Datos para agregar con el botón Agregar resaltado junto a la lista Columnas de salida.](assets/uc_enrichment_9.png)

1. Agregar una **[!UICONTROL Label]**. A continuación, en la columna **[!UICONTROL Expression]**, haga clic en **[!UICONTROL Edit expression]**.

   ![Columnas de salida con la etiqueta Birthdate y el botón Edit expression resaltado en la columna Expression.](assets/uc_enrichment_10.png)

1. En primer lugar, se debe establecer como objetivo la semana antes del cumpleaños como **Fecha de inicio de validez** con la siguiente **[!UICONTROL Expression]**: `SubDays([target/@birthDate], 7)`.

   ![Columnas de salida con la etiqueta Birthdate y la expresión Date of birth (target/@birthDate).](assets/uc_enrichment_11.png)

1. A continuación, para crear el campo de fecha personalizado **Validity end date**, que abarca la semana después del cumpleaños, se debe añadir la **[!UICONTROL Expression]**: `AddDays([target/@birthDate], 7)`.

   Se puede añadir una etiqueta a la expresión.

   ![Columnas de salida que enumeran Birthdate y la columna Validity start date con su expresión y alias.](assets/uc_enrichment_12.png)

1. Haga clic en **[!UICONTROL Ok]**. El enriquecimiento está listo.

Después de la actividad de **[!UICONTROL Enrichment]** puede agregar una entrega. En este caso, agregamos una entrega por correo electrónico para enviar a los destinatarios una oferta especial con fechas de validez para los clientes que celebran su cumpleaños ese mes.

1. Arrastre y suelte una actividad de **[!UICONTROL Email delivery]** después de su actividad de **[!UICONTROL Enrichment]**.

   ![Flujo de trabajo con una actividad de envío de correo electrónico agregada después de la actividad de enriquecimiento.](assets/uc_enrichment_15.png)

1. Haga doble clic en la actividad **[!UICONTROL Email delivery]** para comenzar a personalizar la entrega.
1. Añada a la entrega una **[!UICONTROL Label]** y haga clic en **[!UICONTROL Continue]**.
1. Haga clic en **[!UICONTROL Save]** para crear su envío por correo electrónico.
1. Compruebe en la pestaña **[!UICONTROL Approval]** del envío de correo electrónico **[!UICONTROL Properties]** que **[!UICONTROL Confirm delivery before sending option]** está marcado.

   A continuación, inicie el flujo de trabajo para enriquecer la transición saliente con la información objetivo.

   ![Pestaña Aprobaciones de propiedades de entrega con la opción Confirmar la entrega antes de enviarla activada.](assets/uc_enrichment_18.png)

Ahora puede empezar a diseñar su envío por correo electrónico con los campos de fecha personalizados creados en la actividad **[!UICONTROL Enrichment]**.

1. Haga doble clic en la actividad **[!UICONTROL Email delivery]**.
1. Añada sus extensiones de destino al correo electrónico. Debe estar dentro de la siguiente expresión para configurar el formato de las fechas de validez:

   ```
   <%=
           formatDate(targetData.alias of your expression,"%2D.%2M")  %>
   ```

1. Haga clic en ![botón de la barra de herramientas de Personalization con una flecha desplegable.](assets/uc_enrichment_16.png). Seleccione **[!UICONTROL Target extension]** y luego las fechas de validez personalizadas creadas anteriormente con la actividad **[!UICONTROL Enrichment]** para agregar la extensión a la expresión formatDate.

   ![Menú Personalization Extensión de Target submenú que enumera la fecha de inicio de validez y la fecha de finalización de validez.](assets/uc_enrichment_19.png)

1. Configure su contenido de correo electrónico según sea necesario.

   ![Contenido de HTML de correo electrónico con expresiones formatDate que utilizan campos targetData para las fechas de validez.](assets/uc_enrichment_17.png)

1. Previsualice el correo electrónico para comprobar si los campos de fecha personalizados se han configurado correctamente.

   ![Pestaña Vista previa de correo electrónico que muestra el mensaje de cumpleaños con las fechas de validez del 20/12 al 03/01 rellenadas.](assets/uc_enrichment_20.png)

Su correo electrónico está listo. Puede comenzar a enviar las pruebas y confirmar el envío para mandar los correos electrónicos de cumpleaños.
