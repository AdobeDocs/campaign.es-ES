---
title: Administración de cuarentena en Campaign
description: Explicación de la administración de cuarentena en Adobe Campaign
feature: Profiles, Monitoring
role: User, Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: e45799f0f3849d53d2c5f593bc02954b3a55fc28
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 35%

---

# Cuarentena {#quarantine-management}

Adobe Campaign administra una lista de direcciones en cuarentena para canales en línea (correo electrónico, SMS, notificación push). Algunos proveedores de acceso a Internet consideran automáticamente los correos electrónicos como correo no deseado si la tasa de direcciones no válidas es demasiado alta. Por lo tanto, la cuarentena le permite evitar ser agregado a la lista de bloqueados de la por estos proveedores. Además, la cuarentena reduce el coste de entrega de los SMS mediante la exclusión en las entregas de los números de teléfono incorrectos.

Cuando su dirección o número de teléfono están en cuarentena, los destinatarios se excluyen del objetivo durante el análisis de la entrega: no podrá enviar mensajes de marketing, incluidos correos electrónicos de flujo de trabajo automatizado, a esos contactos. Si esas direcciones en cuarentena también están presentes en las listas, se excluirán al enviarlas a esas listas. Una dirección de correo electrónico se puede poner en cuarentena, por ejemplo, cuando el buzón está lleno, si la dirección no existe o si el servidor de correo electrónico no está disponible.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**Cuarentena** solo se aplica a un **dirección**, a **número de teléfono**, o a **token de dispositivo**, pero no al propio perfil. Del mismo modo, un perfil cuya dirección de correo electrónico se haya puesto en cuarentena puede actualizar su perfil e introducir una nueva, y luego puede volver a recibir entregas. Del mismo modo, si dos perfiles tienen el mismo número de teléfono, ambos se verán afectados si el número está en cuarentena. Las direcciones en cuarentena o los números de teléfono se muestran en los [registros de exclusión](#delivery-quarantines) (para una entrega) o en la [lista de cuarentena](#non-deliverable-bounces) (para toda la plataforma).

Por otro lado, los perfiles pueden estar en la **lista de bloqueados de** como después de una baja (exclusión), para un canal determinado: esto implica que ya no están en el objetivo de ningún canal. Como consecuencia, si un perfil de la lista de bloqueados de la para el canal de correo electrónico tiene dos direcciones de correo electrónico, ambas se excluirán de la entrega. Puede comprobar si un perfil está en la lista de bloqueados de uno o más canales en la sección **[!UICONTROL No longer contact]** de la pestaña **[!UICONTROL General]** del perfil. [Más información](../audiences/view-profiles.md)

>[!NOTE]
>
>Cuando los destinatarios informan el mensaje como correo no deseado o responden a un mensaje SMS con una palabra clave como &quot;DETENER&quot;, su dirección o número de teléfono se pone en cuarentena como **[!UICONTROL Denylisted]**. Su perfil se actualiza en consecuencia.

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## ¿Por qué se envía un correo electrónico, un teléfono o un dispositivo a cuarentena? {#quarantine-reason}

Adobe Campaign administra la cuarentena según el tipo de error de entrega y su motivo. Se asignan durante la calificación de mensajes de error. Más información sobre la administración de errores de entrega [en esta página](delivery-failures.md).

Se pueden capturar dos tipos de errores:

* **Error grave**: la dirección de correo electrónico, el número de teléfono o el dispositivo se envían inmediatamente a cuarentena.
* **Error leve**: los errores leves incrementan un contador de errores y podrían poner en cuarentena un correo electrónico, un número de teléfono o un token de dispositivo. Rendimiento de campaña [reintentos](delivery-failures.md#retries): cuando el contador de errores alcanza el umbral de límite, la dirección, el número de teléfono o el token del dispositivo se ponen en cuarentena. [Más información](delivery-failures.md#retries).

En la lista de direcciones en cuarentena, el campo **[!UICONTROL Error reason]** indica por qué la dirección seleccionada se envía a cuarentena. [Más información](#identifying-quarantined-addresses-for-the-entire-platform).


Si un usuario clasifica un correo electrónico como correo no deseado, el mensaje se redirige automáticamente a un buzón de correo técnico administrado por el Adobe. A continuación, la dirección de correo electrónico del usuario se envía automáticamente a la cuarentena con el estado **[!UICONTROL Denylisted]**. Este estado hace referencia únicamente a la dirección y el perfil no está en la lista de bloqueados de la para que el usuario siga recibiendo mensajes SMS y notificaciones push. Obtenga más información sobre los bucles de comentarios en la [Guía de prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#feedback-loops){target="_blank"}.

>[!NOTE]
>
>La cuarentena en Adobe Campaign distingue entre mayúsculas y minúsculas. Asegúrese de importar las direcciones de correo electrónico en minúsculas para que no se redireccionen más adelante.

## Acceso a direcciones en cuarentena {#access-quarantined-addresses}

Las direcciones en cuarentena se pueden mostrar para una entrega específica o para toda la plataforma.

### Cuarentenas para una entrega{#delivery-quarantines}

Las direcciones en cuarentena se enumeran durante la fase de preparación de la entrega, en los registros de envío del panel de envío.

Para cada entrega, también puede comprobar las **[!UICONTROL Delivery summary]** report: muestra el número de direcciones en cuarentena en el destino de la entrega y muestra:

* El número de direcciones puestas en cuarentena durante el análisis de la entrega.
* El número de direcciones puestas en cuarentena después de la acción de entrega.

### Direcciones de devolución y envío no permitidas{#non-deliverable-bounces}

Para ver la lista de direcciones en cuarentena **para toda la plataforma**, los administradores de Campaign pueden navegar a  **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. Esta sección enumera los elementos en cuarentena para **email**, **SMS** y **Notificación push** canales.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>El número de cuarentenas aumenta con el tiempo. Por ejemplo, si se considera que la duración de una dirección de correo electrónico es de tres años y la lista de distribución aumenta en un 50 % cada año, el aumento de la cuarentena se puede calcular de la siguiente manera:
>
>Fin de año 1: (1&#42;0,33)/(1+0,5) = 22 %.
>
Fin de año 2: ((1,22&#42;0,33)+0,33)/(1,5+0,75) = 32,5 %.

Además, la variable **[!UICONTROL Non-deliverables and bounces]** informe integrado, disponible en el **Informes** de esta página de inicio, muestra información sobre las direcciones en cuarentena, los tipos de error encontrados y un desglose de errores por dominio. Puede filtrar los datos de una entrega específica o personalizar este informe según sea necesario.

Obtenga más información acerca de las direcciones de rechazo en la [Guía de prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target="_blank"}.

### Dirección de correo en cuarentena {#quarantined-recipient}

Se puede buscar el estado del correo electrónico de cualquier destinatario.

Para ello, seleccione el perfil de destinatario y haga clic en la pestaña **[!UICONTROL Deliveries]**. Para todas las entregas a ese destinatario, se puede averiguar si la dirección falló, si se puso en cuarentena durante el análisis, etc.

Para cada carpeta, puede mostrar solo los destinatarios cuya dirección de correo electrónico esté en cuarentena, con la variable **[!UICONTROL Quarantined email address]** filtro integrado, como se muestra a continuación:

![](assets/quarantine-filter.png)


## Eliminación de una dirección en cuarentena {#remove-a-quarantined-address}

Las direcciones que coinciden con condiciones específicas se eliminan automáticamente de la lista de cuarentena mediante el **Database cleanup** flujo de trabajo integrado.

Las direcciones se eliminan automáticamente de la lista de cuarentena en los siguientes casos:

* Las direcciones de un estado **[!UICONTROL With errors]** se eliminarán de la lista de cuarentena tras un envío correcto.
* Las direcciones de un estado **[!UICONTROL With errors]** se eliminarán de la lista de cuarentena si el último rebote suave se produjo hace más de 10 días. Para obtener más información sobre la administración de errores leves, consulte [esta sección](#soft-error-management).
* Las direcciones con un estado **[!UICONTROL With errors]** que rebotó con el error **[!UICONTROL Mailbox full]** se eliminarán de la lista de cuarentena pasados 30 días.

A continuación, su estado cambia a **[!UICONTROL Valid]**.

>[!CAUTION]
>
Los destinatarios con una dirección en un estado **[!UICONTROL Quarantine]** o **[!UICONTROL Denylisted]** nunca se eliminarán, aunque reciban un correo electrónico.

También puede eliminar manualmente una dirección de la lista de cuarentena. Para eliminar una dirección de la cuarentena, puede:

* Cambie su estado a **[!UICONTROL Valid]** desde el **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** nodo.

  ![](assets/tech-quarantine-status.png)

Es posible que deba realizar actualizaciones masivas en la lista de cuarentena, por ejemplo, en caso de una interrupción del ISP durante la cual los correos electrónicos se marcan erróneamente como rechazos porque no se pueden enviar correctamente a su destinatario.

Para ello, cree un flujo de trabajo y añada una consulta en la tabla de cuarentena para filtrar todos los destinatarios afectados y así poder eliminarlos de la lista de cuarentena e incluirlos en futuros envíos de correo electrónico de Campaign.

A continuación se muestran las directrices recomendadas para esta consulta:

* **El texto del error (texto de cuarentena)** contiene “Momen_Code10_InvalidRecipient”
* **Dominio de correo electrónico (@domain)** igual a domain1.com O **Dominio de correo electrónico (@domain)** igual a domain2.com O **Dominio de correo electrónico (@domain)** igual a domain3.com
* **Estado de la actualización (@lastModified)** el `MM/DD/YYYY HH:MM:SS AM` o después
* **Estado de la actualización (@lastModified)** el `MM/DD/YYYY HH:MM:SS PM` o antes

Una vez que tenga la lista de destinatarios afectados, añada una **[!UICONTROL Update data]** actividad para establecer su estado en **[!UICONTROL Valid]** por lo tanto, serán eliminados de la lista de cuarentena por el **[!UICONTROL Database cleanup]** flujo de trabajo. También puede eliminarlos de la tabla de cuarentena.

