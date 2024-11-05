---
title: Introducción a los mensajes
description: Introducción a los mensajes
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
source-git-commit: 0ff645a87700c038b78fb4cc45062822d6d97148
workflow-type: tm+mt
source-wordcount: '1305'
ht-degree: 89%

---

# Introducción a los mensajes {#gs-ac-msg}

Con Adobe Campaign, puede enviar campañas de canales múltiples, incluidos correos electrónicos, SMS, notificaciones push y correo postal, y medir su eficacia mediante varios informes dedicados. Estos mensajes están diseñados y enviados por medio de envíos y pueden personalizarse para cada destinatario.

Las funciones principales incluyen establecimiento de objetivos, definición y personalización de mensajes, ejecución de comunicaciones y los informes operativos asociados.

## Casos de uso {#gs-ac-delivery}

Para enviar mensajes, debe crear una entrega. El modo de creación de envíos depende de su caso de uso.

>[!NOTE]
>
>Al crear una entrega, debe seleccionar una plantilla. Las plantillas predeterminadas están disponibles para cada canal. Obtenga más información acerca de las plantillas de envío en [esta página](../send/create-templates.md).

### Mensajes de una sola toma {#msg-single}

Puede enviar mensajes de una sola toma manualmente al destinatario principal. Aprenda a enviar su primer mensaje en [esta sección](create-message.md)

![](assets/send-email.png)

### Mensajes en una campaña de marketing {#msg-campaign}

Puede enviar mensajes en el contexto de una [campaña de marketing](campaigns.md), definir un proceso de aprobación y enviarlos y realizar un seguimiento de ellos en un panel consolidado. Aprenda en [esta sección](../../automation/campaigns/marketing-campaign-deliveries.md)

![](assets/deliveries-in-a-campaign.png)

### Mensajes en un flujo de trabajo {#msg-wf}

Puede enviar mensajes a través de un [flujo de trabajo](../config/workflows.md) y automatizar los envíos. Aprenda en [esta página](../../automation/workflow/delivery.md)

![](assets/send-in-a-wf.png)

### Mensajes activados {#msg-trigger}

Puede [almacenar mensajes en Déclencheur](../send/transactional.md) de un evento. La mensajería transaccional (Centro de mensajes) es el módulo de Campaign diseñado para gestionar mensajes de déclencheur.  Obtenga más información acerca de la capacidad de los mensajes transaccionales en [esta sección](../architecture/architecture.md#transac-msg-archi)

Los pasos para configurar y enviar mensajes transaccionales se detallan en [esta página](../send/transactional.md)

## Elija su canal {#gs-channel}

Adobe Campaign v8 incluye los siguientes canales de envío:

* **Canal de correo electrónico**: los envíos de correo electrónico le permiten enviar correos electrónicos personalizados a la población objetivo. [Más información](#gs-channel-email)

* **Canales móviles**: los envíos en canales móviles permiten enviar mensajes personalizados a los dispositivos móviles de la población de público destinatario. [Más información](#gs-channel-sms)

* **Canal de aplicaciones móviles**: los envíos de aplicaciones móviles permiten enviar notificaciones a dispositivos con sistemas iOS y Android. [Más información](#gs-channel-push)

* **Canal de correo directo**: los envíos de correo directo permiten generar un archivo de extracción que contenga datos sobre la población de público destinatario. [Más información](#gs-channel-direct)


  En [esta sección](#other-channels) se describen otros canales.

  >[!NOTE]
  >
  >El número de canales disponibles depende del contrato. Compruebe el acuerdo de licencia.

### Canal de correo electrónico {#gs-channel-email}

El [canal de correo electrónico](../send/direct-mail.md) es uno de los canales principales de Adobe Campaign, el cual permite programar y enviar correos electrónicos personalizados a objetivos específicos.

Se pueden enviar diferentes tipos de correos electrónicos:

* Correos electrónicos de envío único: correos electrónicos que se pueden enviar una vez a un destino definido. Suelen utilizarse para promocionar un contenido específico que se prepara y se envía una sola vez (newsletter, correo electrónico promocional, etc.).
* Correos electrónicos recurrentes: en una campaña, envíe el mismo correo electrónico regularmente y añada cada envío y sus informes periódicamente. Se envía el mismo correo electrónico, pero normalmente a un destino diferente, en función del destino apto para el día de la entrega. Un ejemplo común es un correo electrónico de cumpleaños. Para obtener más información, consulte [envíos recurrentes](../../automation/workflow/recurring-delivery.md).
* Correos electrónicos de transacción: correos electrónicos individuales que se activan según el comportamiento de los clientes. Consulte [mensajería transaccional](../send/transactional.md).

Para obtener más información sobre el uso y recomendaciones de envío, consulte [Prácticas recomendadas de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=es#sending-messages){target="_blank"} de Adobe Campaign Classic

Para obtener más información sobre los distintos tipos de envíos, consulte [esta sección](#types-of-deliveries).

### Canal móvil {#gs-channel-sms}

Adobe Campaign le permite enviar mensajes [SMS](../send/sms/sms.md) y de [LINE](../send/line.md) a móviles.

En los mensajes SMS, puede crear, modificar y personalizar mensajes solo de formato de texto. También puede obtener una previsualización de los mensajes SMS antes de enviarlos.

Para los mensajes de LINE, puede enviar texto o imágenes y vínculos.

Para enviar mensajes SMS o de LINE a un teléfono móvil se necesita:

* Una cuenta externa configurada en el canal **[!UICONTROL Mobile (SMS)]** o en el canal **[!UICONTROL LINE]**.
* Una plantilla de envíos de SMS o LINE vinculada correctamente a esta cuenta externa.


### Canal de notificaciones push {#gs-channel-push}

Puede usar Adobe Campaign para enviar [notificaciones push](../send/push.md) personalizadas y segmentadas a dispositivos móviles iOS y Android mediante aplicaciones dedicadas. Una vez realizados los pasos de configuración e integración, se pueden crear y realizar los envíos de iOS y Android y enviarlos con Adobe Campaign. También puede diseñar y enviar notificaciones enriquecidas con imágenes o vídeos a dispositivos Android.

### Canal de correo directo {#gs-channel-direct}

[Correo directo](../send/direct-mail.md) es un canal sin conexión que permite crear, personalizar y generar un archivo externo para compartirlo con los proveedores de correo directo. Utilice este canal para organizar canales en línea y sin conexión en los recorridos del cliente.

Al preparar un envío de correo directo, Adobe Campaign genera un archivo con todos los perfiles de destino y la información de contacto elegida (por ejemplo, una dirección postal). Después, puede enviar este archivo al proveedor de correo directo que se encarga del envío real.


### Otros canales {#other-channels}

Adobe Campaign también proporciona una plantilla de envío por teléfono que se utiliza para crear envíos externos. El uso de este canal implica la implementación de metodologías dedicadas para procesar archivos de salida. Los pasos de configuración son los mismos que para el [canal de correo directo](../send/direct-mail.md).

>[!NOTE]
>
>El canal del teléfono no es un canal integrado. Su implementación requiere la participación de un asesor o un socio de Adobe. Para obtener más información, póngase en contacto con su representante de Adobe.

Los envíos de tipo “Otro” utilizan una plantilla técnica específica que no ejecuta un proceso: esto les permite administrar las acciones de marketing ejecutadas fuera de la plataforma de Adobe Campaign.

Este canal no tiene un mecanismo específico. Es un canal genérico con su propia opción de enrutamiento de cuenta externa, tipo de plantilla de envío y actividad de flujo de trabajo de campaña, igual que cualquier otro canal de comunicación disponible en Adobe Campaign. Este canal se ha diseñado únicamente para fines descriptivos, por ejemplo para definir envíos para los que se desea mantener un seguimiento del destinatario de una campaña realizada en una herramienta que no sea Adobe Campaign.

## Elija el tipo de envío {#types-of-deliveries}

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

## Adición de personalización {#personalization}

Los mensajes enviados por Adobe Campaign se pueden personalizar de varias formas. [Obtenga más información acerca las funcionalidades de personalización](../send/personalize.md)

Puede hacer lo siguiente:

* Insertar campos de personalización dinámicos. [Más información](../send/personalization-fields.md)
* Inserte bloques de personalización predefinidos. [Más información](../send/personalization-blocks.md)
* Cree contenido condicional. [Más información](../send/conditions.md)


## Envío y seguimiento {#gs-tracking-logs}

La monitorización de los envíos una vez enviados es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Puede monitorizarlas después de enviar un envío, así como comprender cómo se administran los errores y las cuarentenas.

Aprenda a monitorizar los envíos en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es#sending-messages){target="_blank"}

