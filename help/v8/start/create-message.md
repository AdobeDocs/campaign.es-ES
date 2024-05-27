---
title: Introducción a los mensajes
description: Introducción a los mensajes
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 7f6c394f56d517c0a675e0fd2341bb6ef98044f0
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 72%

---

# Introducción a los mensajes {#gs-ac-audiences}

## Canales de envío {#gs-ac-channels}

Con Adobe Campaign, puede enviar campañas de canales múltiples, incluidos correos electrónicos, SMS, notificaciones push y correo postal, y medir su eficacia mediante varios informes dedicados. Estos mensajes están diseñados y enviados por medio de envíos y pueden personalizarse para cada destinatario.

Las funciones principales incluyen direccionamiento, definición y personalización de mensajes, ejecución de comunicaciones y los informes operativos asociados. El punto de acceso funcional principal es el asistente de entrega. Este punto de acceso lleva a varias funciones incluidas en Adobe Campaign.

Adobe Campaign v8 incluye los siguientes canales de envío:

* **Canal de correo electrónico**: los envíos de correo electrónico le permiten enviar correos electrónicos personalizados a la población objetivo. [Más información](#gs-channel-email)

* **Canales móviles**: las entregas en canales móviles permiten enviar mensajes personalizados en dispositivos móviles a la población objetivo. [Más información](#gs-channel-sms)

* **Canal de aplicaciones móviles**: las entregas de aplicaciones móviles permiten enviar notificaciones a dispositivos iOS y Android. [Más información](#gs-channel-push)

* **Canal de correo postal**: las entregas de correo postal permiten generar un archivo de extracción que contenga datos sobre la población objetivo. [Más información](#gs-channel-direct)


  Otros canales se describen en [esta sección](#other-channels).

  >[!NOTE]
  >
  >El número de canales disponibles depende del contrato. Compruebe el acuerdo de licencia.

## Elige tu canal {#gs-channel}

### Canal de correo electrónico {#gs-channel-email}

El [canal de correo electrónico](../send/direct-mail.md) es uno de los canales principales de Adobe Campaign, el cual permite programar y enviar correos electrónicos personalizados a objetivos específicos.

Se pueden enviar diferentes tipos de correos electrónicos:

* Correos electrónicos de envío único: correos electrónicos que se pueden enviar una vez a un destino definido. Suelen utilizarse para promocionar un contenido específico que se prepara y se envía una sola vez (newsletter, correo electrónico promocional, etc.).
* Correos electrónicos recurrentes: en una campaña, envíe el mismo correo electrónico regularmente y añada cada envío y sus informes periódicamente. Se envía el mismo correo electrónico, pero normalmente a un destino diferente, en función del destino apto para el día de la entrega. Un ejemplo común es un correo electrónico de cumpleaños. Para obtener más información, consulte [envíos recurrentes](../../automation/workflow/recurring-delivery.md).
* Correos electrónicos de transacción: correos electrónicos individuales que se activan según el comportamiento de los clientes. Consulte [mensajería transaccional](../send/transactional.md).

Para obtener más información sobre el uso de las entregas y las recomendaciones, consulte Adobe Campaign Classic [Prácticas recomendadas de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html#sending-messages){target="_blank"}

Para obtener más información sobre los distintos tipos de envíos, consulte [esta sección](#types-of-deliveries).

### Canal móvil {#gs-channel-sms}

Adobe Campaign le permite enviar mensajes [SMS](../send/sms.md) y de [LINE](../send/line.md) a móviles.

En los mensajes SMS, puede crear, modificar y personalizar mensajes solo de formato de texto. También puede obtener una previsualización de los mensajes SMS antes de enviarlos.

Para los mensajes de LINE, puede enviar texto o imágenes y vínculos.

Para enviar mensajes SMS o de LINE a un teléfono móvil se necesita:

* Una cuenta externa configurada en el canal **[!UICONTROL Mobile (SMS)]** o en el canal **[!UICONTROL LINE]**.
* Una plantilla de envíos de SMS o LINE vinculada correctamente a esta cuenta externa.


### Canal de notificaciones push {#gs-channel-push}

Puede utilizar Adobe Campaign para enviar mensajes personalizados y segmentados [notificaciones push](../send/push.md) en dispositivos móviles iOS y Android, a través de aplicaciones especializadas. Una vez realizados los pasos de configuración e integración, se pueden crear y realizar las entregas de iOS y Android con Adobe Campaign. También puede diseñar y enviar notificaciones rich con imágenes o vídeos a dispositivos Android.

### Canal de correo directo {#gs-channel-direct}

[Correo directo](../send/direct-mail.md) es un canal sin conexión que le permite crear, personalizar y generar un archivo externo para compartirlo con sus proveedores de correo postal. Utilice este canal para orquestar canales en línea y sin conexión en los recorridos del cliente.

Al preparar una entrega de correo postal, Adobe Campaign genera un archivo con todos los perfiles de destino y la información de contacto elegida (por ejemplo, una dirección postal). A continuación, puede enviar este archivo a su proveedor de correo postal, que se encargará del envío real.


### Otros canales {#other-channels}

Adobe Campaign también incluye una plantilla de envíos telefónicos, que se utiliza para crear envíos externos. El uso de este canal implica la implementación de metodologías dedicadas para procesar archivos de salida. Los pasos de configuración son los mismos que para el [canal de correo directo](../send/direct-mail.md).

>[!NOTE]
>
>El canal telefónico no es un canal integrado. Su implementación requiere la participación de un asesor o un socio de Adobe. Para obtener más información, póngase en contacto con su representante de Adobe.

Los envíos de tipo &quot;Otros&quot; utilizan una plantilla técnica específica que no ejecuta un proceso: esto les permite administrar las acciones de marketing ejecutadas fuera de la plataforma de Adobe Campaign.

Este canal no tiene un mecanismo específico. Es un canal genérico con su propia opción de enrutamiento de cuenta externa, tipo de plantilla de envíos y actividad de flujo de trabajo de campaña, igual que cualquier otro canal de comunicación disponible en Adobe Campaign. Este canal se ha diseñado únicamente para fines descriptivos, por ejemplo para definir envíos para los que se desea mantener un seguimiento del destinatario de una campaña realizada en una herramienta que no sea Adobe Campaign.

## Elija el tipo de entrega {#types-of-deliveries}

Existen tres tipos de objetos de entrega en Campaign:

### Entrega única {#single-delivery}

Una **entrega** es un objeto de envío independiente que se ejecuta una vez. Puede duplicarse y prepararse de nuevo; sin embargo, cuando esté en su estado final (cancelado, detenido, finalizado), no se puede volver a utilizar.

Las entregas se pueden crear desde la lista de entregas o dentro de un flujo de trabajo mediante una actividad de [entrega](../../automation/workflow/delivery.md).

Los flujos de trabajo también proporcionan actividades de entrega específicas según el tipo de canal que desee utilizar. Para obtener más información sobre estas actividades, consulte [esta sección](../../automation/workflow/cross-channel-deliveries.md).

### Entrega recurrente {#recurring-delivery}

A **envío recurrente** está disponible en el contexto de un flujo de trabajo. Permite crear una nueva entrega cada vez que se ejecuta la actividad. Esto evita tener que crear una nueva entrega para las tareas recurrentes. Por ejemplo, si ejecuta este tipo de actividad una vez al mes, tras un año acaba teniendo 12 envíos.

Las entregas recurrentes se crean en los flujos de trabajo a través de la actividad de [entrega recurrente](../../automation/workflow/recurring-delivery.md). En esta sección se muestra un ejemplo de esta actividad: [Creación de una entrega recurrente en un flujo de trabajo de objetivos](../../automation/workflow/send-a-birthday-email.md).

### Entrega continua {#continuous-delivery}

A **envío continuo** está disponible en el contexto de un flujo de trabajo. Permite añadir nuevos destinatarios a una entrega existente, lo que evita tener que crear una nueva entrega cada vez que se ejecuta.

Si cambia la información de la entrega (contenido, nombre, etc.), se crea un nuevo objeto de envío en la ejecución de la entrega. Si no se ha cambiado ninguna información, se vuelve a utilizar el mismo objeto de envío y los “logs” de entrega y seguimiento se añaden en el mismo objeto.

Por ejemplo, si ejecuta este tipo de actividad una vez al mes, acaba teniendo un solo envío después de un año (siempre y cuando no haya realizado ningún cambio en la entrega).

Las entregas continuas se crean dentro de flujos de trabajo a través de la [Actividad de entrega continua](../../automation/workflow/continuous-delivery.md).


## Elija cómo enviar los mensajes{#gs-send-msg}

Una vez creado el mensaje y diseñado y probado su contenido, puede elegir cómo desea enviarlo. Campaign ofrece un conjunto de funcionalidades para lo siguiente:

* Enviar mensajes manualmente al destinatario principal

  ![](assets/send-email.png)

  Obtenga información sobre cómo enviar mensajes en [esta sección](../send/send.md)

* Enviar mensajes asociados a una [campaña de marketing](campaigns.md)

  ![](assets/deliveries-in-a-campaign.png)

  Obtenga información sobre cómo enviar mensajes en el contexto de una campaña en [esta sección](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=es){target="_blank"}

* Enviar mensajes a través de un [flujo de trabajo](../config/workflows.md)

  ![](assets/send-in-a-wf.png)

  Obtenga información sobre cómo automatizar los envíos de correo electrónico en [esta página](../../automation/workflow/delivery.md)

* [Mensajes de activación ](../send/transactional.md) de un evento

  La mensajería transaccional (Centro de mensajes) es el módulo de Campaign diseñado para gestionar mensajes de activación.

  Obtenga más información acerca de la capacidad de los mensajes transaccionales en [esta sección](../architecture/architecture.md#transac-msg-archi)

  Los pasos para configurar y enviar mensajes transaccionales se detallan en [esta página](../send/transactional.md)

* Programación de mensajes

  ![](assets/schedule-send.png)

  Obtenga información sobre cómo programar la entrega de envíos en [esta página](../send/configure-and-send.md)

  Consulte también esto [Caso de uso: obtenga información sobre cómo programar y enviar un correo electrónico de cumpleaños](../../automation/workflow/send-a-birthday-email.md)


## Adición de personalización{#personalization}

Los mensajes enviados por Adobe Campaign se pueden personalizar de varias formas. [Obtenga más información acerca las funcionalidades de personalización](../send/personalize.md)

Puede hacer lo siguiente:

* Insertar campos de personalización dinámicos. [Más información](../send/personalization-fields.md)
* Inserte bloques de personalización predefinidos. [Más información](../send/personalization-blocks.md)
* Cree contenido condicional. [Más información](../send/conditions.md)


## Registros de seguimiento y envío{#gs-tracking-logs}

La monitorización de los envíos una vez enviados es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Puede monitorizarlas después de enviar un envío, así como comprender cómo se administran los errores y las cuarentenas.

Aprenda a monitorizar los envíos en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es#sending-messages){target="_blank"}

