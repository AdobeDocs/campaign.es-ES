---
title: Estructura del esquema de campaña
description: Estructura del esquema de Campaign
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: 9c4a9e71-3fc8-4b4e-8782-0742bbeaf426
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 12%

---

# Estructura del esquema{#schema-structure}

La estructura básica de un `<srcschema>` es el siguiente:

```
<srcSchema>
    <enumeration>
        ...          //definition of enumerations
    </enumeration>
   
    <element>         //definition of the root <element>    (mandatory)

        <compute-string/>  //definition of a compute-string
        <key>
            ...        //definition of keys
        </key>
        <sysFilter>
            ...           //definition of filters
        </sysFilter>
        <attribute>
            ...             //definition of fields
        </attribute>
    
            <element>           //definition of sub-<element> 
                  <attribute>           //(collection, links or XML)
                  ...                         //and additional fields
                  </attribute>
                ...
            </element>
      
    </element> 

        <methods>                 //definition of SOAP methods
            <method>
                ...
            </method>
            ...
    </methods>  
          
</srcSchema>
```

El documento XML de un esquema de datos debe contener **`<srcschema>`** el elemento raíz con los atributos **name** y **namespace** para rellenar el nombre del esquema y su área de nombres.

```
<srcSchema name="schema_name" namespace="namespace">
...
</srcSchema>
```

Utilice el siguiente contenido XML para ilustrar la estructura de un esquema de datos:

```
<recipient email="John.doe@aol.com" created="AAAA/DD/MM" gender="1"> 
  <location city="London"/>
</recipient>
```

Con su esquema de datos correspondiente:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email"/>
    <attribute name="created"/>
    <attribute name="gender"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

## Descripción {#description}

El punto de entrada del esquema es el elemento principal. Es fácil de identificar porque tiene el mismo nombre que el esquema y debe ser el elemento secundario del elemento raíz. La descripción del contenido comienza con este elemento.

En nuestro ejemplo, el elemento principal se representa mediante la siguiente línea:

```
<element name="recipient">
```

Los elementos **`<attribute>`** y **`<element>`** que siguen al elemento principal permiten definir las ubicaciones y los nombres de los elementos de datos en la estructura XML.

En nuestro esquema de ejemplo, estos son:

```
<attribute name="email"/>
<attribute name="created"/>
<attribute name="gender"/>
<element name="location">
  <attribute name="city"/>
</element>
```

Se deben cumplir las siguientes reglas:

* Cada **`<element>`** y **`<attribute>`** debe identificarse por nombre a través de **name** atributo.

   >[!CAUTION]
   >
   >El nombre del elemento debe ser conciso, preferiblemente en inglés, e incluir solo caracteres autorizados de acuerdo con las reglas de nomenclatura XML.

* Solo **`<element>`** Los elementos pueden contener **`<attribute>`** elementos y **`<element>`** elementos en la estructura XML.
* Un **`<attribute>`** el elemento debe tener un nombre único dentro de un **`<element>`**.
* El uso de **`<elements>`** en cadenas de datos de varias líneas.

## Tipos de datos {#data-types}

El tipo de datos se introduce mediante la variable **type** en el **`<attribute>`** y **`<element>`** elementos.

Encontrará una lista detallada en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html#configuring-campaign-classic).

Cuando este atributo no se rellena, **cadena** es el tipo de datos predeterminado a menos que el elemento contenga elementos secundarios. Si es así, solo se utiliza para estructurar los elementos jerárquicamente (**`<location>`** en nuestro ejemplo).

Los siguientes tipos de datos son compatibles con los esquemas:

* **cadena**: cadena de caracteres. Ejemplos: un nombre, una ciudad, etc.

   El tamaño se puede especificar mediante la variable **length** (opcional, valor predeterminado &quot;255&quot;).

* **booleano**: Campo booleano. Ejemplo de valores posibles: true/false, 0/1, sí/no, etc.
* **byte**, **corto**, **largo**: enteros (1 byte, 2 bytes, 4 bytes). Ejemplos: una edad, un número de cuenta, una cantidad de puntos, etc.
* **doble**: número de punto flotante de precisión doble. Ejemplos: un precio, una tasa, etc.
* **fecha**, **datetime**: fechas y fechas + horas. Ejemplos: una fecha de nacimiento, una fecha de compra, etc.
* **datetimenotz**: fecha y hora sin datos de zona horaria.
* **intervalo de tiempo**: duraciones. Ejemplo: antigüedad.
* **nota**: campos de texto largos (varias líneas). Ejemplos: una descripción, un comentario, etc.
* **uuid**: campos &quot;uniqueidentifier&quot;

   >[!NOTE]
   >
   >Para contener un **uuid** , la función &quot;newuuid()&quot; debe añadirse y completarse con su valor predeterminado.

Este es un ejemplo de esquema con los tipos introducidos:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email" type="string" length="80"/>
    <attribute name="created" type="datetime"/>
    <attribute name="gender" type="byte"/>
    <element name="location">
      <attribute name="city" type="string" length="50"/>
   </element>
  </element>
</srcSchema>
```

## Propiedades {#properties}

El **`<elements>`** y **`<attributes>`** Los elementos del esquema de datos se pueden enriquecer con varias propiedades. Puede rellenar una etiqueta para describir el elemento actual.

### Etiquetas y descripciones {#labels-and-descriptions}

* El **etiqueta** La propiedad permite introducir una descripción breve.

   >[!NOTE]
   >
   >La etiqueta está asociada al idioma actual de la instancia.

   **Ejemplo**:

   ```
   <attribute name="email" type="string" length="80" label="Email"/>
   ```

   La etiqueta se puede ver desde el formulario de entrada de la consola del cliente de Adobe Campaign:

   ![](assets/schema_label.png)

* El **desc** La propiedad permite introducir una descripción larga.

   La descripción se puede ver desde el formulario de entrada en la barra de estado de la ventana principal de la consola del cliente de Adobe Campaign.

   >[!NOTE]
   >
   >La descripción está asociada al idioma actual de la instancia.

   **Ejemplo**:

   ```
   <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
   ```

### Valores predeterminados {#default-values}

El **predeterminado** La propiedad permite definir una expresión que devuelva un valor predeterminado en la creación de contenido.

El valor debe ser una expresión compatible con el lenguaje XPath. Para obtener más información, consulte [esta sección](#reference-with-xpath).

**Ejemplo**:

* Fecha actual: **default=GetDate()&quot;**
* Contador: **default=&quot;&#39;FRM&#39;+CounterValue(&#39;myCounter&#39;)&quot;**

   En este ejemplo, el valor predeterminado se construye utilizando la concatenación de una cadena y llamando a la variable **CounterValue** función con un nombre de contador libre. El número devuelto se incrementa en uno en cada inserción.

   >[!NOTE]
   >
   >En la consola del cliente de Adobe Campaign, la variable **[!UICONTROL Administration>Counters]** se utiliza para administrar contadores.

Para vincular un valor predeterminado a un campo, puede utilizar el `<default>  or  <sqldefault>   field.  </sqldefault> </default>`

`<default>` : le permite rellenar previamente el campo con un valor predeterminado al crear entidades. El valor no será un valor SQL predeterminado.

`<sqldefault>` : permite tener un valor añadido al crear un campo. Este valor aparece como un resultado SQL. Durante una actualización de esquema, este valor solo afecta a los registros nuevos.

### Enumeraciones {#enumerations}

#### Lista desglosada libre {#free-enumeration}

El **userEnum** La propiedad permite definir una enumeración gratuita para memorizar y mostrar los valores introducidos mediante este campo. La sintaxis es la siguiente:

**userEnum=&quot;nombre de la enumeración&quot;**

El nombre dado a la enumeración puede elegirse libremente y compartirse con otros campos.

Estos valores se muestran en una lista desplegable del formulario de entrada:

![](assets/schema_user_enum.png)

>[!NOTE]
>
>En la consola del cliente de Adobe Campaign, la variable **[!UICONTROL Administration > Enumerations]** se utiliza para administrar enumeraciones.

#### Establecer enumeración {#set-enumeration}

El **enum** La propiedad permite definir una enumeración fija utilizada cuando se conoce de antemano la lista de valores posibles.

El **enum** attribute hace referencia a la definición de una clase de enumeración rellenada en el esquema fuera del elemento principal.

Las enumeraciones permiten al usuario seleccionar un valor de una lista desplegable en lugar de introducir el valor en un campo de entrada normal:

![](assets/schema_enum.png)

Ejemplo de una declaración de enumeración en el esquema de datos:

```
<enumeration name="gender" basetype="byte" default="0">    
  <value name="unknown" label="Not specified" value="0"/>    
  <value name="male" label="male" value="1"/>   
  <value name="female" label="female" value="2"/>   
</enumeration>
```

Se declara una enumeración fuera del elemento principal mediante la variable **`<enumeration>`** Elemento.

Las propiedades de la enumeración son las siguientes:

* **baseType**: tipo de datos asociados con los valores,
* **etiqueta**: descripción de la enumeración,
* **name**: nombre de la enumeración,
* **predeterminado**: valor predeterminado de la enumeración.

Los valores de enumeración se declaran en la variable **`<value>`** con los atributos siguientes:

* **name**: nombre del valor almacenado internamente,
* **etiqueta**: etiqueta mostrada a través de la interfaz gráfica.

#### enumeración dbenum {#dbenum-enumeration}

* El **dbeno** La propiedad permite definir una enumeración cuyas propiedades son similares a las del **enum** propiedad.

   Sin embargo, la variable **name** El atributo no almacena el valor internamente, almacena un código que permite ampliar las tablas correspondientes sin modificar su esquema.

   Los valores se definen mediante la variable **[!UICONTROL Administration>Enumerations]** nodo.

   Esta enumeración se utiliza para especificar la naturaleza de las campañas, por ejemplo.

   ![](assets/schema_dbenum.png)

### Ejemplo {#example}

A continuación, se muestra un ejemplo de esquema con las propiedades rellenadas:

```
<srcSchema name="recipient" namespace="cus">
  <enumeration name="gender" basetype="byte">    
    <value name="unknown" label="Not specified" value="0"/>    
    <value name="male" label="male" value="1"/>   
    <value name="female" label="female" value="2"/>   
  </enumeration>

  <element name="recipient">
    <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
    <attribute name="created" type="datetime" label="Date of creation" default="GetDate()"/>
    <attribute name="gender" type="byte" label="gender" enum="gender"/>
    <element name="location" label="Location">
      <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
   </element>
  </element>
</srcSchema>
```

## Colecciones {#collections}

Una colección es una lista de elementos con el mismo nombre y el mismo nivel jerárquico.

El **libre** el atributo con el valor &quot;true&quot; permite rellenar un elemento de colección.

**Ejemplo**: definición del **`<group>`** elemento de colección en el esquema.

```
<element name="group" unbound="true" label="List of groups">
  <attribute name="label" type="string" label="Label"/>
</element>
```

Con proyección del contenido XML:

```
<group label="Group1"/>
<group label="Group2"/>
```

## Referencia con XPath {#reference-with-xpath}

El lenguaje XPath se utiliza en Adobe Campaign para hacer referencia a un elemento o atributo perteneciente a un esquema de datos.

XPath es una sintaxis que permite localizar un nodo en el árbol de un documento XML.

Los elementos se designan por su nombre y los atributos se designan por el nombre precedido del carácter “@”.

**Ejemplo**:

* **@email**: selecciona el correo electrónico,
* **ubicación/@city**: selecciona el atributo &quot;city&quot; en **`<location>`** elemento
* **../@email**: selecciona la dirección de correo electrónico del elemento principal del elemento actual
* **grupo`[1]/@label`**: selecciona el atributo &quot;label&quot; que es el elemento secundario del primer **`<group>`** elemento de colección
* **grupo`[@label='test1']`**: selecciona el atributo &quot;label&quot; que es el elemento secundario del **`<group>`** y contiene el valor &quot;test1&quot;

>[!NOTE]
>
>Se añade una restricción adicional cuando la ruta cruza un subelemento. En este caso, la siguiente expresión debe colocarse entre corchetes:
>
>* **ubicación/@city** no es válido; utilice **`[location/@city]`**
>* **`[@email]`** y **@email** son equivalentes
>


También es posible definir expresiones complejas, como las siguientes operaciones aritméticas:

* **@gender+1**: añade 1 al contenido del **género** atributo,
* **@email + &#39;(&#39;+@created+&#39;)&#39;**: construye una cadena tomando el valor de la dirección de correo electrónico añadida a la fecha de creación entre paréntesis (para el tipo de cadena, ponga la constante entre comillas).

Se han añadido funciones de alto nivel a las expresiones para enriquecer el potencial de este lenguaje.

Puede acceder a la lista de funciones disponibles a través de cualquier editor de expresiones en la consola del cliente de Adobe Campaign:

![](assets/schema_function.png)

**Ejemplo**:

* **GetDate()**: devuelve la fecha actual
* **Año(@created)**: devuelve el año de la fecha contenida en el atributo &quot;created&quot;.
* **GetEmailDomain(@email)**: devuelve el dominio de la dirección de correo electrónico.

## Creación de una cadena a través de la cadena de cálculo {#building-a-string-via-the-compute-string}

A **Cadena Compute** es una expresión XPath que se utiliza para construir una cadena que representa un registro de una tabla asociada al esquema. **Cadena Compute** se utiliza principalmente en la interfaz gráfica para mostrar la etiqueta de un registro seleccionado.

El **Cadena Compute** se define mediante la variable **`<compute-string>`** bajo el elemento principal del esquema de datos. Un **expr** contiene una expresión XPath para calcular la visualización.

**Ejemplo**: calcule la cadena de la tabla de destinatarios.

```
<srcSchema name="recipient" namespace="nms">  
  <element name="recipient">
    <compute-string expr="@lastName + ' ' + @firstName +' (' + @email + ')' "/>
    ...
  </element>
</srcSchema>
```

Resultado de la cadena calculada para un destinatario: **Doe John (john.doe@aol.com)**

>[!NOTE]
>
>Si el esquema no contiene una Compute string, se rellena una Compute string de forma predeterminada con los valores de la clave principal del esquema.
