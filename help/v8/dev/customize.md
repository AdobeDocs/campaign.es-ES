---
title: Personalizar la instancia
description: Obtenga información sobre cómo personalizar la instancia
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 22%

---

# Personalizar la instancia{#gs-ac-custom}

Obtenga información sobre cómo **Personalización de la instancia de Campaign**.

>[!CAUTION]
>
>La personalización de Adobe Campaign está reservada para usuarios expertos.

## Crear nuevos campos de datos y esquemas

Adobe Campaign utiliza esquemas de datos para:

* Definir el modo en que los objetos de datos de la aplicación están vinculados a las tablas de bases de datos subyacentes
* Definir vínculos entre los diferentes objetos de datos dentro de la aplicación de Campaign
* Definir y describir los campos individuales incluidos en cada objeto

Por ejemplo, para añadir un campo a una tabla existente, como la tabla de destinatarios (nms:recipient), debe ampliar ese esquema.

Hay dos modos de extensión de tabla disponibles:

* A través de la interfaz, utilizando la variable **Campo nuevo** asistente

   Aprenda a añadir rápidamente un nuevo campo en Campaign en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic){target="_blank"}

* Programáticamente, ampliando el esquema. Obtenga información sobre cómo ampliar un esquema existente en [esta sección](../dev/extend-schema.md).

También puede crear nuevas tablas en la base de datos de Campaign y ampliar el modelo de datos integrado.

Para añadir un tipo de datos completamente nuevo que no exista de forma predeterminada en Adobe Campaign (por ejemplo, una tabla de contratos), puede crear un esquema personalizado directamente. Para obtener más información, consulte [este ejemplo](../dev/create-schema.md#example--creating-a-contract-table).

**Temas relacionados**

![](../assets/do-not-localize/book.png) Ejemplo de edición de esquema en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic){target="_blank"}

![](../assets/do-not-localize/book.png) Caso de uso: vincular un campo a una tabla de referencia existente en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link){target="_blank"}


## Modificación de los formularios de entrada

Los formularios de entrada de Campaign se pueden adaptar a su implementación. Puede agregar o quitar campos de formulario modificando el contenido XML.

Obtenga información sobre cómo modificar un formulario de entrada existente o crear un nuevo formulario en [esta sección](../dev/forms.md).

## Personalizar tableros{#gs-custom-dashboards}

La interfaz de Adobe Campaign utiliza muchas aplicaciones web para acceder, gestionar e interactuar con destinatarios, envíos, campañas, inventarios, etc. Se visualizan en la interfaz en forma de paneles con una sola página.

Las aplicaciones web incorporadas se almacenan en la variable **Administración > Configuración > Aplicaciones web** de Explorer.

Obtenga información sobre cómo crear una página de información general en Campaign en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application){target="_blank"}


## Personalización de listas y creación de filtros {#gs-lists-and-filters}

Las listas de campañas incluyen filtros predefinidos para facilitar la navegación y la visualización de datos.

Cuando navega por el árbol del Explorador de Adobe Campaign, los datos contenidos en la base de datos se muestran en listas. Puede filtrar estas listas, ejecutar búsquedas, añadir información, filtrar y ordenar datos.

Obtenga información sobre cómo configurar listas y guardar una configuración de lista en [esta página](../start/campaign-ui.md).

Puede aplicar filtros en estas listas para mostrar solo los datos que necesita el operador. A continuación, se pueden ejecutar acciones en los datos filtrados. La configuración del filtro permite seleccionar datos de una lista de forma dinámica. Al modificar los datos, los datos filtrados se actualizan.

Obtenga más información sobre las opciones de filtrado en [esta página](../audiences/create-filters.md).
