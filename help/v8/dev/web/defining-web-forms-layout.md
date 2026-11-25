---
product: campaign
title: Definición del diseño de los formularios web
description: Definición del diseño de los formularios web
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 23ca17f8-de1a-4f9c-8357-3965dc3329b1
TQID: 'https://experienceleague.adobe.com/-0PZWl-79Q-MXZ-jHjp-VF12IUPeMcq27aGSgWl5Ans'
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
source-wordcount: '703'
ht-degree: 71%
---
# Definición del diseño de los formularios web{#defining-web-forms-layout}



## Creación de contenedores {#creating-containers}

Los contenedores permiten combinar los campos de una página, configurar su diseño y organizar los elementos de la página.

Para cada página del formulario, los contenedores se crean mediante el botón **[!UICONTROL Containers]** de la barra de herramientas.

![Editor de página de formulario web con el botón de barra de herramientas Contenedores abierto, que ofrece la opción Contenedor estándar](assets/s_ncs_admin_survey_containers_add.png)

Utilice un contenedor para agrupar los elementos de la página sin añadir una etiqueta al procesamiento final. Los elementos se agrupan en el subdirectorio del contenedor. Los contenedores estándar permiten administrar el diseño.

Por ejemplo:

![Propiedades de página con un árbol de dos contenedores, información general y sus contratos, y sus campos de formulario](assets/s_ncs_admin_survey_containers_std_arbo.png)

La posición de las etiquetas se aplica a los elementos situados bajo el contenedor en la jerarquía. Puede sobrecargarse para cada elemento si es necesario. Añada o quite columnas para cambiar el diseño. Consulte [Colocación de los campos en la página](#positioning-the-fields-on-the-page).

En el ejemplo anterior, la renderización es la siguiente:

![Página de formulario procesada con dos contenedores: campos de detalles personales y una lista de casillas de verificación de contrato, además de un botón Validar](assets/s_ncs_admin_survey_containers_std_ex.png)

## Colocación de los campos en la página {#positioning-the-fields-on-the-page}

El diseño del formulario web se define página por página en cada contenedor y se puede sobrecargar si es necesario.

Las páginas se dividen en columnas: cada página contiene un determinado número de columnas. Cada campo de la página ocupa **n** celdas. Los contenedores también ocupan un determinado número de columnas y los campos que contienen ocupan un determinado número de celdas.

De forma predeterminada, las páginas se crean en una única columna y cada elemento ocupa una celda. Esto significa que los campos se muestran uno debajo de otro, cada uno de los cuales ocupa una línea entera, como se muestra a continuación:

![Página de formulario de una sola columna procesada con los campos Género, Nombre, Nombre y Correo electrónico apilados en líneas separadas](assets/s_ncs_admin_survey_container_ex.png)

En el siguiente ejemplo, se ha conservado la configuración predeterminada. La página ocupa una sola columna que incluye cuatro contenedores.

![Propiedades de página con cuatro contenedores y Número de columnas establecido en 1 resaltado](assets/s_ncs_admin_survey_container_ex0.png)

Cada contenedor ocupa una columna y cada elemento ocupa una celda:

![Propiedades del elemento de información con el número de celdas establecido en 1 resaltado en la configuración de visualización](assets/s_ncs_admin_survey_container_ex0a.png)

La renderización es la siguiente:

![Procesamiento de página de una sola columna con cuatro contenedores, cada uno con una columna, apilados verticalmente](assets/s_ncs_admin_survey_container_ex0_rend.png)

Se pueden adaptar los parámetros de visualización para obtener la siguiente renderización:

![Procesamiento de página de dos columnas donde los contenedores 1 y 3 rellenan la columna izquierda y los contenedores 2 y 4 la derecha](assets/s_ncs_admin_survey_container_ex1_rend.png)

En el ejemplo de renderización anterior, cada campo de entrada, título e imagen ocupa una celda en las columnas de los contenedores.

Se puede modificar el formato en cada contenedor. En este ejemplo, se puede extender el contenido del contenedor 4 en dos columnas y distribuir los elementos.

![El contenedor 4 con dos columnas: el título y el cuadro combinado tienen una celda cada uno, la casilla de verificación abarca dos celdas](assets/s_ncs_admin_survey_container_ex2_rend.png)

El título y la lista ocupan una celda cada uno (y, por tanto, una línea completa del contenedor) y la casilla de verificación se extiende por dos celdas. El número de celdas atribuido al campo de entrada se define en la pestaña **[!UICONTROL General]** o en la pestaña **[!UICONTROL Advanced]**, según el tipo de campo:

![Ficha avanzada del elemento checkbox con el número de celdas establecido en 2 en la configuración de visualización](assets/s_ncs_admin_survey_container_ex2.png)

## Definición de la posición de etiquetas {#defining-the-position-of-labels}

Puede definir la alineación de campos y etiquetas en el formulario.

De forma predeterminada, los parámetros de visualización para campos y otro contenido de la página se heredan de la configuración general del formulario, la configuración de la página o la configuración del contenedor principal, si existe.

Los parámetros de visualización globales para todo el formulario se especifican en el cuadro de propiedades del formulario. La pestaña **[!UICONTROL Rendering]** permite seleccionar la posición de las etiquetas.

![Cuadro de diálogo Propiedades del formulario web, ficha Procesamiento, con la lista Posición de la etiqueta: Heredado, Izquierda, Derecha, Arriba, Abajo, Oculto](assets/s_ncs_admin_survey_label_position.png)

Esta posición se puede sobrecargar para cada página, cada contenedor y cada campo, a través de la pestaña **[!UICONTROL Advanced]**.

Se admiten las siguientes alineaciones:

* Heredado: la alineación se hereda del elemento principal (valor predeterminado), es decir, el contenedor principal si existe, o de lo contrario, la página.
* Izquierda/derecha: la etiqueta se coloca a la derecha o a la izquierda del campo,
* Encima/debajo: la etiqueta se coloca encima o debajo del campo,
* Oculta: la etiqueta no se muestra.
