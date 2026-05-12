---
title: Personalizar la instancia
description: Aprenda a personalizar la instancia
feature: Configuration, Application Settings
role: Developer
level: Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
TQID: https://experienceleague.adobe.com/HPOVcNhDJCNRMwYiEsXUCQ-p-63qM6T-Yz0BDVp4P-8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 525
ht-degree: 5%

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

  Aprenda a añadir rápidamente un nuevo campo en Campaign en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html#configuring-campaign-classic){target="_blank"}

* Mediante programación, ampliando el esquema. Aprenda a ampliar un esquema existente en [esta sección](../dev/extend-schema.md).

También puede crear nuevas tablas en la base de datos de Campaign y ampliar el modelo de datos integrado.

Para añadir un tipo de datos completamente nuevo que no existe de forma predeterminada en Adobe Campaign (por ejemplo, una tabla de contratos), puede crear un esquema personalizado directamente. Para obtener más información, consulte [este ejemplo](../dev/create-schema.md#example--creating-a-contract-table).

**Temas relacionados**

Ejemplo de edición de esquema en [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#configuring-campaign-classic){target="_blank"}

Caso de uso: vincular un campo a una tabla de referencia existente en [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#uc-link){target="_blank"}


## Modificación de los formularios de entrada

Los formularios de entrada de la campaña se pueden adaptar a su implementación. Puede agregar o quitar campos de formulario modificando el contenido XML.

Aprenda a modificar un formulario de entrada existente o a crear un nuevo formulario en [esta sección](../dev/forms.md).

## Personalizar paneles{#gs-custom-dashboards}

La interfaz de Adobe Campaign utiliza muchas aplicaciones web para acceder, administrar e interactuar con destinatarios, envíos, campañas, inventarios, etc. Se visualizan en la interfaz en forma de paneles con una sola página.

Las aplicaciones web integradas se almacenan en la carpeta **Administration > Configuration > Web applications** del explorador.

Aprenda a crear una página de información general en Campaign en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html#creating-a-single-page-web-application){target="_blank"}


## Personalización de listas y creación de filtros {#gs-lists-and-filters}

Las listas de campañas incluyen filtros predefinidos para facilitar la navegación y la visualización de los datos.

Cuando navega por el árbol del Explorador de Adobe Campaign, los datos contenidos en la base de datos se muestran en listas. Puede filtrar estas listas, ejecutar búsquedas, añadir información, filtrar y ordenar datos.

Obtenga información sobre cómo configurar listas y guardar una configuración de lista en [esta página](../start/campaign-ui.md).

Puede aplicar filtros en estas listas para mostrar solo los datos necesarios para el operador. A continuación, se pueden ejecutar acciones en los datos filtrados. La configuración del filtro permite seleccionar datos de una lista de forma dinámica. Al modificar los datos, los datos filtrados se actualizan.

Obtenga más información acerca de las opciones de filtrado en [esta página](../audiences/create-filters.md).
