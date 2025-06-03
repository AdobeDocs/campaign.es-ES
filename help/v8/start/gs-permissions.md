---
title: Introducción a los permisos en Campaign v8
description: Obtenga información sobre los pasos para definir permisos en Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 17%

---

# Introducción a los permisos{#gs-permissions}

Adobe Campaign permite definir y administrar los derechos asignados a los usuarios. Se trata de un conjunto de derechos y restricciones que autorizan o niegan:

* Acceder a determinadas funciones
* Acceder a determinados datos
* Acceder a determinadas acciones (crear, modificar, eliminar)

Estos permisos se definen combinando permisos de grupos de operadores, derechos asignados y permisos en carpetas.

En Adobe Campaign, los usuarios son **operadores** y **grupos de operadores** representan funciones de usuario. Un operador es un usuario de Adobe Campaign que tiene permisos para iniciar sesión y realizar acciones. Los usuarios se crean en Admin Console. Los permisos se aplican a perfiles de usuario o grupos de usuarios. Existen dos tipos de permisos que puede conceder:

* Puede definir grupos de operadores a los que desee atribuir derechos y luego asociar los operadores con uno o varios grupos. Esto permite reutilizar derechos y hacer que los perfiles de operador sean más coherentes. También facilita la administración y el mantenimiento de los perfiles de usuario.
* Puede asignar derechos asignados directamente a los usuarios, en algunos casos para sobrecargar los derechos asignados a través de grupos.

## Pasos clave para conceder permisos{#key-steps-permissions}

Como administrador de productos, puede conceder permisos a los usuarios de su organización. Los permisos se conceden mediante Adobe Admin Console y la consola del cliente de Campaign. Los usuarios inician sesión en Adobe Campaign con su Adobe ID. Aprenda a conectarse a Adobe Campaign en [esta página](connect.md).

Los pasos clave son los siguientes:

* **Paso 1**: Defina sus grupos de operadores y asígneles permisos en la consola del cliente de Campaign. [Más información](manage-permissions.md#create-product-profile).
Tenga en cuenta que también puede utilizar grupos de operadores integrados para empezar con. Estos grupos predeterminados y sus permisos se enumeran en [esta sección](manage-permissions.md#ootb-productprofiles).
* **Paso 2**: Cree perfiles de producto en Adobe Admin Console que coincidan con esos grupos. [Más información](manage-permissions.md#create-product-profile).
Puede utilizar perfiles de producto integrados para empezar con. [Más información](manage-permissions.md#ootb-productprofiles).
* **Paso 3**: Cree usuarios en Adobe Admin Console y asígnelos a un perfil de producto. [Más información](manage-permissions.md#add-users).
* **Paso 4** (opcional): asigne permisos en las carpetas. [Más información](manage-permissions.md#ootb-productprofiles).

## Acerca de Admin Console{#gs-admin-console}

Adobe Admin Console es una ubicación central para administrar las autorizaciones de Adobe en toda la organización. Solo pueden acceder a él los administradores de productos.

Utilice Admin Console para añadir usuarios, crear y asignar perfiles de producto (que son grupos de funciones de operador).

Aprenda a agregar usuarios en [esta página](manage-permissions.md#add-users).

## Acerca de los perfiles de producto{#ootb-product-profiles}

Los perfiles de producto son grupos de productos y servicios que puede asignar a los usuarios. En Adobe Experience Cloud, los permisos se basan en el perfil de un producto, no en el usuario. Sin embargo, puede delegar derechos administrativos a usuarios específicos.

En Admin Console, cada **perfil de producto** de Adobe Experience Cloud para Campaign está asociado a un **grupo de operadores** en la consola del cliente de Campaign.

Aprenda a crear y asignar perfiles de producto en [esta página](manage-permissions.md#create-a-product-profile).

## Derechos asignados de Campaign{#named-rights}

Como miembro de un perfil de producto (es decir, grupo de operadores), un usuario tiene derechos para realizar operaciones, llamados &quot;derechos asignados&quot;, y tiene acceso de lectura o escritura a los datos. Un operador puede ser miembro de varios grupos de operadores: los derechos y permisos de acceso son aditivos.

Obtenga más información acerca de los derechos asignados en [esta sección](manage-permissions.md#use-named-rights).
