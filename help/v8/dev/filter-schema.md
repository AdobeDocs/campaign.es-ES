---
title: Filtrado de esquemas de campaña
description: Obtenga información sobre cómo filtrar esquemas de Campaign
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Filtrar esquemas{#filter-schemas}

## Filtros del sistema {#system-filters}

Puede filtrar el acceso al esquema para usuarios específicos, según sus permisos. Los filtros de sistema permiten administrar los permisos de lectura y escritura de las entidades detalladas en los esquemas mediante **readAccess** y **writeAccess** parámetros.

>[!NOTE]
>
>Esta restricción solo se aplica a usuarios no técnicos: un usuario técnico, con permisos relacionados o utilizando un flujo de trabajo, podrá recuperar y actualizar datos.

* **readAccess**: proporciona acceso de solo lectura a los datos del esquema.

   **Advertencia** - Todas las tablas vinculadas deben configurarse con la misma restricción. Esta configuración puede afectar al rendimiento.

* **writeAccess**: proporciona acceso de escritura a los datos del esquema.

Estos filtros se introducen en la variable principal **element** de los esquemas y, como se muestra en los ejemplos siguientes, se pueden formar para restringir el acceso.

* Restringir permisos de ESCRITURA

   En este caso, el filtro se utiliza para no permitir permisos WRITE en el esquema para operadores sin el permiso ADMINISTRATION. Esto significa que solo los administradores tendrán permisos de escritura en las entidades descritas por este esquema.

   ```
   <sysFilter name="writeAccess">      
    <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
   </sysFilter>
   ```

* Restringir permisos de lectura y escritura:

   En este caso, el filtro se utiliza para no permitir permisos de lectura y escritura en el esquema para todos los operadores. Solo el **internal** cuenta, representada por la expresión &quot;$(loginId)!=0&quot;, tiene estos permisos.

   ```
   <sysFilter name="readAccess"> 
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   
   <sysFilter name="writeAccess">  
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   ```

   Posible **expr** los valores de atributo utilizados para definir la condición son TRUE o FALSE.

>[!NOTE]
>
>Si no se especifica ningún filtro, todos los operadores tendrán permisos de lectura y escritura en el esquema.

## Esquemas integrados de Protect

De forma predeterminada, los esquemas integrados solo son accesibles con permisos WRITE para operadores con derechos de ADMINISTRACIÓN:

* ncm:publishing
* nl:monitorización
* nms:calendar
* xtk:builder
* xtk:conexiones
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk:entityOriginal
* xtk:form
* xtk:funcList
* xtk:fusión
* xtk:image
* xtk:javascript
* xtk:jssp
* xtk:jst
* xtk:navtree
* xtk:operatorGroup
* xtk:package
* xtk:queryDef
* xtk:resourceMenu
* xtk:rights
* xtk:schema
* xtk:scriptContext
* xtk:specFile
* xtk:sql
* xtk:sqlSchema
* xtk:srcSchema
* xtk:strings
* xtk:xslt

>[!CAUTION]
>
>Permisos READ y WRITE para la variable **xtk:sessionInfo** solo es accesible desde la cuenta interna de una instancia de Adobe Campaign.

## Modificación de los filtros del sistema de los esquemas integrados

Los esquemas integrados están protegidos para evitar problemas de compatibilidad con versiones anteriores. Adobe recomienda no modificar los parámetros de esquema predeterminados para garantizar una seguridad óptima.

Sin embargo, en contextos específicos, es posible que tenga que modificar los filtros del sistema de los esquemas integrados. Para ello, siga los pasos a continuación:

1. Cree una extensión para el esquema integrado o abra una extensión existente.
1. Agregar un elemento secundario **`<sysfilter name="<filter name>" _operation="delete"/>`** en el elemento principal para ignorar el filtro debajo del mismo en el esquema integrado.
1. Puede agregar un filtro nuevo, tal como se detalla en la sección [Filtros del sistema](#system-filters) para obtener más información.
