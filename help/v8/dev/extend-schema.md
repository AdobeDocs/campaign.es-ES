---
title: Ampliación de esquemas de Campaign
description: Obtenga información sobre cómo ampliar los esquemas de Campaign
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e4dcb228-0683-437a-88cd-bd7ed33da921
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# Ampliación de un esquema{#extend-schemas}

Como usuario técnico, puede personalizar el modelo de datos de Campaign para satisfacer las necesidades de la implementación: añadir elementos a un esquema existente, modificar un elemento de un esquema o eliminar elementos.

Los pasos clave para personalizar el modelo de datos de Campaign son:

1. Creación de un esquema de extensión
1. Actualizar base de datos de Campaign
1. Adaptación del formulario de entrada

>[!CAUTION]
>El esquema integrado no debe modificarse directamente. Si necesita adaptar un esquema integrado, debe ampliarlo.

![](../assets/do-not-localize/glass.png) Para comprender mejor las tablas integradas de Campaign y su interacción, consulte [esta página](datamodel.md). Consulte también recomendaciones al crear un nuevo esquema en [esta página](create-schema.md).

Para ampliar un esquema, siga los pasos a continuación:

1. Vaya a **[!UICONTROL Administration > Configuration > Data schemas]** en el Explorador.
1. Haga clic en **Nuevo** y seleccione **[!UICONTROL Extend the data in a table using an extension schema]**.

   ![](assets/extend-schema-option.png)

1. Identifique el esquema integrado para ampliarlo y seleccionarlo.

   ![](assets/extend-schema-select.png)

   De forma predeterminada, asigne al esquema de extensión el mismo nombre que al esquema integrado y utilice un área de nombres personalizada.  Tenga en cuenta que algunas áreas de nombres solo son internas. [Más información](schemas.md#reserved-namespaces)

   ![](assets/extend-schema-validate.png)

1. Una vez en el editor de esquemas, añada los elementos que necesite mediante el menú contextual y guarde.

   ![](assets/extend-schema-edit.png)

   En el siguiente ejemplo, agregamos el **MembershipYear** , establezca un límite de longitud para el apellido (este límite sobrescribirá el predeterminado) y elimine la fecha de nacimiento del esquema integrado.

   ![](assets/extend-schema-sample.png)

   ```
   <srcSchema created="YYYY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YYYY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
    <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">
       <attribute label="Member since" name="MembershipYear" type="long"/>
       <attribute length="50" name="lastName"/>
       <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema>
   ```

1. Desconéctese y vuelva a conectarse a Campaign para comprobar la actualización de la estructura de esquema en **[!UICONTROL Structure]** pestaña.

   ![](assets/extend-schema-structure.png)

1. Actualice la estructura de la base de datos para aplicar los cambios. [Más información](update-database-structure.md)

1. Una vez implementados los cambios en la base de datos, se puede adaptar el formulario de entrada de destinatario para que los cambios sean visibles. [Más información](forms.md)
