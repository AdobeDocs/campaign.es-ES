---
product: Adobe Campaign
title: Concesión de permisos para Campaign v8
description: Obtenga información sobre cómo conceder permisos a Campaign v8
feature: Audiencias
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 4bd67cd3e4e88015d8044f07ca95927b6d7867f3
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 1%

---

# Introducción a los permisos

En Adobe Campaign, los usuarios son **operadores** y los **grupos de operadores** representan funciones de usuario.

Adobe Campaign incluye grupos de operadores integrados, como gestores de campañas o supervisores de flujo de trabajo. Todos los grupos integrados se enumeran en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

Como miembro de un grupo de operadores, un usuario tiene derechos para realizar operaciones, denominadas &quot;Derechos asignados&quot;, y tiene acceso a los datos, que se encuentran en carpetas de la vista **Explorer**. Un operador puede ser miembro de varios grupos de operadores: Los derechos y permisos de acceso son aditivos.

Derechos asignados conceden permisos a:

* Realizar operaciones
Por ejemplo, el botón **Analyze** del editor de envíos está activado para los miembros del grupo **Delivery Operator** que tienen el **Prepare Delivery** asignado derecho

* Acceso a carpetas
La pertenencia a grupos de operadores puede conceder o restringir derechos de acceso a carpetas cambiando la configuración de seguridad de las carpetas. [Obtenga más información en la documentación](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder) de Campaign Classic v7. Por ejemplo, puede afectar a: **Escriba access** para crear nuevas entidades (como envíos, perfiles, etc.), **Read access** para utilizar entidades, **Delete access** para eliminar entidades.

**Obtenga** más información en la documentación de Campaign Classic v7:

[!DNL :arrow_upper_right:] [Derechos asignados integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html)

[!DNL :arrow_upper_right:] [Grupos de operadores integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

[!DNL :arrow_upper_right:] [Pasos para configurar permisos](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html)

[!DNL :arrow_upper_right:] [Configuración de seguridad en carpetas](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder).