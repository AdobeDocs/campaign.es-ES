---
product: Adobe Campaign
title: Concesión de permisos para Campaign v8
description: Obtenga información sobre cómo conceder permisos a Campaign v8
feature: Audiencias
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 7%

---

# Introducción a los permisos

En Adobe Campaign, los usuarios son **operadores** y los **grupos de operadores** representan funciones de usuario.

Adobe Campaign incluye grupos de operadores integrados, como gestores de campañas o supervisores de flujo de trabajo. Todos los grupos integrados se enumeran en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

Como miembro de un grupo de operadores, un usuario tiene derechos para realizar operaciones, denominadas &quot;Derechos asignados&quot;, y tiene acceso a los datos, que se encuentran en carpetas de la vista **Explorer**. Un operador puede ser miembro de varios grupos de operadores: Los derechos y permisos de acceso son aditivos.

Derechos asignados conceden permisos a:

* Realizar operaciones
Por ejemplo, el botón **Analyze** del editor de envíos está activado para los miembros del grupo **Delivery Operator** que tienen el **Prepare Delivery** asignado derecho

* Acceso a carpetas
La pertenencia a grupos de operadores puede conceder o restringir derechos de acceso a carpetas cambiando la configuración de seguridad de las carpetas. [Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}. Por ejemplo, puede afectar a: **Escriba access** para crear nuevas entidades (como envíos, perfiles, etc.), **Read access** para utilizar entidades, **Delete access** para eliminar entidades.

**** Obtenga más información en la documentación de Campaign Classic v7:

↗️ [Derechos asignados integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

↗️ [Grupos de operadores integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

↗️ [Pasos para configurar permisos](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}

↗️ [Configuración de seguridad en carpetas](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}