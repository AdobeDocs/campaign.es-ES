---
solution: Campaign v8
product: Adobe Campaign
title: Actualizar la estructura de la base de datos
description: Actualizar la estructura de la base de datos
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 0%

---

# Actualizar la estructura de la base de datos{#updating-the-database-structure}

Para aplicar las modificaciones realizadas en los esquemas, inicie el asistente de actualización de la base de datos. Se puede acceder a este asistente mediante **[!UICONTROL Tools > Advanced > Update database structure]** . Comprueba si la estructura física de la base de datos coincide con su descripción lógica y ejecuta las secuencias de comandos de actualización SQL.

![](assets/schema_update.png)

Los módulos de la base de datos se rellenan y activan automáticamente.

![](assets/schema_update_select2.png)

Siga los pasos y vea el script SQL de actualización de la base de datos:

![](assets/schema_update2.png)

>[!NOTE]
>
>Esto se encuentra en un campo de edición y se puede modificar para eliminar o agregar código SQL.

A continuación, inicie la actualización de la base de datos:

![](assets/schema_update3.png)
