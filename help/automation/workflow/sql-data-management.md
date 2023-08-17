---
product: campaign
title: Gestión de datos SQL
description: Descubra más información sobre la actividad del flujo de trabajo Gestión de datos SQL
feature: Workflows
exl-id: a1e08d57-0387-4802-b447-f6d9ad87072a
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 100%

---

# Administración de datos SQL{#sql-data-management}

La actividad de **SQL Data Management** permite escribir sus propios scripts SQL para crear y rellenar tablas de trabajo.

## Requisitos previos {#prerequisites}

Antes de configurar la actividad, asegúrese de que se cumplan los siguientes requisitos previos:

* La actividad solo está disponible para fuentes de datos remotos.
* El esquema de salida debe existir en la base de datos y estar vinculado a una base de datos de FDA.


## Configuración de la actividad de gestión de datos SQL {#configuring-the-sql-data-management-activity}

1. Especifique la actividad **[!UICONTROL Label]**.
1. Seleccione usar la **[!UICONTROL External account]**, luego seleccione el vínculo **[!UICONTROL Outbound schema]** vinculado a esta cuenta externa.

   >[!CAUTION]
   >
   >El esquema saliente es fijo y no se puede editar.

1. Agregue el script SQL.

   >[!CAUTION]
   >
   >Es responsabilidad del escritor del script de SQL asegurarse de que el script SQL funcione y que sus referencias (nombres de campos, etc.) estén en conformidad con el esquema saliente.

   Si desea cargar un código SQL existente, seleccione la opción **[!UICONTROL The SQL script is contained in an entity stored in the database]**. Los scripts SQL se deben crear y almacenar en el menú **[!UICONTROL Administration]** / **[!UICONTROL Configuration]** / **[!UICONTROL SQL scripts]**.

   De lo contrario, escriba o copie y pegue el script SQL en el área dedicada.

   ![](assets/sql_datamanagement.png)

   La actividad permite utilizar las siguientes variables en el script:

   * **activity.tableName**: Nombre SQL de la tabla de trabajo saliente.
   * **task.incomingTransitionByName(‘name’).tableName**: Utilice el nombre SQL de la tabla de trabajo realizada por la transición entrante (la transición se identifica con su nombre).

     >[!NOTE]
     >
     >El valor (“”) corresponde al campo **[!UICONTROL Name]** Name de las propiedades de transición.

1. Si la secuencia de comandos SQL ya contiene comandos para crear una tabla de trabajo saliente, anule la selección de la opción **[!UICONTROL Automatically create work table]**. De lo contrario, se crea una tabla de trabajo una vez que se ejecute el flujo de trabajo.
1. Haga clic en **[!UICONTROL Ok]** para confirmar esta configuración.

La actividad está configurada. Está listo para ejecutarse en el flujo de trabajo.

>[!CAUTION]
>
>Una vez que se ejecuta la actividad, la transición de salida registra solo el recuento. Puede variar según el nivel de complejidad de la secuencia de comandos SQL.
>  
>Si se reinicia la actividad, se ejecuta todo el script desde el principio, independientemente del estado de ejecución.

## Ejemplos de script SQL: {#sql-script-samples}

>[!NOTE]
>
>Los ejemplos de script de esta sección están pensados para ejecutarse en PostgreSQL.

El siguiente script permite crear una tabla de trabajo e insertar datos en esta misma tabla de trabajo:

```
CREATE UNLOGGED TABLE <%= activity.tableName %> (
  iRecipientId INTEGER DEFAULT 0,
  sFirstName VARCHAR(100),
  sMiddleName VARCHAR(100),
  sLastName VARCHAR(100),
  sEmail VARCHAR(100)
);

INSERT INTO <%= activity.tableName %>
SELECT iRecipientId, sFirstName, sMiddleName, sLastName, sEmail
FROM nmsRecipient
GROUP BY iRecipientId, sFirstName, sMiddleName, sLastName, sEmail;
```

El siguiente script permite realizar una operación CTAS (CREATE TABLE AS SELECT) y crear un índice de tabla de trabajo:

```
CREATE TABLE <%= activity.tableName %>
AS SELECT iRecipientId, sEmail, sFirstName, sLastName, sMiddleName
FROM nmsRecipient
WHERE sEmail IS NOT NULL
GROUP BY iRecipientId, sEmail, sFirstName, sLastName, sMiddleName;

CREATE INDEX ON <%= activity.tableName %> (sEmail);

ANALYZE <%= activity.tableName %> (sEmail);
```

El siguiente script permite combinar dos tablas de trabajo:

```
CREATE TABLE <%= activity.tableName %>
AS SELECT i1.sFirstName, i1.sLastName, i2.sEmail
FROM <%= task.incomingTransitionByName('input1').tableName %> i1
JOIN <%= task.incomingTransitionByName('input2').tableName %> i2 ON (i1.id = i2.id)
```
