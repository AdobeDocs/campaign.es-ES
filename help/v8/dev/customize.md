---
title: Personalizar la instancia
description: Obtenga información sobre cómo personalizar la instancia
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 22%

---

# Personalizar la instancia{#gs-ac-custom}

Obtenga información sobre cómo **personalizar la instancia de Campaign**

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

* A través de la interfaz, utilizando el asistente **New field**

   ↗️ Aprenda a añadir rápidamente un nuevo campo en Campaign en [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)

* Programáticamente, ampliando el esquema

   ?? Aprenda a ampliar un esquema existente en [esta sección](../dev/extend-schema.md).


También puede crear nuevas tablas en la base de datos de Campaign y ampliar el modelo de datos integrado.

Para añadir un tipo de datos completamente nuevo que no exista de forma predeterminada en Adobe Campaign (por ejemplo, una tabla de contratos), puede crear un esquema personalizado directamente. Para obtener más información, consulte [este ejemplo](../dev/create-schema.md#example--creating-a-contract-table).

**Temas relacionados**

↗️ Ejemplo de edición de esquema en la documentación de [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)

↗️ caso de uso: vincular un campo a una tabla de referencia existente en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)


## Modificación de los formularios de entrada

Los formularios de entrada de Campaign se pueden adaptar a su implementación. Puede agregar o quitar campos de formulario modificando el contenido XML.

?? Aprenda a modificar un formulario de entrada existente o crear un nuevo formulario en [esta sección](../dev/forms.md).

## Personalizar tableros{#gs-custom-dashboards}

La interfaz de Adobe Campaign utiliza muchas aplicaciones web para acceder, gestionar e interactuar con destinatarios, envíos, campañas, inventarios, etc. Se visualizan en la interfaz en forma de paneles con una sola página.

Las aplicaciones web listas para su uso se almacenan en el nodo Administration > Configuration > Web applications.

↗️ Aprenda a crear una página de información general en Campaign en [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)


## Personalización de listas y creación de filtros {#gs-lists-and-filters}

### Acceso a datos de tableros

Las listas de campañas incluyen filtros predefinidos para facilitar la navegación y la visualización de datos.

↗️ Obtenga más información sobre las opciones de filtrado en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)


### Acceso a datos desde el Explorador

Cuando navega por el árbol del Explorador de Adobe Campaign, los datos contenidos en la base de datos se muestran en listas. Puede filtrar estas listas, ejecutar búsquedas, añadir información, filtrar y ordenar datos.

↗️ Obtenga información sobre cómo configurar listas y guardar una configuración de lista en [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)


Puede aplicar filtros en estas listas para mostrar solo los datos que necesita el operador. A continuación, se pueden ejecutar acciones en los datos filtrados. La configuración del filtro permite seleccionar datos de una lista de forma dinámica. Al modificar los datos, los datos filtrados se actualizan.

↗️ Aprenda a filtrar los datos en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)
