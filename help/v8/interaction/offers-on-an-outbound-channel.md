---
product: campaign
title: Ofertas en un canal de salida
description: Ofertas en un canal de salida
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 77fee343-09d1-4d60-be43-efe02953a70c
TQID: 'https://experienceleague.adobe.com/WGoYaHNR13J47UVmKpHRSm9aw0T8ZrvHUl9zGXezQBU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 54%
---
# Ofertas en un canal de salida{#offers-on-an-outbound-channel}



## Envío de ofertas por correo electrónico {#email-offer-delivery}

En nuestra base de datos, existe una categoría de ofertas de viajes a África. Se han configurado los requisitos, los contextos y las representaciones de cada oferta. Ahora queremos crear una campaña para presentar las ofertas por correo electrónico.

1. Cree una campaña de marketing y los flujos de trabajo de segmentación.

   ![Flujo de trabajo de segmentación de la campaña Viajes a África: carpeta, envío, anulación de duplicación y dos actividades de actualización de listas](assets/offer_delivery_example_001.png)

1. Edite la entrega por correo electrónico y haga clic en el icono **[!UICONTROL Offers]**.

   ![Envío de correo electrónico con el icono Ofertas que abre la ventana Administración de ofertas, las opciones de selección de ofertas y el campo Espacio de ofertas](assets/offer_delivery_example_002.png)

1. Elija el espacio del correo electrónico para el entorno de la oferta que coincida con los días festivos.

   ![Ventana de administración de ofertas con la lista del espacio de ofertas que muestra los espacios de correo electrónico disponibles, incluidos los recorridos de suscriptores](assets/offer_delivery_example_003.png)

1. Elija la categoría que contiene las ofertas de viajes de África.

   ![Ventana de administración de ofertas con el árbol de categorías expandido en Catálogo de ofertas y Recorridos, categoría de África resaltada](assets/offer_delivery_example_004.png)

1. Defina el número de ofertas en la entrega a dos.

   ![Ventana de administración de ofertas con categoría África y Número de propuestas por mensaje establecido en 2](assets/offer_delivery_example_005.png)

1. Cierre la ventana de Gestión de ofertas y cree el contenido de su envío.

   ![Editor de contenido de HTML de envío de correo electrónico con vistas de inclusión predeterminadas, listo para propuestas de ofertas](assets/offer_delivery_example_006.png)

1. Utilice los menús para insertar una primera propuesta de oferta y elija la función de procesamiento HTML.

   ![Menú de la barra de herramientas de contenido de HTML: Propositions, Proposition 1, Rendering function and HTML rendering](assets/offer_delivery_example_007.png)

1. Inserte la segunda propuesta de oferta.

   ![El contenido de HTML de correo electrónico con ambas propuestas incluye líneas usando la vista rendering/html, antes del vínculo de baja](assets/offer_delivery_example_008.png)

1. Haga clic en **[!UICONTROL Preview]** para previsualizar las ofertas de la entrega y, a continuación, seleccione un destinatario para previsualizar las ofertas a medida que las reciban.

   ![Pestaña Delivery Preview que muestra el correo electrónico con el título de la oferta de Crossing the Sahara, el texto y la imagen de un destinatario seleccionado](assets/offer_delivery_example_009.png)

1. Guarde la entrega e inicie el flujo de trabajo de objetivos.
1. Abra la entrega y haga clic en la pestaña **[!UICONTROL Audit]** de la entrega: puede ver que el motor de ofertas ha seleccionado las propuestas que se realicen desde las diferentes ofertas del catálogo.

   ![Pestaña Auditoría de entregas Registra las propuestas generadas por oferta, como las ofertas de Pirámides y Sahara](assets/offer_delivery_example_010.png)

## Realizar una simulación de oferta {#perform-an-offer-simulation}

1. En la pestaña **[!UICONTROL Profiles and Targets]**, haga clic en el vínculo **[!UICONTROL Simulations]** y, luego, haga clic en el botón **[!UICONTROL Create]**.

   ![Lista de simulaciones con el botón Crear abriendo el cuadro de diálogo Nueva simulación de oferta con plantilla, etiqueta y carpeta](assets/offer_simulation_001.png)

1. Elija una etiqueta y especifique la configuración de ejecución si es necesario.

   ![Nuevo cuadro de diálogo de simulación de oferta con la etiqueta 1 año de suscriptores, la carpeta Simulaciones y la configuración de ejecución](assets/offer_simulation_example_002.png)

1. Guarde la simulación. A continuación, se abre en una nueva pestaña.

   ![Panel de simulación de 1 año de suscriptores con la pestaña Edit y un botón Start simulation](assets/offer_simulation_example_003.png)

1. Haga clic en la pestaña **[!UICONTROL Edit]** luego en **[!UICONTROL Scope]**.

   ![Pestaña Simulation Edit, sección Scope, con entorno o categoría, espacio de ofertas, temas, fecha de contacto y propuestas](assets/offer_simulation_example_004.png)

1. Elija la categoría para la que desea simular las ofertas.

   ![La lista de entornos o categorías se ha expandido en Ofertas - diseño y Catálogo de ofertas, con la categoría Viajes seleccionada](assets/offer_simulation_example_005.png)

1. Seleccione el espacio de oferta que se utilizará para la simulación.

   ![Lista de espacio de ofertas en la categoría Viajes que ofrece Correo directo y Correo electrónico (Entorno - Destinatario)](assets/offer_simulation_example_006.png)

1. Introduzca las fechas de validez. Debe introducir al menos una fecha de inicio. Esto permite que el filtro del motor de ofertas ofrezca y elija las que son válidas en una fecha determinada.
1. Si es necesario, especifique uno o varios temas para restringir el número de ofertas a aquellas que contengan una palabra clave en su configuración.

   En nuestro ejemplo, la categoría **Viaje** contiene dos subcategorías con dos temas independientes. Queremos ejecutar una simulación para las ofertas con el tema de los **clientes>1 año**.

   ![Sección de ámbito con el tema Cliente > 1 año ingresado en el campo Temas para la categoría Viajes](assets/offer_simulation_example_007.png)

1. Elija los destinatarios a los que desea destinarlas.

   ![Asistente para filtrar la selección de destinos eligiendo una lista de destinatarios y luego la lista de viajeros frecuentes](assets/offer_simulation_example_008.png)

1. Configure el número de ofertas que se enviarán a cada destinatario.

   En nuestro ejemplo, el motor de oferta elegirá las 3 ofertas con el peso más alto para cada destinatario.

   ![Sección de ámbito con número de propuestas establecido en 3 y la consulta de destino en la lista de entrega de oferta especial](assets/offer_simulation_example_009.png)

1. Guarde la configuración y, en la pestaña **[!UICONTROL Start]**, haga clic en **[!UICONTROL Dashboard]** para ejecutar la simulación.

   ![Cuadro de diálogo de simulación de inicio del panel solicitando confirmación, con el botón Aceptar resaltado](assets/offer_simulation_example_010.png)

1. Una vez finalizada la simulación, consulte **[!UICONTROL Results]** para obtener un desglose detallado de las propuestas por oferta.

   En nuestro ejemplo, el motor de oferta basa el desglose de las ofertas en 3 propuestas.

   ![Pestaña Resultados de la simulación con desglose de propuestas por ofertas: tamaño de población 30, número de propuestas 30](assets/offer_simulation_example_011.png)

1. Despliegue **[!UICONTROL Breakdown of offers by rank]** para ver la lista de ofertas seleccionadas por el motor de ofertas.

   ![Desglose de ofertas por informe de clasificación con tabla de clasificación de ofertas para Viaje a los Estados Unidos y Descubre Francia, y un gráfico circular](assets/offer_simulation_example_012.png)

1. Si es necesario, puede cambiar la configuración del ámbito y ejecutar otra vez la simulación haciendo clic en **[!UICONTROL Start simulation]**.

   ![Cuadro de diálogo de simulación de inicio del panel solicitando confirmación, con el botón Aceptar resaltado](assets/offer_simulation_example_010.png)

1. Para guardar los datos de simulación, utilice las funciones del historial o de exportación disponibles en el informe.

   ![Informe de desglose de ofertas por rango con el menú Exportar y el icono de guardar resaltados](assets/offer_simulation_example_013.png)
