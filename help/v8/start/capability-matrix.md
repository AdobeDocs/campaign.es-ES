---
solution: Campaign v8
product: Adobe Campaign
title: 'Campaign Classic v7: matriz de capacidades de Campaign v8'
description: Comprender las diferencias entre Campaign Classic v7 y Campaign v8
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 4%

---

# [!DNL Campaign Classic] v7: funciones  [!DNL Campaign] v8{#gs-matrix}

Como usuario [!DNL Campaign Classic] v7 existente, no debería esperar grandes interrupciones en la forma en que normalmente interactúa con [!DNL Adobe Campaign]. La mayoría de los cambios en la versión 8 no están visibles, excepto los pequeños cambios que aparecen en la interfaz de usuario y en los pasos de configuración.

Cambios clave:

* Crear segmentos hasta 200 veces más rápido
* Aumentar la velocidad de entrega
* Informes en tiempo real con Cubes

Como usuario [!DNL Campaign Classic], tenga en cuenta que la mayoría de las funciones [!DNL Campaign Classic] v7 están disponibles con [!DNL Campaign] v8, excepto un pequeño conjunto de ellas, enumeradas en [esta sección](#gs-removed). Otros vendrán en futuras versiones. [Obtenga más información en esta sección](#gs-unavailable-features)

[!DNL :bulb:] Obtenga más información sobre la arquitectura  [!DNL Campaign] v8 en  [esta página](../dev/architecture.md).

## Cambios en la configuración del producto

### [!DNL Campaign] y [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 funciona con dos bases de datos: una base de datos local para la interfaz de usuario mensajería en tiempo real y consultas unitarias y escritura a través de API, y una base de datos de Cloud para la ejecución de campañas, consultas por lotes y la ejecución del flujo de trabajo.

Este es un cambio fundamental en la arquitectura del software. Ahora, los datos son remotos y Campaign federa todos los datos, incluidos los perfiles. [!DNL Campaign] ahora, los procesos escalan de principio a fin, desde la segmentación hasta la ejecución del mensaje: la ingesta de datos, la segmentación, la segmentación, las consultas, las entregas ahora se ejecutan normalmente en minutos. Esta nueva versión resuelve todo el desafío de escalar mientras mantiene el mismo nivel de flexibilidad y extensibilidad. El número de perfiles es casi ilimitado y se puede ampliar la retención de datos.

El almacenamiento en la nube se realiza en **[!DNL Snowflake]**: una nueva **cuenta externa** integrada garantiza la conectividad con la base de datos de Cloud. Está configurado por Adobe y no debe modificarse. [Más información](../config/external-accounts.md).

Cualquier esquema o tabla integrado que deba moverse o replicarse en la base de datos de Cloud viene con una extensión de esquema integrada en el espacio de nombres **xxl**. Estas extensiones contienen cualquier modificación necesaria para mover esquemas integrados de la base de datos local [!DNL Campaign] a la base de datos de [!DNL Snowflake] Cloud y adaptar su estructura en consecuencia: nuevo UUID, vínculos actualizados, etc.

>[!CAUTION]
>
> Los datos del cliente no se almacenan en la base de datos local [!DNL Campaign]. Como consecuencia, cualquier tabla personalizada debe crearse en la base de datos de Cloud.


Hay API específicas disponibles para administrar los datos entre la base de datos local y la base de datos en la nube. Descubra cómo funcionan estas nuevas API y cómo utilizarlas en [esta página](../dev/new-apis.md).

### Duplicación de datos

Un flujo de trabajo técnico específico gestiona la duplicación de tablas que deben estar presentes en ambos lados (base de datos local de Campaign y base de datos de Cloud). Este flujo de trabajo se activa cada hora y depende de una nueva biblioteca JavaScript integrada.

>[!NOTE]
>
> Se han creado varias políticas de replicación en función del tamaño de la tabla (XS, XL, etc.).
> Algunas tablas se duplican en tiempo real, otras se duplican cada hora. Algunas tablas tendrán actualizaciones incrementales, otras se actualizarán por completo.


[Más información sobre la replicación de datos](../config/replication.md)

### Administración de ID

Los objetos de Campaign v8 ahora utilizan un **identificador único universal (UUID)**, que permite valores únicos ilimitados para identificar datos

Tenga en cuenta que este ID se basa en cadenas y no en secuencias.

### Mantenimiento simplificado

Los usuarios de Campaign no necesitan ser expertos en bases de datos: ya no es necesario realizar operaciones complejas de mantenimiento de bases de datos o indexar tablas complejas.

## Funciones no disponibles temporales{#gs-unavailable-features}

Tenga en cuenta que algunas funciones aún no están disponibles en esta primera versión, como:

* Administración de recursos de marketing
* Distributed Marketing
* Administración de ofertas entrantes (módulo de interacción)
* Campaign Optimization (Optimización de la campaña)
* Gestor de respuestas
* Modelos de implementación híbridos/locales

## Funciones eliminadas{#gs-removed}

Para alinearse con la nueva arquitectura y el modelo de implementación de Campaign v8, algunas funciones históricas del Campaign Classic v7 ya no están disponibles en Campaign v8.

* Cupones
* Seguimiento web
* Encuestas
* Social Marketing
* Conector ACS (oferta principal)

