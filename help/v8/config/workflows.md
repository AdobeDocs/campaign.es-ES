---
product: Adobe Campaign
title: Administrar y automatizar procesos con flujos de trabajo de Adobe Campaign
description: Introducción a los flujos de trabajo
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 41ea85bc3c616ed7cdd0718ff3368aab971a5352
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 20%

---

# Administrar y automatizar procesos

Configure Campaign para aprovechar las potentes capacidades de automatización de campañas de marketing.

Puede configurar:

* Flujos de trabajo
* Campañas recurrentes
* Ciclo de validación completo
* Alertas
* Envío automático de informes
* Eventos activados

## Diseñe y utilice flujos de trabajo{#gs-ac-wf}

Utilice los flujos de trabajo de Adobe Campaign para mejorar la velocidad y la escala de cada aspecto de las campañas de marketing, desde la creación de segmentos y la preparación de mensajes hasta la entrega.

Aprenda a diseñar flujos de trabajo en estos [casos de uso de extremo a extremo](#end-to-end-uc).

Obtenga más información sobre los flujos de trabajo, la interfaz de usuario y la ejecución en la documentación de Campaign Classic v7 :

[!DNL :arrow_upper_right:]  [Introducción a los flujos de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* Actividades de flujo de trabajo:
   * [Actividades de segmentación](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html): Consulta, lista de lectura, enriquecimiento, unión, etc.
   * [Actividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html) de control de flujo: Planificador, ramificación, alerta, señal externa, etc.
   * [Actividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) de acción: Envíos multicanal, código JavaScript, actividades CRM, Actualizar acumulado, etc.
   * [Actividades de evento](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html): Transferencia de archivos, descarga de web y más
      [!DNL :arrow_upper_right:]  [Crear una audiencia en un flujo de trabajo de campaña de marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)

      [!DNL :arrow_upper_right:]  [Prácticas recomendadas con flujos de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
      [!DNL :arrow_upper_right:] [Flujos de trabajo técnicos integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
      [!DNL :arrow_upper_right:] [Monitorización de la ejecución de flujos de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)


## Configuración de campañas recurrentes

Diseñe un flujo de trabajo recurrente y cree una nueva instancia de envío cada vez que se ejecute el flujo de trabajo. Por ejemplo, si el flujo de trabajo está diseñado para ejecutarse una vez a la semana, el resultado sería 52 envíos después de un año. Esto también significa que los registros se separarán por cada instancia de envío.

[!DNL :arrow_upper_right:] Aprenda a crear una campaña recurrente en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns).


## Aprovechar los eventos de déclencheur

Utilice la mensajería transaccional de Campaign para automatizar los mensajes generados a partir de eventos activados desde sistemas de información. Estos mensajes transaccionales pueden ser factura, confirmación de pedido, confirmación de envío, cambio de contraseña, notificación de no disponibilidad del producto, extracto de cuenta o creación de cuenta de sitio web, por ejemplo. Estos mensajes se pueden enviar de forma individual o en lote por correo electrónico, SMS o notificaciones push.

[!DNL :bulb:] Obtenga más información sobre las funcionalidades de mensajería transaccional en  [esta sección](../send/transactional.md).

Conecte Adobe Campaign y Adobe Analytics para recuperar acciones de usuario y enviar mensajes personalizados casi en tiempo real.

[!DNL :bulb:] Aprenda a integrar Campaign con otras soluciones en  [esta sección](../start/connect.md)


## Casos de uso de extremo a extremo del flujo de trabajo{#end-to-end-uc}

En esta sección, encontrará varios casos de uso que aprovechan las capacidades de los Flujos de trabajo de Campaign. Estos casos de uso se crean en Adobe Campaign Classic v7 y se aplican a Adobe Campaign v8.

### Entregas {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [Prueba A/B](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html)

   Obtenga información sobre cómo comparar dos contenidos de entrega de correo electrónico a través de un flujo de trabajo de objetivo. El mensaje y el texto son idénticos en ambos envíos: solo cambia el diseño. La población objetivo se divide en tres: dos grupos de prueba y la población restante. Se envía una versión diferente a cada grupo de prueba.

* [Envío de correo electrónico de cumpleaños](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html)

   Este caso de uso detalla cómo planificar la entrega de un correo electrónico recurrente a una lista de destinatarios en el día de su cumpleaños.

* [Carga de contenido de entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)

   Cuando el contenido de su envío está disponible en un archivo HTML ubicado en un servidor remoto, puede cargar fácilmente este contenido en los envíos de Adobe Campaign.

* [Flujo de trabajo de entrega por canales cruzados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)

   Obtenga información sobre cómo crear un flujo de trabajo de envío entre canales. El objetivo es segmentar una audiencia de los destinatarios de la base de datos en grupos diferentes y enviar un correo electrónico al primer grupo y un SMS al otro.

* [Enriquecimiento de correo electrónico con campos de datos personalizados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)

   Aprenda a enviar un correo electrónico con campos de datos personalizados a perfiles que celebran su cumpleaños este mes. El correo electrónico incluirá un cupón válido una semana antes y después de su cumpleaños.

* [Automatización de la creación, edición y publicación de contenido](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html)

   Obtenga información sobre cómo automatizar la creación y el envío de un bloque de contenido con el complemento Gestión de contenido de Campaign.


### Monitorización {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Envío de un informe a una lista](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html)

   Obtenga información sobre cómo generar un informe mensual integrado Tracking indicators en formato PDF y enviarlo a una lista de operadores de Campaign.

* [Supervisión de los flujos de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html)

   Aprenda a crear un flujo de trabajo que le permita monitorizar el estado de un conjunto de flujos de trabajo que estén &quot;en pausa&quot;, &quot;detenidos&quot; o &quot;con errores&quot;.

* [Envío de alertas personalizadas a operadores](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html)

   Aprenda a enviar una alerta a un operador que contendrá el nombre de los perfiles que abrieron una newsletter pero que no hicieron clic en el vínculo que contenía.

### Administración de datos {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordinación de actualizaciones de datos](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html)

   Obtenga información sobre cómo comprobar que el proceso de actualización ha finalizado antes de ejecutar otra operación de actualización. Para ello, se configura una variable de instancia y se deja que el flujo de trabajo pruebe si la instancia se está ejecutando para decidir si continuar o no con la ejecución del flujo de trabajo y realizar la actualización.

* [Creación de una lista de resumen](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html)

   Aprenda a crear un flujo de trabajo que, después de recopilar archivos y de seguir varios enriquecimientos, le permita crear una lista de resumen. El ejemplo se basa en una lista de contactos que realizaron compras en una tienda.

* [Enriquecimiento de datos](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)

   Aprenda a enviar envíos personalizados a perfiles que participaron en la competición más reciente en función de su puntuación.

* [Uso de agregados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html)

   Obtenga información sobre cómo identificar los últimos destinatarios agregados a la base de datos.

* [Actualización trimestral de la lista con una consulta incremental](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html)

   Aprenda a utilizar una consulta incremental para actualizar automáticamente una lista de destinatarios.

* [Configuración de un flujo de trabajo de importación recurrente](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html)

   Aprenda a diseñar un flujo de trabajo que se pueda reutilizar para importar perfiles procedentes de un CRM en la base de datos de Adobe Campaign.

### Segmentación {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Consulta de la tabla de destinatarios](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html)

   Obtenga información sobre cómo recuperar los nombres y correos electrónicos de los destinatarios cuyo dominio de correo electrónico es &quot;orange.co.uk&quot; y que no viven en Londres.

* [Información de envío de consulta](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html)

   Aprenda a definir consultas sobre la información de envío para recuperar el comportamiento del perfil.

* [Calcular agregados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html)

   Aprenda a contar la cantidad de perfiles que viven en Londres, según el sexo.

* [Realización de consultas con una relación de varios a varios](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html)

   Obtenga información sobre cómo encontrar perfiles no contactados durante los últimos 7 días.

* [Llame a una variable de instancia en una consulta](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example)

   Aprenda a utilizar una variable de instancia para calcular dinámicamente el porcentaje dividido que se aplicará a una población.

