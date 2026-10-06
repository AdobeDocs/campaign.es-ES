---
title: Concesión de permisos a Campaign v8
description: Obtenga información sobre cómo conceder permisos a Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 14%
---
# Introducción a los permisos

En Adobe Campaign, los usuarios son **operadores** y **grupos de operadores** representan funciones de usuario.

Un operador es un usuario de Adobe Campaign que tiene permisos para iniciar sesión y realizar acciones. De forma predeterminada, los operadores se almacenan en el nodo **[!UICONTROL Administration > Access management > Operators]**.

Adobe Campaign incluye grupos de operadores integrados, como administradores de campañas o supervisores de flujos de trabajo. Obtenga más información sobre los permisos en [esta sección](../start/gs-permissions.md)

Como miembro de un grupo de operadores, un usuario tiene derechos para realizar operaciones, denominadas &quot;Derechos asignados&quot;, y acceso a los datos, que se encuentran en las carpetas de la vista **Explorer**. Un operador puede ser miembro de varios grupos de operadores: los derechos y permisos de acceso son aditivos.

Derechos asignados: Conceda permisos a:

* Realizar operaciones
Por ejemplo, el botón **Analizar** del editor de envíos está activado para los miembros del grupo **Operador de envíos** que tienen el derecho asignado **Preparar envío**

* Acceso a carpetas
La pertenencia a grupos de operadores puede conceder o restringir derechos de acceso a las carpetas cambiando la configuración de seguridad de las carpetas. Obtenga más información en [esta página](../start/folder-permissions.md). Por ejemplo, puede afectar a: **Acceso de escritura** para crear nuevas entidades (como envíos, perfiles, etc.), **Acceso de lectura** para usar entidades, **Acceso de eliminación** para eliminar entidades.

## Zonas de seguridad

Cada operador debe estar vinculado a una zona para iniciar sesión en una instancia y la IP del operador debe incluirse en las direcciones o conjuntos de direcciones definidos en la zona de seguridad. La configuración de la zona de seguridad se realiza en el archivo de configuración del servidor de Adobe Campaign.

Los operadores están vinculados a una zona de seguridad desde su perfil en la consola, a la que se puede acceder desde el nodo **[!UICONTROL Administration > Access management > Operators]**.

>[!NOTE]
>
>Como usuario de Cloud Services administrados, Adobe establece las zonas de seguridad por usted. Para obtener más información, [comuníquese con Adobe](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Más información**

* [Derechos asignados integrados](../start/gs-permissions.md)

* [Pasos para configurar los permisos](../start/manage-permissions.md)
