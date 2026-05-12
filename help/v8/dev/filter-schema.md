---
title: Filtrado de esquemas de Campaign
description: Aprenda a filtrar esquemas de Campaign
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
TQID: https://experienceleague.adobe.com/2T0OxjyVTM9-lzsOfcaqv81YVtVvrNpprpyC0VLoWgU
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2: id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 401
ht-degree: 2%

---

# Filtrar esquemas{#filter-schemas}

## Filtros del sistema {#system-filters}

Puede filtrar el acceso a esquemas a usuarios específicos, según sus permisos. Los filtros del sistema le permiten administrar los permisos de lectura y escritura de las entidades detalladas en los esquemas, utilizando los parámetros **readAccess** y **writeAccess**.

>[!NOTE]
>
>Esta restricción se aplica solo a los usuarios no técnicos: un usuario técnico, con permisos relacionados o que utilice un flujo de trabajo, podrá recuperar y actualizar datos.

* **readAccess**: proporciona acceso de solo lectura a los datos del esquema.

  **Advertencia**: todas las tablas vinculadas deben estar configuradas con la misma restricción. Esta configuración puede afectar al rendimiento.

* **writeAccess**: proporciona acceso de escritura a los datos del esquema.

Estos filtros se introducen en el nivel principal **element** de los esquemas y, como se muestra en los ejemplos siguientes, se pueden formar para restringir el acceso.

* Restringir permisos de ESCRITURA

  En este caso, el filtro se utiliza para impedir los permisos de ESCRITURA en el esquema a los operadores sin el permiso ADMINISTRACIÓN. Esto significa que solo los administradores tendrán permisos de escritura en las entidades descritas en este esquema.

  ```
  <sysFilter name="writeAccess">      
   <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
  </sysFilter>
  ```

* Restrinja los permisos de LECTURA y ESCRITURA:

  En este caso, el filtro se utiliza para impedir los permisos de LECTURA y ESCRITURA en el esquema para todos los operadores. Solo la cuenta **internal**, representada por la expresión &quot;$(loginId)!=0&quot;, tiene estos permisos.

  ```
  <sysFilter name="readAccess"> 
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  
  <sysFilter name="writeAccess">  
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  ```

  Los posibles valores de atributo **expr** utilizados para definir la condición son TRUE o FALSE.

>[!NOTE]
>
>Si no se especifica ningún filtro, todos los operadores tendrán permisos de lectura y escritura en el esquema.

## Protección de esquemas integrados

De forma predeterminada, solo se puede acceder a los esquemas integrados con permisos de ESCRITURA para operadores con derechos de ADMINISTRACIÓN:

* ncm:publishing
* nl:monitoring
* nms:calendar
* xtk:builder
* xtk:connections
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk:entityOriginal
* xtk:form
* xtk:funcList
* xtk:fusion
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
>Los permisos de LECTURA y ESCRITURA para el esquema **xtk:sessionInfo** solo son accesibles desde la cuenta interna de una instancia de Adobe Campaign.

## Modificación de los filtros del sistema de los esquemas integrados

Los esquemas integrados están protegidos para evitar problemas de compatibilidad con versiones anteriores. Adobe recomienda no modificar los parámetros de esquema predeterminados para garantizar una seguridad óptima.

Sin embargo, en contextos específicos, es posible que tenga que modificar los filtros del sistema de los esquemas integrados. Para realizar esto, siga los pasos a continuación:

1. Cree una extensión para el esquema integrado o abra una extensión existente.
1. Agregue un elemento secundario **`<sysfilter name="<filter name>" _operation="delete"/>`** en el elemento principal para omitir el filtro bajo el mismo en el esquema integrado.
1. Puede agregar un nuevo filtro, tal como se detalla en la sección [Filtros del sistema](#system-filters).
