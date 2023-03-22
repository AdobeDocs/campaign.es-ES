---
title: Concesión de permisos para Campaign v8
description: Obtenga información sobre cómo conceder permisos a Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 13%

---

# Introducción a los permisos

En Adobe Campaign, los usuarios son **operadores** y **grupos de operadores** representan funciones de usuario.

Un operador es un usuario de Adobe Campaign que tiene permisos para iniciar sesión y realizar acciones. De forma predeterminada, los operadores se almacenan en el nodo **[!UICONTROL Administration > Access management > Operators]**.

Adobe Campaign incluye grupos de operadores integrados, como gestores de campañas o supervisores de flujo de trabajo. Obtenga más información sobre los permisos en [esta sección](../start/gs-permissions.md)

Como miembro de un grupo de operadores, un usuario tiene derechos para realizar operaciones, denominadas &quot;Derechos asignados&quot;, y tiene acceso a los datos, que se encuentran en carpetas de la **Explorer** vista. Un operador puede ser miembro de varios grupos de operadores: Los derechos y permisos de acceso son aditivos.

Derechos asignados conceden permisos a:

* Realizar operaciones Por ejemplo, la variable **Analizar** en el editor de entregas está activado para los miembros del **Operador de envío** grupo que tenga la variable **Preparación de la entrega** Derecho asignado

* El acceso a las carpetas La pertenencia a grupos de operadores puede conceder o restringir derechos de acceso a las carpetas cambiando la configuración de seguridad de las carpetas. Obtenga más información en [esta página](../start/folder-permissions.md). Por ejemplo, puede afectar a: **Acceso de escritura** para crear nuevas entidades (como entregas, perfiles, etc.), **Acceso de lectura** para utilizar entidades, **Eliminar acceso** para eliminar entidades.

## Zonas de seguridad

Cada operador debe estar vinculado a una zona para iniciar sesión en una instancia y la IP del operador debe incluirse en las direcciones o conjuntos de direcciones definidos en la zona de seguridad. La configuración de la zona de seguridad se realiza en el archivo de configuración del servidor de Adobe Campaign.

Los operadores están vinculados a una zona de seguridad desde su perfil en la consola, accesible en la **[!UICONTROL Administration > Access management > Operators]** nodo .

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, Adobe establece las zonas de seguridad por usted. Para obtener más información, [Adobe de contacto](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Más información**

* [Derechos asignados integrados](../start/gs-permissions.md)

* [Pasos para configurar permisos](../start/manage-permissions.md)
