---
solution: Campaign v8
product: Adobe Campaign
title: Introducción a los perfiles
description: Introducción a los perfiles
feature: Perfiles
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 905003b74a1f875432f08c5c70edf3d0451b861f
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 9%

---

# Importar datos en Campaign {#ootb-profiles}

Campaign le ayuda a añadir contactos a la base de datos de Cloud. Puede cargar un archivo, programar y automatizar varias actualizaciones de contacto, recopilar datos en la web o introducir información de perfil directamente en la tabla de destinatarios.

:bulb: Introducción a [audiencias](audiences.md)
:bulb: Comprender el modelo de datos [de Campaign](../dev/datamodel.md)

## Importación de perfiles en un flujo de trabajo

Las importaciones de perfil se configuran en plantillas dedicadas ejecutadas a través de flujos de trabajo mediante la actividad **Import**. Se pueden repetir automáticamente según un programa, por ejemplo, para automatizar el intercambio de datos entre varios sistemas de información. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html).

![](assets/import-wf.png)

Obtenga más información en la documentación de Campaign Classic v7:

:arrow_upper_right: [Introducción a importaciones y exportaciones](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html)

:arrow_upper_right: [Prácticas recomendadas de importación y exportación](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html)

:arrow_upper_right: [Configurar y ejecutar una importación](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html)

## Ejecutar importaciones unitarias

Cree y ejecute un trabajo de importación de datos genérico para cargar contactos en la base de datos de Cloud.

![](assets/new-import.png)

:arrow_upper_right: Obtenga información sobre cómo ejecutar trabajos de importación unitarios para alimentar la base de datos en [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html).

## Recopilación de perfiles mediante aplicaciones web

Utilice Campaign para crear formularios web y recopilar y administrar la información de perfil de forma fácil y eficaz. Puede compartir estos formularios en su sitio web, lo que facilita que sus contactos proporcionen su información. Su información se envía a Campaign para crear su perfil o actualizar su información si ya está presente en la base de datos.

![](assets/web-form-page.png)

:arrow_upper_right: Aprenda a crear formularios web en [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html).

**Temas relacionados**

* [Crear audiencias](audiences.md)
* [Deduplicación de perfiles](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html)
* [Enriquecimiento de los datos de perfil](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)
