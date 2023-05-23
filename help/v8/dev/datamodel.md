---
title: Introducción al modelo de datos de Campaign
description: Empiece con el modelo de datos de Campaign y combine los datos de sus fuentes para favorecer sus comunicaciones y los resultados de marketing.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 6%

---

# Introducción al modelo de datos de Campaign {#gs-ac-datamodel}

Adobe Campaign viene con un modelo de datos predefinido. En esta sección se proporcionan algunos detalles sobre las tablas integradas del modelo de datos de Adobe Campaign y su interacción. Adobe Campaign se basa en una base de datos en la nube que contiene tablas vinculadas entre sí.

La estructura básica del modelo de datos de Adobe Campaign se puede describir de la siguiente manera:

* **Tabla de destinatarios**: el modelo de datos se basa en una tabla principal que es de forma predeterminada la tabla de destinatario (nmsRecipient). Esta tabla almacena todos los perfiles de marketing.

   ![](../assets/do-not-localize/glass.png) Para obtener más información sobre la tabla de destinatarios, consulte [esta sección](#ootb-profiles).

* **Tabla de envío**: el modelo de datos también incluye una parte dedicada a almacenar todas las actividades de marketing. Normalmente es la tabla Delivery (NmsDelivery). Cada registro de esta tabla representa una acción de envío o una plantilla de envío. Contiene todos los parámetros necesarios para realizar envíos como destinatario, contenido, etc.

* **Tablas de registros**: Estas tablas almacenan todos los registros asociados con la ejecución de las campañas.

   Los &quot;logs&quot; de entrega son todos los mensajes enviados a los destinatarios o dispositivos a través de todos los canales. La tabla principal de registros de entregas (NmsBroadLogRcp) contiene los registros de entregas de todos los destinatarios.
La tabla principal de registros de seguimiento (NmsTrackingLogRcp) almacena los registros de seguimiento de todos los destinatarios. Los registros de seguimiento hacen referencia a reacciones de los destinatarios, como aperturas de correos electrónicos y clics. Cada reacción corresponde a un registro de seguimiento.
Los registros de envío y los registros de seguimiento se eliminan después de un período determinado, que se especifica en Adobe Campaign y se puede modificar. Por lo tanto, es muy recomendable exportar los registros de forma regular.

* **Tablas técnicas**: recopile datos técnicos utilizados para el proceso aplicativo, incluidos operadores y derechos de usuario (xtkGroup) y carpetas (XtkFolder).

>[!NOTE]
>
>Para acceder a la descripción de cada tabla, vaya a Administración > Configuración > Esquemas de datos, seleccione un recurso de la lista y haga clic en **Documentación** pestaña.

Al comenzar con Adobe Campaign, debe evaluar el modelo de datos predeterminado para comprobar qué tabla es la más adecuada para almacenar los datos de marketing.

Puede utilizar la tabla de destinatarios predeterminada con los campos predeterminados, como se describe en [esta sección](#ootb-profiles). Si es necesario, se puede ampliar con dos mecanismos:

* [Ampliación de una tabla existente](extend-schema.md) con campos nuevos. Por ejemplo, puede agregar un nuevo campo &quot;Fidelidad&quot; a la tabla Destinatario.
* [Crear una nueva tabla](create-schema.md), por ejemplo, una tabla &quot;Purchase&quot; que enumera todas las compras realizadas por cada perfil de la base de datos y la vincula a la tabla Recipient.

![](../assets/do-not-localize/glass.png) Descubra las prácticas recomendadas al trabajar con el modelo de datos de Campaign en [esta sección](datamodel-best-practices.md).

## Tabla de perfil integrada {#ootb-profiles}

La tabla de destinatarios integrada (nmsrecipient) en Adobe Campaign proporciona un buen punto de partida para crear el modelo de datos. Tiene una serie de campos predefinidos y vínculos de tabla que se pueden ampliar fácilmente. Esto resulta particularmente útil cuando se segmenta principalmente a destinatarios, ya que se ajusta a un modelo de datos sencillo centrado en el destinatario.

Las ventajas de utilizar la tabla de destinatarios estándar son las siguientes:

* Trabajo listo para usar con funcionalidades clave como suscripciones, listas semilla y mucho más
* Proporción de una base de datos de marketing con un modelo de datos centrado en el destinatario
* Implementación más rápida
* Mantenimiento sencillo por parte del soporte y los socios

Es posible ampliar la tabla de destinatarios, pero no reducir el número de campos o vínculos de la tabla.

![](../assets/do-not-localize/glass.png) Obtenga información sobre cómo ampliar un esquema existente en [esta sección](extend-schema.md).

![](../assets/do-not-localize/book.png) Descubra ejemplos de extensiones de tabla de destinatarios integradas en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#extending-a-table){target="_blank"}

También puede utilizar una tabla de destinatarios diferente para adaptarse mejor a sus necesidades empresariales o funcionales. Este método viene con limitaciones y se describe en [esta sección](custom-recipient.md).

## Tablas de Campaign y base de datos en la nube

Para comprender mejor la administración de tablas en Campaign v8, tenga en cuenta que, en el contexto de un [Implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), las tablas se duplican entre Campaign y su base de datos de Snowflake Cloud.

![](../assets/do-not-localize/glass.png) Obtenga más información acerca de la estrategia y los mecanismos de replicación en [esta sección](../architecture/replication.md).

**Temas relacionados**

![](../assets/do-not-localize/glass.png) Descubra cómo importar perfiles en [esta sección](../start/import.md)
![](../assets/do-not-localize/glass.png) Obtenga más información acerca de las audiencias de Campaign en [esta sección](../start/audiences.md)
