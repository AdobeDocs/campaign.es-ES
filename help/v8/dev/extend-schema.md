---
solution: Campaign Classic
product: campaign
title: Ampliación de esquemas de Campaign
description: Descubra cómo ampliar los esquemas de Campaign
translation-type: tm+mt
source-git-commit: f1aed22d04bc0170b533bc088bb1a8e187b44dce
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---

# Ampliar un esquema{#extend-schemas}

Como usuario técnico, puede personalizar el modelo de datos de Campaign para satisfacer las necesidades de su implementación: añadir elementos a un esquema existente, modificar un elemento de un esquema o eliminar elementos.

Los pasos clave para personalizar el modelo de datos de Campaign son:

1. Crear un esquema de extensión
1. Actualización de la base de datos de Campaign
1. Adaptación del formulario de entrada

>[!CAUTION]
>El esquema integrado no debe modificarse directamente. Si necesita adaptar un esquema integrado, debe ampliarlo.

:bulb: Para comprender mejor las tablas integradas de Campaign y su interacción, consulte [esta página](datamodel.md).

Para ampliar un esquema, siga los pasos a continuación:

1. Vaya a la carpeta **[!UICONTROL Administration > Configuration > Data schemas]** en el Explorador.
1. Haga clic en el botón **New** y seleccione **[!UICONTROL Extend the data in a table using an extension schema]**.

   ![](assets/extend-schema-option.png)

1. Identifique el esquema integrado que desea ampliar y selecciónelo.

   ![](assets/extend-schema-select.png)

   Por convención, asigne el mismo nombre al esquema de extensión que al esquema integrado y utilice un espacio de nombres personalizado.

   ![](assets/extend-schema-validate.png)

1. Una vez en el editor de esquemas, añada los elementos que necesite utilizando el menú contextual y guarde.

   ![](assets/extend-schema-edit.png)

   En el siguiente ejemplo, agregamos el atributo Membership Year , establecemos un límite de longitud para los apellidos (este límite sobrescribirá el predeterminado) y eliminamos la fecha de nacimiento del esquema integrado.

   ```
   <srcSchema created="YY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
   <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
           name="recipient">
   <attribute name="Membership Year" label="memberYear" type="long"/>
   <attribute length="50" name="lastName"/>
   <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema> 
   ```

1. Actualice la estructura de la base de datos para aplicar los cambios. [Obtenga más información](update-database-structure.md)
1. Una vez implementados los cambios en la base de datos, se puede adaptar el formulario de entrada de destinatarios para que los cambios sean visibles. [Obtenga más información](forms.md)