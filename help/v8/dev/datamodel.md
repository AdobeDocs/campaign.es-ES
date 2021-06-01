---
product: Adobe Campaign
title: 'Introducción al modelo de datos de Campaign '
description: 'Introducción al modelo de datos de Campaign '
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 4%

---

# Introducción al modelo de datos de Campaign {#gs-ac-datamodel}

Adobe Campaign viene con un modelo de datos predefinido. Esta sección proporciona algunos detalles sobre las tablas integradas del modelo de datos de Adobe Campaign y su interacción. Adobe Campaign se basa en una base de datos de Cloud que contiene tablas vinculadas.

La estructura básica del modelo de datos de Adobe Campaign se puede describir de la siguiente manera:

* **Tabla** de destinatarios: El modelo de datos se basa en una tabla principal que, de forma predeterminada, es la tabla de destinatarios (nmsRecipient). Esta tabla permite almacenar todos los perfiles de marketing.

   [!DNL :bulb:] Para obtener más información sobre la tabla de destinatarios, consulte  [esta sección](#ootb-profiles).

* **Tabla** de envío: El modelo de datos también incluye una parte dedicada a almacenar todas las actividades de marketing. Normalmente es la tabla Delivery (NmsDelivery). Cada registro de esta tabla representa una acción de envío o una plantilla de envío. Contiene todos los parámetros necesarios para realizar envíos como destinatario, contenido, etc.

* **Registros tablas**: Estas tablas almacenan todos los registros asociados con la ejecución de las campañas.

   Los registros de envío son todos los mensajes enviados a los destinatarios o dispositivos en todos los canales. La tabla principal Delivery logs (NmsBroadLogRcp) contiene los registros de envío de todos los destinatarios.
La tabla principal Tracking logs (NmsTrackingLogRcp) almacena los registros de seguimiento de todos los destinatarios. Los registros de seguimiento hacen referencia a reacciones de los destinatarios, como aperturas de correo electrónico y clics. Cada reacción corresponde a un registro de seguimiento.
Los registros de envío y los registros de seguimiento se eliminan después de un periodo determinado, que se especifica en Adobe Campaign y se puede modificar. Por lo tanto, es muy recomendable exportar los registros de forma regular.

* **Tablas** técnicas: Recopile datos técnicos utilizados para el proceso aplicativo, incluidos operadores y derechos de usuario (xtkGroup), carpetas (XtkFolder).

>[!NOTE]
>
>Para acceder a la descripción de cada tabla, vaya a Administración > Configuración > Esquemas de datos, seleccione un recurso de la lista y haga clic en la pestaña **Documentación**.

Al comenzar con Adobe Campaign, debe evaluar el modelo de datos predeterminado para comprobar qué tabla es la más adecuada para almacenar los datos de marketing.

Puede utilizar la tabla de destinatarios predeterminada con los campos predeterminados, como se describe en [esta sección](#ootb-profiles). Si es necesario, puede ampliarlo con dos mecanismos:

* [Amplíe una ](extend-schema.md) tabla existente con campos nuevos. Por ejemplo, puede agregar un nuevo campo &quot;Lealtad&quot; a la tabla de destinatarios.
* [Cree una nueva tabla](create-schema.md), por ejemplo una tabla &quot;Purchase&quot; que enumere todas las compras realizadas por cada perfil de la base de datos y vincúlelo a la tabla Recipient .

[!DNL :bulb:] Descubra las prácticas recomendadas al trabajar con el modelo de datos de Campaign en  [esta sección](datamodel-best-practices.md).

## Tabla de perfil integrada {#ootb-profiles}

La tabla de destinatarios integrada (nmsrecipient) en Adobe Campaign proporciona un buen punto de partida para crear su modelo de datos. Tiene varios campos predefinidos y vínculos de tabla que se pueden ampliar fácilmente. Esto resulta especialmente útil cuando se dirige principalmente a destinatarios, ya que se ajusta a un modelo de datos sencillo centrado en los destinatarios.

Los beneficios de utilizar la tabla de destinatarios estándar son:

* Uso de funciones clave como suscripciones, listas de fuentes y mucho más
* Proporcionar una base de datos de marketing con un modelo de datos centrado en el destinatario
* Implementación más rápida
* Fácil mantenimiento por parte de socios y soporte

Es posible ampliar la tabla de destinatarios, pero no reducir el número de campos o vínculos de la tabla.

[!DNL :bulb:] Aprenda a ampliar un esquema existente en  [esta sección](extend-schema.md).

[!DNL :arrow_upper_right:] Descubra ejemplos de extensiones de tabla de destinatarios integradas en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)

También puede utilizar una tabla de destinatarios diferente para adaptarla mejor a sus necesidades empresariales o funcionales. Este método viene con limitaciones y se describe en [esta sección](custom-recipient.md).

## Tablas de Campaign y base de datos de Cloud

Para comprender mejor la administración de tablas en Campaign v8, tenga en cuenta que las tablas se duplican entre Campaign y su base de datos de Snowflake Cloud.

[!DNL :bulb:] Obtenga más información sobre la estrategia y los mecanismos de replicación en  [esta sección](../config/replication.md).

**Temas relacionados**

[!DNL :bulb:] Descubra cómo importar perfiles en  [esta ](../start/import.md)
[!DNL :bulb:] secciónObtenga más información sobre las audiencias de Campaign en  [esta sección](../start/audiences.md)
