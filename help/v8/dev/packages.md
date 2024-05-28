---
title: Trabajo con paquetes de datos
description: Trabajo con paquetes de datos
feature: Data Management, Package Export/Import
role: Developer
level: Intermediate, Experienced
source-git-commit: 933c266febdc293dccdf9b7383d94d7a5dce22bc
workflow-type: tm+mt
source-wordcount: '1941'
ht-degree: 50%

---

# Trabajo con paquetes de datos{#data-packages}

## Introducción a los paquetes {#gs-data-packages}

Puede utilizar paquetes de datos para exportar e importar la configuración y los datos personalizados de la plataforma. Los paquetes pueden contener diferentes tipos de configuraciones y componentes, filtrados o no.

En los paquetes de datos de Campaign, las entidades de la base de datos de Adobe Campaign se muestran en archivos XML. En un paquete, cada entidad se representa con todos sus datos.

El principio de **paquetes de datos** es exportar una configuración de datos e integrarla en otro entorno de Adobe Campaign. Aprenda a mantener un conjunto coherente de paquetes de datos en esta [sección](#data-package-best-practices).

### Tipos de paquetes {#types-of-packages}

Puede trabajar con tres tipos de paquetes en Adobe Campaign: paquetes de usuario, paquetes de plataforma y paquetes de administrador.

* A **paquete de usuario** permite seleccionar la lista de entidades a exportar. Este tipo de paquete administra dependencias y comprueba errores.
* A **paquete de plataforma** incluye todos los recursos técnicos añadidos (no estándar): esquemas, código JavaScript, etc.
* Un **paquete de administración** incluye todas las plantillas y objetos empresariales añadidos (no estándar): plantillas, bibliotecas, etc.

>[!CAUTION]
>
>El **plataforma** y **administrador** los paquetes contienen una lista predefinida de entidades a exportar. Cada entidad está vinculada a unas condiciones de filtrado que permiten eliminar los recursos utilizables del paquete creado.

## Estructura de datos {#data-structure}

La descripción de un paquete de datos es un documento XML estructurado que se ajusta a la gramática del **xrk:navtree** esquema de datos, como en el ejemplo siguiente:

```xml
<package>
  <entities schema="nms:recipient">
    <recipient email="john.smith@adobe.com" lastName="Smith" firstName="John">      
      <folder _operation="none" name="nmsRootFolder"/>      
      <company _operation="none" name="Adobe"/>
    </recipient>
  </entities>
  <entities schema="sfa:company">
    <company name="Adobe">
      <location city="London" zipCode="W11 2BQ"/>
    </company>
  </entities>
</package>
```

El documento XML debe comenzar y terminar con el elemento `<package>`. Cualquiera `<entities>` elementos que siguen distribuyen los datos por tipo de documento. Un `<entities>` contiene los datos del paquete en el formato del esquema de datos introducido en la variable **esquema** atributo. Los datos de un paquete no deben contener claves internas que no sean compatibles con las bases, como las claves generadas automáticamente (opción **autopk**).

En nuestro ejemplo, las uniones en la variable `folder` y `company` Los vínculos de se han sustituido por teclas de &quot;alto nivel&quot; en las tablas de destino:

```xml
<recipient>
  <folder _operation="none" name="nmsRootFolder"/>
  <company _operation="none" name="Adobe"/>
</recipient>
```

El `operation` atributo con el valor `none` define un vínculo de reconciliación.

Un paquete de datos se puede crear manualmente desde cualquier editor de texto. Debe asegurarse de que la estructura del documento XML cumple con el `xtk:navtree` esquema de datos. La consola del cliente tiene un módulo de exportación e importación de paquete de datos.

## Exportación de paquetes {#export-packages}

Los paquetes se pueden exportar de tres formas diferentes:

* Utilice el **[!UICONTROL Package Export]** asistente para exportar un conjunto de objetos en un solo paquete. [Más información](#export-a-set-of-objects-in-a-package)
* Para exportar un **objeto único**, haga clic con el botón derecho en él y seleccione **[!UICONTROL Actions > Export in a package]**.
* Utilice el **Definiciones de paquetes** para crear una estructura de paquetes en la que se añaden objetos para exportarlos posteriormente en un paquete. [Más información](#manage-package-definitions)

Una vez exportado el paquete, puede importarlo, junto a todas las entidades añadidas, en otra instancia de Campaign.

### Exportación de un conjunto de objetos en un paquete {#export-a-set-of-objects-in-a-package}

Para exportar un conjunto de objetos en un paquete de datos, siga estos pasos:

1. Vaya al asistente de exportación de paquetes mediante el **[!UICONTROL Tools > Advanced > Export package...]** menú del explorador.
1. Seleccione el [tipos de paquetes](#types-of-packages).

   ![](assets/package_type.png)

1. Haga clic en **Añadir** para seleccionar las entidades que desea exportar como paquete.

   >[!CAUTION]
   >
   >Si exporta una carpeta de tipo **[!UICONTROL Offer category]**, **[!UICONTROL Offer environment]**, **[!UICONTROL Program]** o **[!UICONTROL Plan]**, evite seleccionar la carpeta **xtk:folder**, ya que puede perder algunos datos. Seleccione la entidad que corresponde a la carpeta: **nms:offerCategory** para categorías de ofertas, **nms:offerEnv** para entornos de ofertas, **nms:program** para programas y **nms:plan** para planes.

   El mecanismo de dependencia controla la secuencia de exportación de entidades. Para obtener más información, consulte [Administración de dependencias](#managing-dependencies).

1. Clic **[!UICONTROL Next]** y defina la consulta de filtro en el tipo de documento que se va a extraer. Debe configurar la cláusula de filtrado para la extracción de datos.

   >[!NOTE]
   >
   >El editor de consultas se muestra en [esta sección](../../automation/workflow/query.md).

1. Clic **[!UICONTROL Next]** y seleccione el orden de los datos exportados.

1. Previsualice los datos que desea extraer para comprobar la configuración.

1. La última página del asistente de exportación de paquetes permite iniciar la exportación. Los datos se almacenan en el archivo indicado en el campo **[!UICONTROL File]**.

### Administración de dependencias {#manage-dependencies}

El proceso de exportación realiza un seguimiento de los vínculos entre los distintos elementos exportados. Este mecanismo se define por dos reglas:

* objetos vinculados a un vínculo con una `own` o `owncopy` La integridad de tipos se exporta en el mismo paquete que el objeto exportado.
* objetos vinculados a un vínculo con una `neutral` o `define` la integridad de tipo (vínculo definido) debe exportarse por separado.

>[!NOTE]
>
>Los tipos de integridad vinculados a elementos de esquema se definen en [esta página](database-links.md).

#### Exportación de una campaña {#export-a-campaign}

A continuación se muestra un ejemplo de cómo exportar una campaña. La campaña de marketing que se va a exportar contiene:
* a `MyTask`tarea
* a `campaignWorkflow` flujo de trabajo en la siguiente carpeta: **[!UICONTROL Administration > Production > Technical workflows > Campaign processes > MyWorkflow]**.

La tarea y el flujo de trabajo se exportan en el mismo paquete que la campaña, ya que los esquemas coincidentes están conectados por vínculos con una `own` integridad de tipo.

El contenido del paquete es:

```xml
<?xml version='1.0'?>
<package author="Administrator (admin)" buildNumber="7974" buildVersion="7.1" img=""
label="" name="" namespace="" vendor="">
 <desc></desc>
 <version buildDate="2013-01-09 10:30:18.954Z"/>
 <entities schema="nms:operation">
  <operation duration="432000" end="2013-01-14" internalName="OP1" label="MyCampaign"
  modelName="opEmpty" start="2013-01-09">
   <controlGroup>
    <where filteringSchema=""/>
   </controlGroup>
   <seedList>
    <where filteringSchema="nms:seedMember"></where>
    <seedMember internalName="SDM1"></seedMember>
   </seedList>
   <parameter useAsset="1" useBudget="1" useControlGroup="1" useDeliveryOutline="1"
   useDocument="1" useFCPValidation="0" useSeedMember="1" useTask="1"
   useValidation="1" useWorkflow="1"></parameter>
   <fcpSeed>
    <where filteringSchema="nms:seedMember"></where>
   </fcpSeed>
   <owner _operation="none" name="admin" type="0"/>
   <program _operation="none" name="nmsOperations"/>
   <task end="2013-01-17 10:07:51.000Z" label="MyTask" name="TSK2" start="2013-01-16 10:07:51.000Z"
   status="1">
    <owner _operation="none" name="admin" type="0"/>
    <operation _operation="none" internalName="OP1"/>
    <folder _operation="none" name="nmsTask"/>
   </task>
   <workflow internalName="WKF12" label="CampaignWorkflow" modelName="newOpEmpty"
   order="8982" scenario-cs="Notification of the workflow supervisor (notifySupervisor)"
   schema="nms:recipient">
    <scenario internalName="notifySupervisor"/>
    <desc></desc>
    <folder _operation="none" name="Folder4"/>
    <operation _operation="none" internalName="OP1"/>
   </workflow>
  </operation>
 </entities>
</package>   
```

La afiliación a un tipo de paquete se define en un esquema con la variable `@pkgAdmin and @pkgPlatform` atributo. Ambos atributos reciben una expresión XTK que define las condiciones de afiliación del paquete.

```xml
<element name="offerEnv" img="nms:offerEnv.png" 
template="xtk:folder" pkgAdmin="@id != 0">
```

Por último, el `@pkgStatus` attribute permite definir las reglas de exportación para estos elementos o atributos. En función del valor del atributo, el elemento o atributo se encuentra en el paquete exportado. Los tres valores posibles de este atributo son:

* `never`: no exporta el campo/vínculo
* `always`: fuerza la exportación de este campo
* `preCreate`: autoriza la creación de la entidad vinculada

>[!NOTE]
>
>El `preCreate` el valor solo se admite para eventos de tipo vínculo. Permite crear o señalar una entidad que aún no se ha cargado en el paquete exportado.

## Administración de definiciones de paquetes {#manage-package-definitions}

Las definiciones de paquete permiten crear una estructura de paquetes en la que se añaden entidades que se exportan posteriormente en un solo paquete. Después puede importar este paquete y todas las entidades añadidas en otra instancia de Campaign.

### Creación de una definición de paquete {#create-a-package-definition}

Se puede acceder a las definiciones de paquetes desde el menú **[!UICONTROL Administration > Configuration > Package management > Package definitions]**.

Para crear una definición de paquete, haga clic en el botón **[!UICONTROL New]** y complete la información general de la definición del paquete.

![](assets/packagedefinition_create.png)

A continuación, se pueden añadir entidades a la definición del paquete y exportarla a un paquete de archivos XML.

**Temas relacionados:**

* [Adición de entidades a una definición de paquete](#add-entities-to-a-package-definition)
* [Configuración de la generación de definiciones de paquetes](#configure-package-definitions-generation)
* [Exportación de paquetes desde una definición de paquete](#export-packages-from-a-package-definition)

### Adición de entidades a una definición de paquete {#add-entities-to-a-package-definition}

En la pestaña **[!UICONTROL Content]**, haga clic en el botón **[!UICONTROL Add]** para seleccionar las entidades que desea exportar con el paquete. Las prácticas recomendadas al seleccionar entidades se presentan en la [esta sección](#export-a-set-of-objects-in-a-package).

![](assets/packagedefinition_addentities.png)

Las entidades se pueden añadir a una definición de paquete directamente desde su ubicación en la instancia. Para realizar esto, siga los pasos a continuación:

1. Haga clic con el botón derecho en la entidad deseada y luego seleccione **[!UICONTROL Actions > Export in a package]**.

1. Seleccione **[!UICONTROL Add to a package definition]** y luego seleccione la definición del paquete a la que desea añadir la entidad.

1. La entidad se añade a la definición del paquete y se exporta con el paquete (consulte [esta sección](#export-packages-from-a-package-definition)).

### Configuración de la generación de definiciones de paquetes {#configure-package-definitions-generation}

La generación de paquetes se puede configurar desde la pestaña de **[!UICONTROL Content]** de definición del paquete. Para ello, haga clic en el vínculo **[!UICONTROL Generation parameters]**.

![](assets/packagedefinition_generationparameters.png)

* Utilice el **[!UICONTROL Include the definition]** opción para incluir la definición utilizada actualmente en la definición del paquete.
* Utilice el **[!UICONTROL Include an installation script]** opción para añadir una secuencia de comandos javascript para ejecutarla en la importación del paquete. Al seleccionarlo, se añade una pestaña **[!UICONTROL Script]** en la pantalla de definición del paquete.
* Utilice el **[!UICONTROL Include default values]** para añadir al paquete los valores de todos los atributos de las entidades.

  Esta opción no está seleccionada de forma predeterminada para evitar exportaciones largas. Esto significa que, de forma predeterminada, los atributos de las entidades con valores predeterminados (&quot;cadena vacía&quot;, &quot;0&quot; y &quot;falso&quot; si no se definen en el esquema) no se añaden al paquete y, por lo tanto, no se exportan.

  >[!CAUTION]
  >
  >Si la instancia en la que se importa el paquete contiene entidades idénticas a las del paquete (por ejemplo, con la misma ID externa), sus atributos no se actualizan. Esto puede ocurrir si los atributos de la instancia anterior tienen valores predeterminados, ya que no se incluyen en el paquete. En ese caso, la selección de la opción **[!UICONTROL Include default values]** impide que las versiones se fusionen, ya que todos los atributos de la instancia anterior se exportan con el paquete.

### Exportación de paquetes desde una definición de paquete {#export-packages-from-a-package-definition}

Para exportar un paquete desde una definición de paquete, siga los pasos siguientes:

1. Seleccione la definición del paquete que desea exportar y haga clic en **[!UICONTROL Actions]** y seleccione. **[!UICONTROL Export the package]**.
1. Compruebe el nombre y la ubicación del archivo exportado.
1. Haga clic en **[!UICONTROL Start]** para iniciar la exportación.

## Importación de paquetes {#import-packages}

Se puede acceder al asistente de importación de paquetes a través del menú principal **[!UICONTROL Tools > Advanced > Import package]** de la consola del cliente.

### Instalación de un paquete desde un archivo {#install-a-package-from-a-file}

Para importar un paquete de datos existente, siga estos pasos:

1. Acceso al asistente de importación a través del menú principal **[!UICONTROL Tools > Advanced > Import package]** de la consola del cliente.
1. Seleccione el archivo XML y haga clic en **[!UICONTROL Open]**.

El contenido del paquete que se va a importar se muestra en la sección central del editor.

Haga clic en **[!UICONTROL Next]** y después en **[!UICONTROL Start]** para iniciar la importación.

### Instalación de un paquete integrado {#install-a-standard-package}

Paquetes integrados (también conocidos como paquetes estándar) se instalan cuando se configura Adobe Campaign. Según los permisos, el modelo de implementación y la oferta de productos, puede importar nuevos paquetes estándar.

Consulte el acuerdo de licencia para comprobar qué paquetes puede instalar.

## Prácticas recomendadas de paquete de datos {#data-package-best-practices}

En esta sección se describe cómo organizar los paquetes de datos de forma coherente durante toda la duración del proyecto.


### Versiones

Siempre debe importar en la misma versión de la plataforma. Debe comprobar que implementa los paquetes entre dos instancias que tienen la misma compilación. Evite forzar la importación y siempre actualice primero la plataforma (si la compilación es diferente).

>[!IMPORTANT]
>
>Adobe no admite la importación entre distintas versiones.

Preste atención a la estructura del esquema y de la base de datos. La importación de un paquete con esquema debe ir seguida de la generación de esquemas.

### Tipos de paquetes {#package-types}

Empiece por definir diferentes tipos de paquetes. Solo se utilizan cuatro tipos:

**Entidades**

* Todos los elementos específicos de &quot;xtk&quot; y &quot;nms&quot; en Adobe Campaign como esquemas, formularios, carpetas, plantillas de envíos, etc.
* Puede considerar una entidad como elemento &quot;admin&quot; y &quot;platform&quot;.
* Evite incluir más de una entidad en un paquete al cargarlo en una instancia de Campaign.

Si necesita implementar la configuración en una instancia nueva, puede importar todos los paquetes de entidades.

**Funciones**

Este tipo de paquete:
* Responde a un requisito o especificación del cliente.
* Contiene una o varias funcionalidades.
* Debe contener todas las dependencias para poder ejecutar la funcionalidad sin ningún otro paquete.

**Campañas**

Este paquete no es obligatorio. A veces resulta útil crear un tipo específico para todas las campañas, incluso si una campaña se puede ver como una función.

**Actualizaciones**

Una vez configurada, una función se puede exportar a otro entorno. Por ejemplo, el paquete se puede exportar de un entorno de desarrollo a un entorno de prueba. En esta prueba, se muestra un defecto. Primero, debe corregirse en el entorno de desarrollo. A continuación, el parche debe aplicarse a la plataforma de prueba.

La primera solución sería volver a exportar toda la función. Sin embargo, para evitar cualquier riesgo (actualizar elementos no deseados), es más seguro tener un paquete que contenga solamente la corrección.

Por este motivo, recomendamos crear un paquete &quot;actualización&quot; que contenga solo un tipo de entidad de la función.

Una actualización no solo podría ser una corrección, sino también un nuevo elemento del paquete de campaña, función o entidad. Para evitar implementar todo el paquete, puede exportar un paquete de actualización.

### Convenciones de nomenclatura {#data-package-naming}

Ahora que los tipos están definidos, debemos especificar una convención de nombres. Adobe Campaign no permite crear subcarpetas para las especificaciones del paquete, lo que significa que los números son la mejor solución para mantenerse organizados. Números de nombres de paquetes de prefijos.

Por ejemplo, puede utilizar la siguiente convención:

* Entidad: de 1 a 99
* Función: de 100 a 199
* Campaña: de 200 a 299
* Actualización: de 5000 a 5999

#### Orden de paquetes de entidades {#entity-packages-order}

Para ayudar a la importación, los paquetes de entidades deben ordenarse a medida que se importan.

Por ejemplo:

* 001 - Esquema
* 002 - Formulario
* 003 - Imágenes
* Etc.

>[!NOTE]
>
>Forms solo debe importarse **después** actualizaciones de esquema.


#### Documentación del paquete {#package-documentation}

Al actualizar un paquete, siempre debe colocar un comentario en el campo de descripción para detallar las modificaciones y motivos (por ejemplo, &quot;añadir un nuevo esquema&quot; o &quot;corregir un defecto&quot;).

Una práctica recomendada también es introducir la fecha de la actualización.

>[!IMPORTANT]
>
>El campo de descripción solo puede contener hasta 2000 caracteres.

