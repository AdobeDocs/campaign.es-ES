---
title: Work with Campaign and External databases (FDA)
description: Learn how to work with Campaign and External databases
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 355b9219ffd9d481d15d2d0982d49923842cc27b
workflow-type: tm+mt
source-wordcount: '1699'
ht-degree: 54%

---

# Acceso de datos federado (FDA){#gs-fda}

**** You can then access external data without changing the structure of Adobe Campaign data.

>[!NOTE]
>
>* [](../start/compatibility-matrix.md)
>
>* [](../architecture/enterprise-deployment.md) This external account is set up for you by Adobe and must not be modified.
>


Campaign FDA option allows you to extend your data model in a third-party database. Detecta automáticamente la estructura de las tablas de destino y utiliza datos de los orígenes SQL.

****[!DNL Adobe Campaign] Obtenga más información en [esta sección](#fda-permissions).

## Prácticas recomendadas y limitaciones

* ****

   You can pre-process message personalization in a dedicated workflow. **[!UICONTROL Prepare the personalization data with a workflow]****[!UICONTROL Analysis]**

   During the delivery analysis, this option automatically creates and executes a workflow that stores all of the data linked to the target in a temporary table, including data from tables linked in an external database.

   This option significantly improves performances when executing the personalization step.

* ****

   La opción FDA se realiza para manipular los datos en bases de datos externas en modo de lote en los flujos de trabajo. To avoid performance issues, it is not recommended to use the FDA module in the context of unitary operations, such as: personalization, interaction, real-time messaging, etc.

   Evite en la medida de lo posible las operaciones que requieran utilizar tanto Adobe Campaign como la base de datos externa. Para ello, puede hacer lo siguiente:

   * Exporte la base de datos de Adobe Campaign a la base de datos externa y ejecute las operaciones solo desde la base de datos externa antes de volver a importar los resultados en Adobe Campaign.

   * Recopile los datos de la base de datos externa de Adobe Campaign y ejecute las operaciones localmente.

   Si desea personalizar las entregas utilizando datos de la base de datos externa, recopile los datos para utilizarlos en un flujo de trabajo para que estén disponibles en una tabla temporal. A continuación, utilice los datos de la tabla temporal para personalizar su envío.

   The FDA option is subject to the limitations of the external database system that you use.


## Pasos de configuración{#fda-configuration-steps}

To set up access to an external database with FDA, configuration steps are:

1. As an Adobe Managed Services user, contact Adobe to install the drivers on your Campaign instance.
1. Once drivers are installed, set up the external account that correspond to your database on the Adobe Campaign server and test the external account. [Más información](#fda-external-account)
1. Crear el esquema de la base de datos externa en Adobe Campaign. This allows you to identify the data structure of the external database. [Más información](#create-data-schema)

<!--
1. If needed, create a new target mapping from the previously created schema. This is required if the recipients of your deliveries come from the external database. This implementation comes with limitations related to message personalization. [Learn more](#define-data-mapping)
-->

[](../architecture/enterprise-deployment.md) As a consequence, recipients of your deliveries cannot come from the external database.

## Cuenta externa de la base de datos externa{#fda-external-account}

You need to create a specific external account to connect your Campaign instance to your external database.

Para conseguir esto, siga los pasos a continuación:

1. **[!UICONTROL Explorer]****[!UICONTROL Administration]**`>`**[!UICONTROL Platform]**`>`**[!UICONTROL External accounts]**

1. Haga clic en **[!UICONTROL New]**.

   >[!NOTE]
   >
   > **[!UICONTROL Enabled]** If necessary, uncheck this option to disable access to this database without deleting its configuration.

1. Seleccione **[!UICONTROL External database]** como **[!UICONTROL Type]** de su cuenta externa.

1. Choose you external database in the drop-down list and configure the external account. You must specify:

   * **[!UICONTROL Server]**: URL del servidor 

   * **[!UICONTROL Account]**: Nombre del usuario

   * **[!UICONTROL Password]**: Contraseña de la cuenta de usuario

   * **[!UICONTROL Database]**: Nombre de la base de datos

      ![](assets/snowflake.png)

1. Haga clic en la pestaña **[!UICONTROL Parameters]** y luego en el botón **[!UICONTROL Deploy functions]** para crear funciones.

1. Una vez introducidos los parámetros, haga clic en el botón **[!UICONTROL Test the connection]** para aprobarlos.

1. Para permitir que Adobe Campaign acceda a esta base de datos, debe implementar las funciones SQL. Hacer clic en la pestaña **[!UICONTROL Parameters]** y luego en el botón **[!UICONTROL Deploy functions]**.

Puede definir espacios de trabajo específicos para las tablas y para el índice en la pestaña **[!UICONTROL Parameters]**.

[!DNL Snowflake]

| Opción | Descripción |
|---|---|
| esquema de trabajo | Esquema de base de datos que se va a utilizar para tablas de trabajo |
| almacén | Nombre del almacén predeterminado que se va a utilizar. Anula el valor predeterminado del usuario. |
| TimeZoneName | De forma predeterminada, vacío, lo que significa que se utiliza la zona horaria del sistema del servidor de aplicaciones de Campaign Classic. La opción se puede utilizar para forzar el parámetro de sesión TIMEZONE. <br>[Para obtener más información, consulte esta página](https://docs.snowflake.net/manuals/sql-reference/parameters.html#timezone). |
| WeekStart | Parámetro de sesión WEEK_START. De forma predeterminada, se establece en 0. <br>[Para obtener más información, consulte esta página](https://docs.snowflake.com/en/sql-reference/parameters.html#week-start). |
| UseCachedResult | Parámetro de sesión USE_CACHED_RESULTS. De forma predeterminada, se establece en TRUE. Esta opción se puede utilizar para deshabilitar los resultados en caché de Snowflake. <br>Para obtener más información, consulte [esta página](https://docs.snowflake.net/manuals/user-guide/querying-persisted-results.html). |


## Creación del esquema de datos{#create-data-schema}

To create the schema of the external database in Adobe Campaign, follow the steps below:

1. Haga clic en el botón **[!UICONTROL New]** sobre la lista de esquemas de datos y elija **[!UICONTROL Access external data]**.

   ![](assets/wf_new_schema_fda.png)

1. Introduzca un nombre y una descripción para el esquema y seleccione la cuenta externa que activa la conexión con la base de datos. Esto permite acceder a la lista de tablas disponibles en la base externa. Seleccione la tabla que contiene los datos que se van a recopilar.

   ![](assets/wf_new_schema_select_table_fda.png)

1. Haga clic en **[!UICONTROL OK]** para confirmar. Adobe Campaign detecta automáticamente la estructura de la tabla seleccionada y genera el esquema lógico. Tenga en cuenta que Adobe Campaign no genera enlaces.

1. Haga clic en **[!UICONTROL Save]** para confirmar la creación.

<!-- 
## Define the target mapping{#define-data-mapping}

You can define a mapping on the data in an external table.

To do this, once the schema of the external table has been created, you need to create a new delivery mapping to use the data in this table as a delivery target.

To do this, follow these steps:

1. Browse to **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** from Adobe Campaign explorer.

1. Create a new target mapping and select the schema you just created as the targeting dimension.

   ![](assets/new-target-mapping.png)


1. Indicate the fields where the delivery information is stored (last name, first name, email, address, etc.).

   ![](assets/wf_new_mapping_define_join.png)

1. Specify the parameters for information storage, including the suffix of the extension schemas for them to be easily identifiable.

   ![](assets/wf_new_mapping_define_names.png)

   You can choose whether to store exclusions (**excludelog**), with messages (**broadlog**) or in a separate table.

   You can also choose whether to manage tracking for this delivery mapping (**trackinglog**).

1. Then select the extensions to be taken into account. The extension type depends on your platform's parameters and options (view your license contract).

   ![](assets/wf_new_mapping_define_extensions.png)

   Click the **[!UICONTROL Save]** button to launch delivery mapping creation: all linked tables are created automatically based on the selected parameters.
-->

## Permisos{#fda-permissions}

****[!DNL Adobe Campaign]

[!DNL Adobe Campaign]

1. Seleccione el nodo **[!UICONTROL Administration > Access Management > Named Rights]** en el explorador de Adobe Campaign.
1. Cree un nuevo derecho especificando la etiqueta elegida.
1. ****

   * ****
   * ****
   * ****

1. **[!UICONTROL Administration > Access Management > Operators]**

Then, to process the data contained in an external database, the Adobe Campaign operator must have at least &#39;Write&#39; permissions on the database to be able to create worktables. These tables are deleted automatically by Adobe Campaign.

The following permissions are necessary:

* **CONNECT**: conexión con la base de datos remota
* **READ Data**: acceso de sólo lectura a tablas que contienen datos de clientes
* **READ &#39;MetaData**: acceso a los catálogos de datos del servidor para obtener la estructura de la tabla
* **LOAD**: carga masiva en tablas de trabajo (requerido cuando se trabaja en colecciones y uniones)
* **CREATE/DROP** para **TABLE/INDEX/PROCEDURE/FUNCTION** (solo para las tablas de trabajo generadas por Adobe Campaign)
* ****
* **WRITE Data** (según el escenario de integración)

The database administrator needs to make these rights match with the rights specific to each database engine, as detailed below.

|   | Snowflake | Amazon Redshift |
|:-:|:-:|:-:|
| **Conexión a la base de datos remota** | USO EN ALMACÉN (WAREHOUSE), USO EN BASE DE DATOS (DATABASE ) y USO EN PRIVILEGIOS DE ESQUEMA (SCHEMA) | Creación de un usuario vinculado a la cuenta de AWS |
| **Creación de tablas** | Privilegio CREATE TABLE ON SCHEMA | Privilegio CREATE |
| **Creación de índices** | N/A | Privilegio CREATE |
| **Creación de funciones** | Privilegio CREATE FUNCTION ON SCHEMA | El privilegio USAGE ON LANGUAGE plpythonu podrá llamar scripts de python externos |
| **Creación de procedimientos** | N/A | USAGE ON LANGUAGE python privilege to be able to call external python scripts |
| **Eliminación de objetos (tablas, índices, funciones, procedimientos)** | Propiedad del objeto | Tener el objeto o ser un superusuario |
| **Monitoreo de las ejecuciones** | Privilegio MONITOR en el objeto requerido | No se requiere ningún privilegio para utilizar el comando EXPLAIN |
| **Escritura de datos** | Privilegios INSERT o UPDATE (según la operación de escritura) | Privilegios INSERT y UPDATE |
| **Carga de datos en tablas** | Privilegios CREATE STAGE ON SCHEMA, SELECT e INSERT en la tabla de destino | Privilegios SELECT e INSERT |
| **Acceso a los datos del cliente** | Privilegios SELECT en (FUTURE) TABLE(S) o VIEW(S) | Privilegio SELECT |
| **Acceso a metadatos** | Privilegio SELECT en INFORMATION_SCHEMA SCHEMA | Privilegio SELECT |


## Use external data in a workflow

Una vez que se haya creado el esquema, los datos se pueden procesar en los flujos de trabajo de Adobe Campaign.

Múltiples actividades permiten interactuar con datos de una base de datos externa:

* ******[!UICONTROL Query]**

* ******[!UICONTROL Split]** Puede utilizar datos externos para definir los criterios de filtrado que deben utilizarse.

* ******[!UICONTROL Data loading (RDBMS)]**

* ******[!UICONTROL Enrichment]** In this context, it can use data from an external database.


You can also directly define a connection to an external database from these workflow activities, for a temporary usage. En este caso, se trata de una base de datos externa local, reservada para utilizarse dentro de un flujo de trabajo actual: no se guarda en las cuentas externas.

>[!CAUTION]
>
>This type of configuration must only be used temporary to collect data. The external account configuration should be preferred for any other usage.

**[!UICONTROL Query]**

1. **[!UICONTROL Add data...]**
1. **[!UICONTROL External data]**
1. **[!UICONTROL Locally defining the data source]**
1. Seleccionar el motor de base de datos de objetivo en la lista desplegable. Introducir el nombre del servidor y especificar los parámetros de autenticación. Especificar también el nombre de la base de datos externa.
1. Seleccionar la tabla en la que se almacenan los datos. Puede introducir el nombre de la tabla directamente en el campo correspondiente o hacer clic en el icono de edición para acceder a la lista de las tablas de la base de datos.
1. Hacer clic en el botón **[!UICONTROL Add]** para definir uno o varios campos de reconciliación entre los datos de la base de datos externa y los datos de la base de datos de Adobe Campaign. Los iconos **[!UICONTROL Edit expression]** del **[!UICONTROL Remote field]** y el **[!UICONTROL Local field]** le proporcionan acceso a la lista de campos de cada una de las tablas.
1. Si es necesario, especifique una condición de filtrado y el modo de clasificación de datos.
1. Seleccione los datos adicionales que se recopilarán en la base de datos externa. Para ello, haga doble clic en los campos que desea añadir para mostrarlos en las **[!UICONTROL Output columns]**.
1. Hacer clic en **[!UICONTROL Finish]** para confirmar esta configuración.
