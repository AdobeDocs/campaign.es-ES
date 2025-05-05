---
title: Personalizar la instancia
description: Aprenda a personalizar la instancia
feature: Configuration, Application Settings
role: Developer
level: Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 10%

---

# Personalizar la instancia {#gs-ac-custom}

Aprenda a **personalizar la instancia de Campaign**.

>[!CAUTION]
>
>La personalización de Adobe Campaign está reservada únicamente para usuarios expertos.

## Creación de nuevos campos y esquemas de datos

Adobe Campaign utiliza esquemas de datos para lo siguiente:

* Definir el modo en que los objetos de datos de la aplicación están vinculados a las tablas de bases de datos subyacentes
* Defina vínculos entre los diferentes objetos de datos dentro de la aplicación de Campaign
* Definir y describir los campos individuales incluidos en cada objeto

Por ejemplo, para agregar un campo a una tabla existente, como la tabla de destinatarios (nms:recipient), debe ampliar ese esquema.

Hay dos modos de extensión de tabla disponibles:

* A través de la interfaz, mediante el asistente **Nuevo campo**

  Aprenda a añadir rápidamente un nuevo campo en Campaign en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=es#configuring-campaign-classic){target="_blank"}

* Mediante programación, ampliando el esquema. Aprenda a ampliar un esquema existente en [esta sección](../dev/extend-schema.md).

También puede crear nuevas tablas en la base de datos de Campaign y ampliar el modelo de datos integrado.

Para añadir un tipo de datos completamente nuevo que no existe de forma predeterminada en Adobe Campaign (por ejemplo, una tabla de contratos), puede crear un esquema personalizado directamente. Para obtener más información, consulte [este ejemplo](../dev/create-schema.md#example--creating-a-contract-table).

**Temas relacionados**

Ejemplo de edición de esquema en [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=es#configuring-campaign-classic){target="_blank"}

Caso de uso: vincular un campo a una tabla de referencia existente en [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=es#uc-link){target="_blank"}


## Modificación de los formularios de entrada

Los formularios de entrada de la campaña se pueden adaptar a su implementación. Puede agregar o quitar campos de formulario modificando el contenido XML.

Aprenda a modificar un formulario de entrada existente o a crear un nuevo formulario en [esta sección](../dev/forms.md).

## Personalizar paneles{#gs-custom-dashboards}

La interfaz de Adobe Campaign utiliza muchas aplicaciones web para acceder, administrar e interactuar con destinatarios, envíos, campañas, inventarios, etc. Se visualizan en la interfaz en forma de paneles con una sola página.

Las aplicaciones web integradas se almacenan en la carpeta **Administration > Configuration > Web applications** del explorador.

Aprenda a crear una página de información general en Campaign en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=es#creating-a-single-page-web-application){target="_blank"}


## Personalización de listas y creación de filtros {#gs-lists-and-filters}

Las listas de campañas incluyen filtros predefinidos para facilitar la navegación y la visualización de los datos.

Cuando navega por el árbol del Explorador de Adobe Campaign, los datos contenidos en la base de datos se muestran en listas. Puede filtrar estas listas, ejecutar búsquedas, añadir información, filtrar y ordenar datos.

Obtenga información sobre cómo configurar listas y guardar una configuración de lista en [esta página](../start/campaign-ui.md).

Puede aplicar filtros en estas listas para mostrar solo los datos necesarios para el operador. A continuación, se pueden ejecutar acciones en los datos filtrados. La configuración del filtro permite seleccionar datos de una lista de forma dinámica. Al modificar los datos, los datos filtrados se actualizan.

Obtenga más información acerca de las opciones de filtrado en [esta página](../audiences/create-filters.md).
