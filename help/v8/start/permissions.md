---
title: Concesión de permisos para Campaign v8
description: Obtenga información sobre cómo conceder permisos a Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 13%

---

# Introducción a los permisos

En Adobe Campaign, los usuarios son **operadores** y **grupos de operadores** representan funciones de usuario.

Un operador es un usuario de Adobe Campaign que tiene permisos para iniciar sesión y realizar acciones. De forma predeterminada, los operadores se almacenan en el nodo **[!UICONTROL Administration > Access management > Operators]**.

Adobe Campaign incluye grupos de operadores integrados, como gestores de campañas o supervisores de flujo de trabajo. Todos los grupos integrados se incluyen en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}.

Como miembro de un grupo de operadores, un usuario tiene derechos para realizar operaciones, denominadas &quot;Derechos asignados&quot;, y tiene acceso a los datos, que se encuentran en carpetas de la **Explorer** vista. Un operador puede ser miembro de varios grupos de operadores: Los derechos y permisos de acceso son aditivos.

Derechos asignados conceden permisos a:

* Realizar operaciones Por ejemplo, la variable **Analizar** en el editor de entregas está activado para los miembros del **Operador de envío** grupo que tenga la variable **Preparación de la entrega** Derecho asignado

* El acceso a las carpetas La pertenencia a grupos de operadores puede conceder o restringir derechos de acceso a las carpetas cambiando la configuración de seguridad de las carpetas. [Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}. Por ejemplo, puede afectar a: **Acceso de escritura** para crear nuevas entidades (como entregas, perfiles, etc.), **Acceso de lectura** para utilizar entidades, **Eliminar acceso** para eliminar entidades.

## Zonas de seguridad

Cada operador debe estar vinculado a una zona para iniciar sesión en una instancia y la IP del operador debe incluirse en las direcciones o conjuntos de direcciones definidos en la zona de seguridad. La configuración de la zona de seguridad se realiza en el archivo de configuración del servidor de Adobe Campaign.

Los operadores están vinculados a una zona de seguridad desde su perfil en la consola, accesible en la **[!UICONTROL Administration > Access management > Operators]** nodo .

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, Adobe establece las zonas de seguridad por usted. Para obtener más información, [Adobe de contacto](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}.

**Obtenga más información en la documentación de Campaign Classic v7**

* [Derechos asignados integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

* [Grupos de operadores integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [Pasos para configurar permisos](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}
