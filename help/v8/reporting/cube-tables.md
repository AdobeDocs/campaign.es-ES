---
product: campaign
title: Uso de cubos para crear informes sobre datos
description: Aprenda a utilizar cubos para crear informes
feature: Reporting
role: User, Developer
level: Beginner
exl-id: 7dbc66ab-a468-40ff-9db2-b33e4fd27754
TQID: 'https://experienceleague.adobe.com/fVo8tGw-kPgGgB7djOQr8tv5MoRvrPr-MF2bzYYKDgI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 82ae202007873dab2324bfa4b13a6014efd19887
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 48%
---
# Uso de cubos para explorar datos{#use-cubes-to-create-reports}

Utilice los cubos para crear informes e identificar y seleccionar datos de la base de datos. Se puede:

* Crear informes basados en cubos. [Más información](#explore-the-data-in-a-report).
* Recopilar los datos de la base de datos y agruparlos en listas, por ejemplo, para identificar y crear destinatarios y entregas. [Más información](#build-a-target-population).
* Inserte una tabla dinámica en un informe y haga referencia a un cubo existente en él. [Más información](#insert-a-pivot-table-into-a-report).

## Exploración de los datos de un informe {#explore-the-data-in-a-report}

### Paso 1: Creación de un informe basado en un cubo {#step-1---create-a-report-based-on-a-cube}

Una vez configurado el [cubo](cube-indicators.md), se puede usar como plantilla para crear un nuevo informe.

Para crear un informe basado en un cubo existente, siga los pasos a continuación:

1. En la pestaña **[!UICONTROL Reports]**, haga clic en el botón **[!UICONTROL Create]** y seleccione el cubo recién creado.

   ![Creando una nueva página de informe con la plantilla de cubo Nuevo perfil de cliente seleccionada y el botón Crear](assets/new-report-based-on-cube.png)

1. Haga clic en el botón **[!UICONTROL Create]** para confirmar: esto le lleva a la configuración del informe y a la página de visualización.

   De forma predeterminada, las dos primeras dimensiones disponibles se ofrecen en líneas y columnas, pero no se muestra ningún valor en la tabla. Para generar la tabla, haga clic en el icono principal:

   ![Nuevo informe de perfil de cliente con ejes de fecha de creación y antigüedad y el icono para mostrar la tabla dinámica](assets/cube-report-config.png)

1. Puede cambiar los ejes de la dimensión, eliminarlos, agregar nuevas medidas, etc. Para ello, utilice los iconos adecuados.

   ![Dimensión de fecha de creación arrastrada desde el eje izquierdo al eje superior junto a Edad en el informe Nuevo perfil de cliente](assets/cube-switch-axis.png)

   Estas operaciones se detallan a continuación.

### Paso 2: Selección de líneas y columnas {#step-2---select-lines-and-columns}

La visualización predeterminada muestra las dos primeras dimensiones del cubo (edad y ciudad, en este caso).

Los botones **[!UICONTROL Add]** en cada eje permiten añadir dimensiones.

![Botón Agregar en el eje de líneas del informe Nuevo perfil de cliente para agregar una dimensión](assets/cube-switch.png)

1. Seleccione las dimensiones que desea mostrar en las líneas y columnas de la tabla. Para ello, arrastre y suelte las dimensiones disponibles.
1. Seleccione las dimensiones que desee añadir a la tabla desde la lista:
   ![Agregue una dimensión al cuadro de diálogo de columna que enumera Ciudad, País, Fecha de última compra e Importe de compras](assets/cube-select-dimension.png)

1. Luego seleccione los parámetros de esta dimensión.

   ![Configuración de Dimension para la ciudad: etiqueta, expandir durante la carga, ordenar datos, orden y número de líneas mostradas](assets/cube-dimension-param.png)

   Estos parámetros dependen del tipo de datos de la dimensión seleccionada.

   Por ejemplo, en el caso de las fechas, puede haber disponibles varios niveles. Para más información, consulte [Visualización de medidas](customize-cubes.md#display-measures).

   En ese caso, están disponibles las siguientes opciones:

   ![Configuración de dimensión de fecha por nivel, año y mes, incluido el formato largo o corto](assets/cube-config.png)

   Puede:

   * Expandir los datos durante la carga: los valores se muestran de forma predeterminada cada vez que se actualiza el informe (valor predeterminado: no).
   * Mostrar el total al final de la línea: cuando los datos se muestran en columnas, una opción adicional permite mostrar el total al final de la línea: se añade una columna a la tabla (valor predeterminado: sí).
   * Aplicar una clasificación: los valores de la columna se pueden ordenar según el valor, la etiqueta o en función de una medida (valor predeterminado: por valor).
   * Mostrar los valores en orden ascendente (a-z, 0-9) o descendente (z-a, 9-0).
   * Cambiar el número de columnas que desea mostrar al cargar (número predeterminado: 200).

1. Haga clic en **[!UICONTROL Ok]** para confirmar que la dimensión se añada a las ya existentes.

   El aviso amarillo sobre la tabla indica que se han realizado cambios. Haga clic en el botón **[!UICONTROL Save]** para guardarlos.

   ![Ciudad agregada al eje de líneas, con el aviso amarillo que le solicita que guarde los cambios del informe](assets/cube-in-report.png)

### Paso 3: Configuración de las medidas que desea mostrar {#step-3---configure-the-measures-to-display}

Una vez definidas las líneas y las columnas, seleccione las medidas que desee mostrar. De forma predeterminada, solo se muestra una medida.

Para añadir y configurar medidas, siga los pasos a continuación:

1. Haga clic en el botón **[!UICONTROL Measures]**.

   ![Botón Medidas abriendo el cuadro de diálogo Configurar medidas con las opciones Etiqueta, Formato y Unidad](assets/cube-measure-button.png)

1. Con el botón **[!UICONTROL Use a measure]**, seleccione una de las medidas existentes.

   ![Agregar una medida existente al cuadro de diálogo de tabla dinámica que enumera francés, alemán, hombres y mujeres](assets/cube-add-measure.png)

   Elija la información que desea mostrar y las opciones de formato. La lista de opciones depende del tipo de medida.

   ![Cuadro de diálogo Configurar medidas con las opciones de formato Número y porcentaje y Editar el botón de medida dinámica](assets/cube-measure-options.png)

   La configuración general de medidas también está disponible a través del icono **[!UICONTROL Edit the configuration of the pivot table]** del encabezado.

   ![Edite el icono de configuración de tabla dinámica en la barra de herramientas de informes](assets/cube-pivot-table-config.png)

   A continuación puede elegir si desea mostrar o no las etiquetas de medida. [Más información](customize-cubes.md#configuring-the-display).

1. Puede generar nuevas medidas basadas en las existentes. Para ello, haga clic en **[!UICONTROL Create a measure]** y configúrelo.

   ![Creación de un cuadro de diálogo de medida dinámica con la combinación de tipo de medidas, operador y dos medidas](assets/cube-create-new-measure.png)

   Los siguientes tipos de medidas está disponibles:

   * Combinación de medidas: este tipo de medida permite crear la nueva medida utilizando las existentes:

     Los operadores disponibles son: suma, diferencia, multiplicación y tasa.

   * Proporción: este tipo de medida permite calcular el número de registros medidos para una dimensión determinada. Se puede calcular la proporcionalidad en función de una dimensión o subdimensión.
   * Variación: esta medida permite calcular la variación en valores de un nivel.
   * Desviación estándar: este tipo de medida permite calcular las desviaciones dentro de cada grupo de celdas en comparación con la media de los valores. Por ejemplo, se puede comparar el volumen de compra de todos los segmentos existentes.

   Una vez creada, la medida se añade al informe.

   ![Tabla dinámica que muestra la nueva medida en alemán e inglés junto a Hombres y mujeres, por compañía](assets/cube-display-new-measure.png)

   Una vez creada una medida, puede editarla y cambiar su configuración. Para ello, haga clic en el botón **[!UICONTROL Measures]** y luego vaya a la pestaña de la medida que desea editar.

   A continuación, haga clic en **[!UICONTROL Edit the dynamic measure]** para acceder al menú de configuración.

## Creación de una población objetivo {#build-a-target-population}

Los informes creados con los cubos permiten recopilar datos de la tabla y guardarlos en una lista.

Para agrupar una población en una lista, siga los pasos a continuación:

1. Haga clic en las celdas que contienen la población que quiera agrupar y selecciónelas. A continuación, haga clic en el icono **[!UICONTROL Add to cart]**.

   ![Icono Agregar al carro de compras en la barra de herramientas de la tabla dinámica CLIENTS con celdas seleccionadas](assets/cube-add-to-cart.png)

   Haga esto las veces que sean necesarias para recopilar varios perfiles.

1. Haga clic en el botón **[!UICONTROL Show cart]** para ver su contenido antes de ejecutar la exportación.

   ![Mostrar botón del carro de compras abriendo el cuadro de diálogo Detalles del carro de compras con los elementos del carro de compras y el botón Exportar](assets/cube-show-cart.png)

1. Utilice el botón **[!UICONTROL Export]** para agrupar los elementos del carro en una lista.

   Introduzca el nombre de la lista y seleccione el tipo de exportación que desea realizar.

   ![Cuadro de diálogo Exportar carro 1/2 con exportar a una lista nueva, Etiqueta, Carpeta y Tipo de exportación y Botón de inicio](assets/cube-export-report.png)

   Haga clic en **[!UICONTROL Start]** para ejecutar la exportación.

1. Una vez finalizada la exportación, un mensaje confirma su ejecución y el número de registros que se han procesado.

   ![Cuadro de diálogo Exportar carro 2/2 que confirma que la exportación ha finalizado con el número de registros y los botones Cerrar](assets/cube-export-confirm.png)

   Puede guardar el contenido del carro o vaciarlo.

   La nueva lista está disponible a través de la ficha **[!UICONTROL Profiles and targets]**.

   ![Lista de la página en Perfiles y destinos que muestra la nueva lista de destinatarios GOLD](assets/cube-list-available.png)

## Inserción de una tabla dinámica en un informe {#insert-a-pivot-table-into-a-report}

Para crear una tabla y explorar los datos de un cubo, siga los pasos a continuación:

1. Cree un nuevo informe con una sola página e inserte una tabla dinámica.

   ![Editor de informes con una actividad Page y la opción Pivot table del menú de la barra de herramientas](assets/cube-insert-in-report.png)

1. En la pestaña **[!UICONTROL Data]** de la página, seleccione un cubo para procesar las dimensiones que contiene y mostrar las medidas calculadas.

   ![Ficha Datos de la tabla dinámica con el cubo Nuevo perfil de cliente seleccionado en el campo Cubo](assets/cube-selected-in-report.png)

   Esto permite generar el informe que se desea mostrar. Para obtener más información, consulte [Paso 2 - Seleccionar líneas y columnas](#step-2---select-lines-and-columns).
