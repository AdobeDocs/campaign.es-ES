---
title: Introducción a los perfiles
description: Introducción a los perfiles
feature: Profiles, Data Management
role: User
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: ht
source-wordcount: '214'
ht-degree: 100%

---

# Importación de datos en Campaign {#ootb-profiles}

Campaign le ayuda a añadir contactos a la base de datos de Cloud. Puede cargar un archivo, programar y automatizar varias actualizaciones de contacto, recopilar datos en la web o introducir información de perfil directamente en la tabla de destinatarios.

Introducción a los [públicos](audiences.md)

Explicación del [modelo de datos](../dev/datamodel.md) de Campaign

## Importación de perfiles en un flujo de trabajo

Las importaciones de perfil se configuran en plantillas dedicadas ejecutadas a través de flujos de trabajo mediante la actividad **Importación**. Se pueden repetir automáticamente según un programa, por ejemplo, para automatizar el intercambio de datos entre varios sistemas de información. Obtenga más información en [esta sección](../../automation/workflow/recurring-import-workflow.md).

![](assets/import-wf.png)


## Ejecución de importaciones unitarias

Cree y ejecute un trabajo de importación de datos genérico para cargar contactos en la base de datos de Cloud.

![](assets/new-import.png)

Obtenga información sobre cómo ejecutar trabajos de importación unitarios para alimentar la base de datos en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=es){target="_blank"}.

## Recopilación de perfiles mediante aplicaciones web

Utilice Campaign para crear formularios web y recopilar y administrar la información de perfil de forma fácil y eficaz. Puede compartir estos formularios en su sitio web, lo que facilita que sus contactos proporcionen su información. Su información se envía a Campaign para crear su perfil o actualizar su información si ya está presente en la base de datos.

![](assets/web-form-page.png)

Aprenda a crear formularios web en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html?lang=es){target="_blank"}.

**Temas relacionados**

* [Crear públicos](audiences.md)
* [Deduplicación de perfiles](../../automation/workflow/deduplication-merge.md)
* [Enriquecimiento de los datos de perfil](../../automation/workflow/enrich-data.md)
