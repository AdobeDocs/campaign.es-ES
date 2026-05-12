---
title: Creación de un nuevo esquema en Campaign
description: Obtenga información sobre cómo crear un nuevo esquema en Campaign
feature: Schema Extension, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: 796af848-b537-4b8d-a601-fe0628a1fc83
TQID: https://experienceleague.adobe.com/Dg-EjmzC6bY4nnsIWmEe-XE4xdWxukCbIfNBxXooGVY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 2%

---

# Creación de un nuevo esquema {#create-new-schema}

Para editar, crear y configurar los esquemas, haga clic en el nodo **[!UICONTROL Administration > Configuration > Data schemas]** de la consola del cliente de Adobe Campaign.

>[!NOTE]
>
>Solo un administrador de la consola de Adobe Campaign puede eliminar esquemas de datos integrados.

![](assets/schema_navtree.png)

La pestaña **[!UICONTROL Edit]** muestra el contenido XML de un esquema:

![](assets/schema_edition.png)

>[!NOTE]
>
>El control de edición &quot;Name&quot; permite introducir la clave de esquema formada por el nombre y el área de nombres. Los atributos &quot;name&quot; y &quot;namespace&quot; del elemento raíz del esquema se actualizan automáticamente en la zona de edición XML del esquema. Tenga en cuenta que algunas áreas de nombres solo son internas. [Más información](schemas.md#reserved-namespaces)

La ficha **[!UICONTROL Preview]** genera automáticamente el esquema extendido:

![](assets/schema_edition2.png)

>[!NOTE]
>
>Cuando se guarda el esquema de origen, se inicia automáticamente la generación del esquema ampliado.

Si necesita comprobar la estructura completa de un esquema, puede utilizar la ficha **[!UICONTROL Preview]**. Si el esquema se ha ampliado, podrá visualizar todas sus extensiones. Como complemento, la pestaña **[!UICONTROL Documentation]** muestra todos los atributos y elementos de esquema y sus propiedades (Campo SQL, tipo/longitud, etiqueta, descripción). La pestaña **[!UICONTROL Documentation]** solo se aplica a los esquemas generados.

## Caso de uso: Creación de una tabla de contrato {#example--creating-a-contract-table}

En el ejemplo siguiente, se crea una nueva tabla para **contratos** en la base de datos. Esta tabla permite almacenar el nombre y los apellidos y las direcciones de correo electrónico de los titulares y cotitulares de cada contrato.

Para ello, debe crear el esquema de la tabla y actualizar la estructura de la base de datos para generar la tabla correspondiente. A continuación se detallan los pasos que debe seguir.

1. Edite el nodo **[!UICONTROL Administration > Configuration > Data schemas]** del árbol de Adobe Campaign y haga clic en **[!UICONTROL New]**.
1. Elija la opción **[!UICONTROL Create a new table in the data template]** y haga clic en **[!UICONTROL Next]**

   ![](assets/create_new_schema.png)

1. Especifique un nombre para la tabla y un área de nombres.

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >De forma predeterminada, los esquemas creados por los usuarios se almacenan en el área de nombres &quot;cus&quot;. Para obtener más información, consulte [Identificación de un esquema](extend-schema.md#identification-of-a-schema).

1. Cree el contenido de la tabla. Se recomienda utilizar el asistente dedicado para asegurarse de que no falta ninguna configuración. Para ello, haga clic en el botón **[!UICONTROL Insert]** y elija el tipo de configuración que desea agregar.

   ![](assets/create_new_content.png)

1. Defina la configuración de la tabla de contratos.

   Se recomienda crear la tabla en la base de datos en la nube agregando el atributo `dataSource="nms:extAccount:ffda"`. Este atributo se agrega de forma predeterminada al crear una tabla nueva.

   ```xml
   <srcSchema created="YYYY-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" lastModified="YYYY-MM-DD HH:MM:SS.TZ"
           mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

   Añada el tipo de enumeración de contrato.

   ```xml
   <srcSchema created="AA-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png" label="Contracts" labelSingular="Contract" AA-MM-DD HH:MM:SS.TZ"mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <enumeration basetype="byte" name="typeContract">
         <value label="Home" name="home" value="0"/>
         <value label="Car" name="car" value="1"/>
         <value label="Health" name="health" value="2"/>
         <value label="Pension fund" name="pension fund" value="2"/>
      </enumeration>
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

1. Guarde el esquema y haga clic en la pestaña **[!UICONTROL Structure]** para generar la estructura:

   ![](assets/configuration_structure.png)

1. Actualice la estructura de la base de datos para crear la tabla a la que se vinculará el esquema. Para obtener más información, consulte [esta sección](update-database-structure.md).
