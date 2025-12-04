---
title: Administración de cuarentena en Campaign
description: Explicación de la administración de cuarentena en Adobe Campaign
feature: Profiles, Monitoring
role: User, Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 29%

---

# Cuarentena {#quarantine-management}

Adobe Campaign administra una lista de direcciones en cuarentena para canales en línea (correo electrónico, SMS, notificación push). Algunos proveedores de acceso a Internet consideran automáticamente los correos electrónicos como correo no deseado si la tasa de direcciones no válidas es demasiado alta. Por lo tanto, la cuarentena le permite evitar ser agregado a la lista de bloqueados de la por estos proveedores. Además, la cuarentena reduce el coste de envío de los SMS mediante la exclusión en los envíos de los números de teléfono incorrectos.

Cuando su dirección o número de teléfono están en cuarentena, los destinatarios se excluyen del objetivo durante el análisis de la entrega: no podrá enviar mensajes de marketing, incluidos correos electrónicos de flujo de trabajo automatizado, a esos contactos. Si esas direcciones en cuarentena también están presentes en las listas, se excluirán al enviarlas a esas listas. Una dirección de correo electrónico se puede poner en cuarentena, por ejemplo, cuando el buzón está lleno, si la dirección no existe o si el servidor de correo electrónico no está disponible.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

## Cuarentena frente a lista de bloqueados de

**La cuarentena** solo se aplica a una **dirección**, un **número de teléfono** o un **token de dispositivo**, pero no al propio perfil. Del mismo modo, un perfil cuya dirección de correo electrónico se haya puesto en cuarentena puede actualizar su perfil e introducir una nueva, y luego puede volver a recibir entregas. Del mismo modo, si dos perfiles tienen el mismo número de teléfono, ambos se verán afectados si el número está en cuarentena. Las direcciones en cuarentena o los números de teléfono se muestran en los [registros de exclusión](#delivery-quarantines) (para una entrega) o en la [lista de cuarentena](#non-deliverable-bounces) (para toda la plataforma).

>[!NOTE]
>
>Cuando los destinatarios informan el mensaje como correo no deseado o responden a un mensaje SMS con una palabra clave como &quot;DETENER&quot;, su dirección o número de teléfono se pone en cuarentena como **[!UICONTROL Denylisted]**. Su perfil se actualiza en consecuencia.

Por otro lado, **perfiles** pueden estar en la **lista de bloqueados de** como después de una baja (exclusión), para un canal determinado: esto implica que ya no están en el objetivo de ningún envío. Como consecuencia, si un perfil de la lista de bloqueados de la para el canal de correo electrónico tiene dos direcciones de correo electrónico, ambas se excluirán de la entrega. Puede comprobar si un perfil está en la lista de bloqueados de uno o más canales en la sección **[!UICONTROL No longer contact]** de la pestaña **[!UICONTROL General]** del perfil. [Más información](../audiences/view-profiles.md)

>[!NOTE]
>
>Los destinatarios que cancelaron la suscripción a través del método List-Unsubscribe [&quot;mailto&quot;](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations#mailto-list-unsubscribe){target="_blank"} no se envían a la cuarentena. Se da de baja su suscripción al [servicio](../start/subscriptions.md) asociado con la entrega, o se envía a la lista de bloqueados de la (visible en la sección **[!UICONTROL No longer contact]** del perfil) si no se ha definido ningún servicio para la entrega.

<!--For the mobile app channel, device tokens are quarantined.-->

## ¿Por qué se envía un correo electrónico, un teléfono o un dispositivo a cuarentena? {#quarantine-reason}

Adobe Campaign administra la cuarentena según el tipo de error de entrega y su motivo. Se asignan durante la calificación de mensajes de error. Obtenga más información acerca de la administración de errores de entrega [en esta página](delivery-failures.md).

Se pueden capturar dos tipos de errores:

* **Error grave**: la dirección de correo electrónico, el número de teléfono o el dispositivo se envían inmediatamente a cuarentena.
* **Error leve**: los errores leves incrementan un contador de errores y podrían poner en cuarentena un correo electrónico, un número de teléfono o un token de dispositivo. Campaign realiza [reintentos](delivery-failures.md#retries): cuando el contador de errores alcanza el umbral de límite, la dirección, el número de teléfono o el token del dispositivo se ponen en cuarentena. [Más información](delivery-failures.md#retries).

En la lista de direcciones en cuarentena, el campo **[!UICONTROL Error reason]** indica por qué la dirección seleccionada se envía a cuarentena. [Más información](#non-deliverable-bounces).


Si un usuario clasifica un correo electrónico como correo no deseado, el mensaje se redirige automáticamente a un buzón de correo técnico administrado por Adobe. A continuación, la dirección de correo electrónico del usuario se envía automáticamente a la cuarentena con el estado **[!UICONTROL Denylisted]**. Este estado hace referencia únicamente a la dirección y el perfil no está en la lista de bloqueados de la para que el usuario siga recibiendo mensajes SMS y notificaciones push. Obtenga más información acerca de los bucles de comentarios en la [Guía de prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#feedback-loops){target="_blank"}.

>[!NOTE]
>
>La cuarentena en Adobe Campaign distingue entre mayúsculas y minúsculas. Asegúrese de importar las direcciones de correo electrónico en minúsculas para que no se redireccionen más adelante.

## Administración de errores en software {#soft-error-management}

A diferencia de los errores en hardware, los errores en software no envían una dirección a la cuarentena inmediatamente, sino que se suman a un contador de errores. Cuando el contador de errores alcanza el umbral de límite, la dirección se pone en cuarentena. Obtenga más información sobre reintentos y tipos de error en [Explicación de los errores de entrega](delivery-failures.md).

El contador de errores se reinicia si el último error significativo se produjo hace más de 10 días. El estado de la dirección cambia a **[!UICONTROL Valid]** y el flujo de trabajo **[!UICONTROL Database cleanup]** la elimina de la lista de cuarentena. [Más información sobre flujos de trabajo técnicos](../config/workflows.md#technical-workflows).

## Acceso a direcciones en cuarentena {#access-quarantined-addresses}

Las direcciones en cuarentena se pueden mostrar para una entrega específica o para toda la plataforma.

### Cuarentenas para una entrega{#delivery-quarantines}

Las direcciones en cuarentena se enumeran durante la fase de preparación de la entrega, en los registros de envío del panel de envío.

Para cada entrega, también puede comprobar el informe **[!UICONTROL Delivery summary]**: muestra el número de direcciones en cuarentena en el destino de la entrega y muestra:

* El número de direcciones puestas en cuarentena durante el análisis de la entrega.
* El número de direcciones puestas en cuarentena después de la acción de entrega.

Obtenga más información sobre los informes de envíos en [esta sección](../reporting/gs-reporting.md).

### Direcciones de devolución y envío no permitidas{#non-deliverable-bounces}

Para ver la lista de direcciones en cuarentena **para toda la plataforma**, los administradores de Campaign pueden examinar **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. Esta sección lista los elementos en cuarentena para los canales **email**, **SMS** y **Notificación push**.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>El número de cuarentenas aumenta con el tiempo. Por ejemplo, si se considera que la duración de una dirección de correo electrónico es de tres años y la lista de distribución aumenta en un 50 % cada año, el aumento de la cuarentena se puede calcular de la siguiente manera:
>
>Fin de año 1: (1&#42;0,33)/(1+0,5) = 22 %.
>
>Fin de año 2: ((1,22&#42;0,33)+0,33)/(1,5+0,75) = 32,5 %.

Además, el informe integrado **[!UICONTROL Non-deliverables and bounces]**, disponible en la sección **Informes** de esta página de inicio, muestra información sobre las direcciones en cuarentena, los tipos de error encontrados y un desglose de errores por dominio. Puede filtrar los datos de una entrega específica o personalizar este informe según sea necesario.

Obtenga más información acerca de las direcciones de rechazo en la [Guía de prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target="_blank"}.

### Dirección de correo en cuarentena {#quarantined-recipient}

Se puede buscar el estado del correo electrónico de cualquier destinatario.

Para ello, seleccione el perfil de destinatario y haga clic en la pestaña **[!UICONTROL Deliveries]**. Para todas las entregas a ese destinatario, se puede averiguar si la dirección falló, si se puso en cuarentena durante el análisis, etc.

Para cada carpeta, puede mostrar solo los destinatarios cuya dirección de correo electrónico esté en cuarentena, con el filtro integrado **[!UICONTROL Quarantined email address]**, como se muestra a continuación:

![](assets/quarantine-filter.png)


## Eliminación de una dirección en cuarentena {#remove-a-quarantined-address}

### Actualizaciones automáticas {#unquarantine-auto}

El flujo de trabajo integrado de **[!UICONTROL Database cleanup]** elimina automáticamente de la lista de cuarentena las direcciones que cumplan condiciones específicas.

Las direcciones se eliminan automáticamente de la lista de cuarentena en los siguientes casos:

* Las direcciones de un estado **[!UICONTROL With errors]** se eliminarán de la lista de cuarentena tras un envío correcto.
* Las direcciones de un estado **[!UICONTROL With errors]** se eliminarán de la lista de cuarentena si el último rebote suave se produjo hace más de 10 días. Para obtener más información sobre la administración de errores leves, consulte [esta sección](#soft-error-management).
* Las direcciones con un estado **[!UICONTROL With errors]** que rebotó con el error **[!UICONTROL Mailbox full]** se eliminarán de la lista de cuarentena pasados 30 días.

A continuación, su estado cambia a **[!UICONTROL Valid]**.

>[!CAUTION]
>
>Los destinatarios con una dirección en un estado **[!UICONTROL Quarantine]** o **[!UICONTROL Denylisted]** nunca se eliminarán, aunque reciban un correo electrónico.

### Actualizaciones manuales {#unquarantine-manual}

También puede eliminar manualmente una dirección de la lista de cuarentena. Para quitar manualmente una dirección de la cuarentena, puede cambiar su estado a **[!UICONTROL Valid]** desde el nodo **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**.

![](assets/tech-quarantine-status.png)

### Actualizaciones masivas {#unquarantine-bulk}

Es posible que deba realizar actualizaciones masivas en la lista de cuarentena en situaciones específicas, como una interrupción del ISP durante la cual los correos electrónicos se marcan erróneamente como rechazos porque no se pueden enviar correctamente a su destinatario.

Para realizar una actualización masiva:

1. Cree un flujo de trabajo y agregue una consulta a la tabla de cuarentena (**[!UICONTROL nms:address]**) para filtrar los destinatarios afectados
2. Utilice condiciones de consulta para identificar las direcciones que se deben dejar de poner en cuarentena, como:
   * **Dominio de correo electrónico (@domain)** es igual a los dominios de ISP afectados
   * **Actualizar estado (@lastModified)** dentro del intervalo de tiempo de la interrupción
   * **Estado (@status)** es igual al estado de cuarentena
3. Agregue una actividad **[!UICONTROL Update data]** para establecer el estado de la dirección en **[!UICONTROL Valid]**

El flujo de trabajo **[!UICONTROL Database cleanup]** quitará automáticamente las direcciones de la lista de cuarentena y se podrán incluir en futuros envíos.

## Temas relacionados

* [Comprensión de los errores de entrega](delivery-failures.md): obtenga información sobre los diferentes tipos de errores de entrega y cómo gestiona Campaign los rechazos
* [Supervisar envíos](delivery-dashboard.md): acceda a los registros de envío y supervise el rendimiento de envío
* [Prácticas recomendadas de entrega](../start/delivery-best-practices.md): prácticas recomendadas para mantener la buena capacidad de entrega y evitar cuarentenas

