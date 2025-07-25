---
title: Introducción a los mensajes
description: Introducción a los mensajes
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a523e76d-776c-47d3-9c15-34241cee1092
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 74%

---

# Introducción a los mensajes {#gs-ac-msg}

Con Adobe Campaign, puede enviar campañas de canales múltiples, incluidos correos electrónicos, SMS, notificaciones push y correo postal, y medir su eficacia mediante varios informes dedicados. Estos mensajes están diseñados y enviados por medio de envíos y pueden personalizarse para cada destinatario.

Las funciones principales incluyen establecimiento de objetivos, definición y personalización de mensajes, ejecución de comunicaciones y los informes operativos asociados.

## Casos de uso {#gs-ac-delivery}

Para enviar mensajes, debe crear una entrega. El modo de creación de envíos depende de su caso de uso.

>[!NOTE]
>
>Al crear una entrega, debe seleccionar una plantilla. Las plantillas predeterminadas están disponibles para cada canal. Obtenga más información acerca de las plantillas de envío en [esta página](../send/create-templates.md).

1. **Mensajes de una sola toma**: puede enviar mensajes de una sola toma a una audiencia. Aprenda a enviar su primer mensaje en [esta sección](create-message.md).

   ![](assets/send-email.png)

1. **Mensajes en una campaña de marketing**: puede enviar mensajes en el contexto de una [campaña de marketing](campaigns.md), definir un proceso de aprobación y enviarlos y realizar un seguimiento de ellos en un panel consolidado. Aprenda en [esta sección](../../automation/campaigns/marketing-campaign-deliveries.md).

   ![](assets/deliveries-in-a-campaign.png)

1. **Mensajes en un flujo de trabajo**: puede enviar mensajes a través de un [flujo de trabajo](../config/workflows.md) y automatizar los envíos. Aprenda en [esta página](../../automation/workflow/delivery.md).

   ![](assets/send-in-a-wf.png)

1. **Mensajes activados** - Puede [mensajes de Déclencheur](../send/transactional.md) de un evento. La mensajería transaccional (Centro de mensajes) es el módulo de Campaign diseñado para gestionar mensajes de déclencheur. Los pasos para configurar y enviar mensajes transaccionales se detallan en [esta página](../send/transactional.md)

## Canales de comunicación {#gs-channel}

Adobe Campaign v8 viene con los canales de envío enumerados a continuación. Los canales disponibles en su entorno dependen del contrato. Compruebe el acuerdo de licencia.

* **Canal de correo electrónico**: los envíos de correo electrónico le permiten enviar correos electrónicos personalizados a la población objetivo. [Más información](../send/email.md)

* **Canales móviles**: los envíos en canales móviles permiten enviar mensajes personalizados a los dispositivos móviles de la población de público destinatario. Puedes enviar [mensajes SMS](../send/sms/sms.md) y [LINE](../send/line.md) a móviles.

* **Canal de aplicaciones móviles**: puede usar Adobe Campaign para enviar [notificaciones push](../send/push.md) personalizadas y segmentadas en dispositivos móviles iOS y Android mediante aplicaciones especializadas. Una vez realizados los pasos de configuración e integración, se pueden crear y realizar los envíos de iOS y Android y enviarlos con Adobe Campaign. También puede diseñar y enviar notificaciones enriquecidas con imágenes o vídeos a dispositivos Android.

* **Canal de correo postal**: [Correo postal](../send/direct-mail.md) es un canal sin conexión que le permite crear, personalizar y generar un archivo externo para compartirlo con sus proveedores de correo postal. Utilice este canal para organizar canales en línea y sin conexión en los recorridos del cliente.

  Al preparar un envío de correo directo, Adobe Campaign genera un archivo con todos los perfiles de destino y la información de contacto elegida (por ejemplo, una dirección postal). Después, puede enviar este archivo al proveedor de correo directo que se encarga del envío real.


* **Otros canales**: Adobe Campaign también incluye una plantilla de envíos telefónicos, que se usa para crear envíos externos. El uso de este canal implica la implementación de metodologías dedicadas para procesar archivos de salida. Los pasos de configuración son los mismos que para el [canal de correo directo](../send/direct-mail.md).

  >[!NOTE]
  >
  >El canal del teléfono no es un canal integrado. Su implementación requiere la participación de un asesor o un socio de Adobe. Para obtener más información, póngase en contacto con su representante de Adobe.

  Los envíos de tipo “Otro” utilizan una plantilla técnica específica que no ejecuta un proceso: esto les permite administrar las acciones de marketing ejecutadas fuera de la plataforma de Adobe Campaign.

  Este canal no tiene un mecanismo específico. Es un canal genérico con su propia opción de enrutamiento de cuenta externa, tipo de plantilla de envío y actividad de flujo de trabajo de campaña, igual que cualquier otro canal de comunicación disponible en Adobe Campaign. Este canal se ha diseñado únicamente para fines descriptivos, por ejemplo para definir envíos para los que se desea mantener un seguimiento del destinatario de una campaña realizada en una herramienta que no sea Adobe Campaign.

## Tipos de envío {#types-of-deliveries}

Existen tres tipos de objetos de entrega en Campaign:

### Entrega única {#single-delivery}

Una **entrega** es un objeto de envío independiente que se ejecuta una vez. Puede duplicarse y prepararse de nuevo; sin embargo, cuando esté en su estado final (cancelado, detenido, finalizado), no se puede volver a utilizar.

Las entregas se pueden crear desde la lista de entregas o dentro de un flujo de trabajo mediante una actividad de [entrega](../../automation/workflow/delivery.md).

Los flujos de trabajo también proporcionan actividades de entrega específicas según el tipo de canal que desee utilizar. Para obtener más información sobre estas actividades, consulte [esta sección](../../automation/workflow/cross-channel-deliveries.md).

### Entrega recurrente {#recurring-delivery}

Hay un **envío recurrente** disponible en el contexto de un flujo de trabajo. Esto permite crear un nuevo envío cada vez que se ejecuta la actividad. Así se evita tener que crear un nuevo envío para las tareas recurrentes. Por ejemplo, si ejecuta este tipo de actividad una vez al mes, tras un año acaba teniendo 12 envíos.

Las entregas recurrentes se crean en los flujos de trabajo a través de la actividad de [entrega recurrente](../../automation/workflow/recurring-delivery.md). En esta sección se muestra un ejemplo de esta actividad: [Creación de una entrega recurrente en un flujo de trabajo de objetivos](../../automation/workflow/send-a-birthday-email.md).

### Entrega continua {#continuous-delivery}

Hay un **envío continuo** disponible en el contexto de un flujo de trabajo. Esto permite añadir nuevos destinatarios a un envío existente, lo que evita tener que crear un nuevo envío cada vez que se ejecuta.

Si cambia la información de la entrega (contenido, nombre, etc.), se crea un nuevo objeto de envío en la ejecución de la entrega. Si no se ha cambiado ninguna información, se vuelve a utilizar el mismo objeto de envío y los “logs” de entrega y seguimiento se añaden en el mismo objeto.

Por ejemplo, si ejecuta este tipo de actividad una vez al mes, acaba teniendo un solo envío después de un año (siempre y cuando no haya realizado ningún cambio en la entrega).

Las entregas continuas se crean dentro de flujos de trabajo a través de la [Actividad de entrega continua](../../automation/workflow/continuous-delivery.md).

## Funciones de Personalization {#personalization}

Los mensajes enviados por Adobe Campaign se pueden personalizar de varias formas. [Obtenga más información acerca las funcionalidades de personalización](../send/personalize.md)

Puede hacer lo siguiente:

* Insertar campos de personalización dinámicos. [Más información](../send/personalization-fields.md)
* Inserte bloques de personalización predefinidos. [Más información](../send/personalization-blocks.md)
* Cree contenido condicional. [Más información](../send/conditions.md)


## Seguimiento y monitorización {#gs-tracking-logs}

La monitorización de los envíos una vez enviados es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Puede monitorizarlas después de enviar un envío, así como comprender cómo se administran los errores y las cuarentenas.

Obtenga información sobre cómo monitorizar los envíos en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es#sending-messages){target="_blank"}
