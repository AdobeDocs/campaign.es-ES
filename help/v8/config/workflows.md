---
solution: Campaign
product: Adobe Campaign
title: Introducción a la automatización de campañas
description: Introducción a la automatización de campañas
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
translation-type: tm+mt
source-git-commit: 2ea953145b645d376d5ea88b89350b45f024ea7d
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

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

Obtenga más información sobre los flujos de trabajo en estas secciones:

* [Introducción a los flujos de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* Actividades de flujo de trabajo
   * [Actividades de segmentación](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html): consulta, lista de lectura, enriquecimiento, unión y más
   * [Actividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html) de control de flujo: planificador, ramificación, alerta, señal externa, etc.
   * [Actividades](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) de acción: envíos multicanal, código JavaScript, actividades CRM, actualizar acumulado, etc.
   * [Actividades de evento](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html): transferencia de archivos, descarga de web y más
* [Conozca los casos de uso end-to-end](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/about-workflow-use-cases.html)
* [Crear una audiencia en un flujo de trabajo de campaña de marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)
* [Prácticas recomendadas de flujos de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
* [Flujos de trabajo técnicos integrados](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
* [Monitorización de la ejecución de flujos de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)

## Configuración de campañas recurrentes

Diseñe una instancia recurrente y cree una nueva instancia de envío cada vez que se ejecute. Por ejemplo, si el flujo de trabajo está diseñado para ejecutarse una vez a la semana, el resultado sería 52 envíos después de un año. Esto también significa que los registros se separarán por cada instancia de envío.

:arrow_upper_right: Aprenda a crear una campaña recurrente en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns).

## Configurar el ciclo de validación completo

Configure el proceso de aprobación para cada paso de los envíos y asegúrese de realizar una monitorización y un control completos de los distintos procesos de las campañas de marketing: segmentación, contenido, presupuesto, extracción y envío de una prueba.

Las notificaciones se envían a los operadores de Adobe Campaign que se establecen como revisores para informarles de una solicitud de aprobación.

:arrow_upper_right: Obtenga información sobre cómo configurar y administrar el proceso de aprobación en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html).


## Enviar alertas

Como operador de Campaign, puede recibir alertas cuando se produce un error.

Puede crear un flujo de trabajo que le permita monitorizar el estado de un conjunto de flujos de trabajo y enviar mensajes recurrentes a los supervisores.

:arrow_upper_right: Obtenga información sobre cómo crear un flujo de trabajo para monitorizar el estado de otros flujos de trabajo en la [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html?lang=en#step-1--creating-the-monitoring-workflow).

También puede recibir una alerta cuando se produzca un error

## Enviar informes automáticos

:arrow_upper_right: Obtenga información sobre cómo enviar automáticamente un informe a una lista de operadores [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html?lang=en#step-1--creating-the-recipient-list).


## Aprovechar los eventos de déclencheur

Utilice la mensajería transaccional de Campaign para automatizar los mensajes generados a partir de eventos activados desde sistemas de información. Estos mensajes transaccionales pueden ser factura, confirmación de pedido, confirmación de envío, cambio de contraseña, notificación de no disponibilidad del producto, extracto de cuenta o creación de cuenta de sitio web, por ejemplo. Estos mensajes se pueden enviar de forma individual o por lotes mediante correos electrónicos, SMS o notificaciones push.

:arrow_upper_right: Obtenga más información sobre las funcionalidades de mensajería transaccional en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=en#transactional-messaging).


Conecte Adobe Campaign y Adobe Analytics para recuperar acciones de usuario y enviar mensajes personalizados casi en tiempo real.

:arrow_upper_right: Aprenda a integrar Campaign con los déclencheur de Analytics en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en#integrating-with-adobe-experience-cloud).

:bulb: Aprenda a integrar Campaign con otras soluciones en [esta sección](../start/connect.md)
