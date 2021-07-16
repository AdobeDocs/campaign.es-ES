---
solution: Campaign
product: Adobe Campaign
title: Concesión de permisos para Campaign v8
description: Obtenga información sobre cómo conceder permisos a Campaign v8
feature: Audiencias
role: Data Engineer
level: Beginner
source-git-commit: 22f47bed75d78684c85471330aca7dadafb9ed65
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 13%

---

# Introducción a los permisos

En Adobe Campaign, los usuarios son **operadores** y los **grupos de operadores** representan funciones de usuario.

Un operador es un usuario de Adobe Campaign que tiene permisos para iniciar sesión y realizar acciones. De forma predeterminada, los operadores se almacenan en el nodo **[!UICONTROL Administration > Access management > Operators]**.

Adobe Campaign incluye grupos de operadores integrados, como gestores de campañas o supervisores de flujo de trabajo. Todos los grupos integrados se enumeran en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}.

Como miembro de un grupo de operadores, un usuario tiene derechos para realizar operaciones, denominadas &quot;Derechos asignados&quot;, y tiene acceso a los datos, que se encuentran en carpetas de la vista **Explorer**. Un operador puede ser miembro de varios grupos de operadores: Los derechos y permisos de acceso son aditivos.

Derechos asignados conceden permisos a:

* Realizar operaciones
Por ejemplo, el botón **Analyze** del editor de envíos está activado para los miembros del grupo **Delivery Operator** que tienen el **Prepare Delivery** asignado derecho

* Acceso a carpetas
La pertenencia a grupos de operadores puede conceder o restringir derechos de acceso a carpetas cambiando la configuración de seguridad de las carpetas. [Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}. Por ejemplo, puede afectar a: **Escriba access** para crear nuevas entidades (como envíos, perfiles, etc.), **Read access** para utilizar entidades, **Delete access** para eliminar entidades.

## Zonas de seguridad

Cada operador debe estar vinculado a una zona para iniciar sesión en una instancia y la IP del operador debe incluirse en las direcciones o conjuntos de direcciones definidos en la zona de seguridad. La configuración de la zona de seguridad se realiza en el archivo de configuración del servidor de Adobe Campaign.

Los operadores están vinculados a una zona de seguridad desde su perfil en la consola, accesible en el nodo **[!UICONTROL Administration > Access management > Operators]**.

?? Como usuario de Cloud Services administrados, Adobe establece las zonas de seguridad por usted. Para obtener más información, [póngase en contacto con el Adobe](https://helpx.adobe.com/es/enterprise/admin-guide.html?lang=es/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}.

**Obtenga más información en la documentación de Campaign Classic v7**

* [Derechos asignados integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

* [Grupos de operadores integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [Pasos para configurar permisos](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}
