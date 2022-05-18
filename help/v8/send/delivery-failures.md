---
title: Fallos de entrega en Campaign
description: Comprender los posibles errores al enviar mensajes con Adobe Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 9c83ebeb-e923-4d09-9d95-0e86e0b80dcc
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '2849'
ht-degree: 68%

---

# Comprensión de los errores de entrega {#delivery-failures}

Las devoluciones son el resultado de un intento de envío y un error en el que el ISP proporciona avisos de error de devolución. El procesamiento de la manipulación de devoluciones es una parte fundamental de la higiene de la lista. Una vez que un correo electrónico determinado ha rebotado varias veces seguidas, este proceso lo marca para su supresión.

Este proceso evita que los sistemas continúen enviando direcciones de correo electrónico no válidas. Las devoluciones son uno de los datos clave que los ISP utilizan para determinar la reputación de la IP. Es importante vigilar esta métrica. &quot;Entregado&quot; frente a &quot;rechazado&quot; es probablemente la forma más común de medir el envío de mensajes de marketing: cuanto mayor sea el porcentaje entregado, mejor.

Si no se puede enviar un mensaje a un perfil, el servidor remoto envía automáticamente un mensaje de error a Adobe Campaign. Este error se clasifica para determinar si la dirección de correo electrónico, el número de teléfono o el dispositivo deben ponerse en cuarentena. Consulte [Administración de correos rechazados](#bounce-mail-qualification).

Una vez enviado un mensaje, puede ver el estado de entrega de cada perfil y el tipo y motivo de error asociado en los registros de envío.

Cuando una dirección de correo electrónico se pone en cuarentena, o si un perfil está en , el destinatario se excluye en el paso de preparación de la entrega. Los mensajes excluidos se muestran en el panel de entrega.

## ¿Por qué ha fallado la entrega del mensaje? {#delivery-failure-reasons}

Existen dos tipos de error cuando falla un mensaje. Cada tipo de error de entrega determina si se envía una dirección a [cuarentena](quarantines.md#quarantine-reason) o no.

* **Rechazos graves**
Las devoluciones duras son errores permanentes generados después de que un ISP determine que un intento de envío a una dirección de suscriptor no se puede entregar. En Adobe Campaign, los rechazos graves clasificados como no entregables se añaden a la lista de cuarentena, lo que significa que no se volverían a probar. Hay algunos casos en los que se ignoraría un rechazo grave si se desconoce la causa del error.

   Estos son algunos ejemplos comunes de rechazos graves: La dirección no existe, Cuenta deshabilitada, Sintaxis incorrecta, Dominio incorrecto

* **Rechazos leves**
Las devoluciones leves son errores temporales que los ISP generan cuando tienen dificultades para enviar correos. Los errores leves [reintento](#retries) varias veces (con variación dependiendo del uso de la configuración de envío personalizada o predeterminada) para intentar una entrega correcta. Las direcciones que reboten de forma continua y suave no se añadirán a la cuarentena hasta que se haya intentado el número máximo de reintentos (que de nuevo varía en función de la configuración).

   Algunas causas comunes de devoluciones leves son las siguientes: Buzón lleno, Recibiendo servidor de correo electrónico inactivo, problemas de reputación del remitente

La variable  **Ignorado** Se sabe que el tipo de error es temporal, como &quot;Fuera de la oficina&quot;, o un error técnico, por ejemplo, si el tipo de remitente es &quot;Administrador de correo&quot;.

El bucle de comentarios funciona como los correos electrónicos rechazados: cuando un usuario clasifica un correo electrónico como correo no deseado, puede configurar las reglas de correo electrónico en Adobe Campaign para bloquear todas las entregas a este usuario. Las direcciones de estos usuarios se incluida en la lista de bloqueados aunque no hayan hecho clic en el vínculo de baja. Las direcciones se añaden al (**NmsAddress**) y no a la tabla de cuarentena (**NmsRecipient**) tabla de destinatarios con la variable **[!UICONTROL Denylisted]** estado. Obtenga más información sobre el mecanismo de bucle de comentarios en la sección [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#feedback-loops).

## Errores sincrónicos y asíncronos {#synchronous-and-asynchronous-errors}

Un envío de mensajes puede fallar inmediatamente, en ese caso se clasifica como un error sincrónico. Si el envío de mensajes falla o más adelante, después de enviarlo, el error es asincrónico.

Estos tipos de errores se administran de la siguiente manera:

* **Error sincrónico**: el servidor remoto contactado por el servidor de entrega de Adobe Campaign devuelve inmediatamente un mensaje de error. No se permite que la entrega se envíe al servidor del perfil. El MTA mejorado determina el tipo de rechazo y clasifica el error, y envía esa información a Campaign para determinar si las direcciones de correo electrónico correspondientes deben ponerse en cuarentena. Consulte [Cualificación de correo rechazado](#bounce-mail-qualification).

* **Error asíncrono**: el servidor receptor reenvía más tarde un correo electrónico devuelto o una SR. Este error se clasifica con una etiqueta relacionada con el error. Pueden producirse errores asíncronos hasta una semana después de mandar la entrega.

>[!NOTE]
>
>Como usuario de Managed Services, la configuración del buzón de rechazos la realiza el Adobe.

## Clasificación del correo rechazado {#bounce-mail-qualification}

<!--NO LONGER WITH MOMENTUM - Rules used by Campaign to qualify delivery failures are listed in the **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** node. It is non-exhaustive, and is regularly updated by Adobe Campaign and can also be managed by the user.

![](assets/delivery-log-qualification.png)-->

Actualmente, la forma en que se gestiona la calificación de correo rechazado en Adobe Campaign depende del tipo de error:

* **Errores sincrónicos**: El MTA mejorado determina el tipo de rechazo y la calificación, y envía esa información a Campaign. Las cualificaciones de devolución en la variable **[!UICONTROL Delivery log qualification]** no se usa para **sincrónica** mensajes de error de error de envío.

* **Errores asincrónicos**: Las reglas que utiliza Campaign para clasificar los errores de entrega asincrónicos se enumeran en la **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** nodo . Las devoluciones asincrónicas se clasifican mediante el proceso inMail a través del **[!UICONTROL Inbound email]** reglas. Para obtener más información, consulte [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}.

<!--NO LONGER WITH MOMENTUM - The message returned by the remote server on the first occurrence of this error type is displayed in the **[!UICONTROL First text]** column of the **[!UICONTROL Audit]** tab.

![](assets/delivery-log-first-txt.png)

Adobe Campaign filters this message to delete the variable content (such as IDs, dates, email addresses, phone numbers, etc.) and displays the filtered result in the **[!UICONTROL Text]** column. The variables are replaced with **`#xxx#`**, except addresses that are replaced with **`*`**.

This process allows to bring together all failures of the same type and avoid multiple entries for similar errors in the Delivery log qualification table.
  
>[!NOTE]
>
>The **[!UICONTROL Number of occurrences]** field displays the number of occurrences of the message in the list. It is limited to 100 000 occurrences. You can edit the field, if you want, for example, to reset it.

Bounce mails can have the following qualification status:

* **[!UICONTROL To qualify]** : the bounce mail could not be qualified. Qualification must be assigned to the Deliverability team to guarantee efficient platform deliverability. As long as it is not qualified, the bounce mail is not used to enrich the list of email management rules.
* **[!UICONTROL Keep]** : the bounce mail was qualified and will be used by the **Refresh for deliverability** workflow to be compared to existing email management rules and enrich the list.
* **[!UICONTROL Ignore]** : the bounce mail is ignored, meaning that this bounce will never cause the recipient's address to be quarantined. It will not be used by the **Refresh for deliverability** workflow and it will not be sent to client instances.

![](assets/delivery-log-status.png)

>[!NOTE]
>
>In case of an outage of an ISP, emails sent through Campaign will be wrongly marked as bounces. To correct this, you need to update bounce qualification.-->


## Gestión de reintentos {#retries}

Si la entrega de mensajes falla tras un error temporal (**Leve** o **Ignorado**), Campaign reintenta enviar. Estos reintentos se pueden realizar hasta el final de la duración de la entrega.

El MTA mejorado configura el número y la frecuencia de los reintentos en función del tipo y la gravedad de las respuestas de rechazo que regresan del ISP del mensaje.

<!--NO LONGER WITH MOMENTUM - The default configuration defines five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally or for each delivery or delivery template. If you need to adapt delivery duration and retries, contact Adobe Support.-->

## Tipos de error de correo electrónico {#email-error-types}

Para el canal de correo electrónico, a continuación se enumeran los posibles motivos de un error en la entrega.

<table> 
 <tbody> 
  <tr> 
   <td> Etiqueta de error </td> 
   <td> Tipo de error </td> 
   <td> Valor técnico </td> 
   <td> Descripción </td> 
  </tr> 
  <tr> 
   <td> Cuenta deshabilitada </td> 
   <td> Leve/Grave </td> 
   <td> 4 </td> 
   <td> La cuenta vinculada a la dirección no está activa. Cuando el proveedor de acceso a Internet (IAP) detecta un periodo de inactividad prolongado, puede cerrar la cuenta del usuario. A partir de ese momento no se pueden realizar entregas a la cuenta de usuario. Si la cuenta está temporalmente desactivada debido a seis meses de inactividad y todavía se puede activar, se asigna el estado “con errores” y se prueba de nuevo la cuenta hasta que el contador de errores alcance 5. Si el error indica que la cuenta está desactivada de forma permanente, se envía directamente a Cuarentena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dirección en cuarentena </td> 
   <td> Grave </td> 
   <td> 9 </td> 
   <td> La dirección se envió a cuarentena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dirección no especificada </td> 
   <td> Grave </td> 
   <td> 7 </td> 
   <td> No se proporciona ninguna dirección para el destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dirección de baja calidad </td> 
   <td> Ignorado </td> 
   <td> 14 </td> 
   <td> El índice de calidad de esta dirección es demasiado bajo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dirección incluida en la lista de bloqueados </td> 
   <td> Grave </td> 
   <td> 8 </td> 
   <td> La dirección se agregó a la lista de bloqueados al momento del envío. Este estado se utiliza para importar datos de listas externas y sistemas externos a la lista de cuarentena de Adobe Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dirección de control </td> 
   <td> Ignorado </td> 
   <td> 127 </td> 
   <td> La dirección del destinatario forma parte del grupo de control.<br /> </td> 
  </tr> 
  <tr> 
   <td> Duplicada </td> 
   <td> Ignorado </td> 
   <td> 10 </td> 
   <td> La dirección del destinatario ya se encontraba en esta entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Error ignorado </td> 
   <td> Ignorado </td> 
   <td> 25 </td> 
   <td> La dirección está incluida en la lista de permitidos. Por lo tanto, el error se ignora y se envía un correo electrónico.<br /> </td> 
  </tr> 
  <tr> 
   <td> Excluido tras la mediación </td> 
   <td> Ignorado </td> 
   <td> 12 </td> 
   <td> El destinatario se ha excluido mediante las reglas de tipología de campaña de tipo “mediación”.<br /> </td> 
  </tr> 
  <tr> 
   <td> Excluido por una regla SQL </td> 
   <td> Ignorado </td> 
   <td> 11 </td> 
   <td> El destinatario se ha excluido mediante una regla de tipología de campaña de tipo “SQL”.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio inválido </td> 
   <td> Leve </td> 
   <td> 2 </td> 
   <td> El dominio de la dirección del correo electrónico es incorrecto o ya no existe. Este perfil se vuelve a seleccionar hasta que el recuento de errores llegue a 5. Después de esto, el registro se pone en estado de cuarentena y no se realiza ningún reintento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Buzón de correo lleno </td> 
   <td> Leve </td> 
   <td> 5 </td> 
   <td> El buzón de este usuario está lleno y no puede aceptar más mensajes. Este perfil se vuelve a seleccionar hasta que el recuento de errores llegue a 5. Después de esto, el registro se pone en estado de cuarentena y no se realiza ningún reintento.<br /> Este tipo de error se administra mediante un proceso de limpieza; la dirección se establece en un estado válido después de 30 días.<br /> Advertencia: para que la dirección se elimine automáticamente de la lista de direcciones en cuarentena, debe iniciarse el flujo de trabajo técnico Database cleanup .<br /> </td> 
  </tr> 
  <tr> 
   <td> Sin conexión </td> 
   <td> Ignorado </td> 
   <td> 6 </td> 
   <td> El teléfono móvil del destinatario está apagado o no está conectado a la red cuando al enviar el mensaje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sin definir </td> 
   <td> Sin definir </td> 
   <td> 0 </td> 
   <td> La dirección se encuentra sin clasificar debido a que aún no se ha sumado el error. Este tipo de error se produce cuando el servidor envía un nuevo mensaje de error: puede tratarse de un error aislado; sin embargo, si vuelve a producirse, el contador de errores aumenta, lo que advierte a los equipos técnicos. Entonces pueden realizar análisis de mensajes y clasificar este error a través del nodo <span class="uicontrol">Administration</span>, <span class="uicontrol">Campaign Management</span>, <span class="uicontrol">Non deliverables Management</span> en la estructura del árbol.<br /> </td> 
  </tr> 
  <tr> 
   <td> No reúne los requisitos para las ofertas </td> 
   <td> Ignorado </td> 
   <td> 16 </td> 
   <td> El destinatario no reunía los requisitos para las ofertas de la entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazado </td> 
   <td> Leve/Grave </td> 
   <td> 20 </td> 
   <td> La dirección se ha enviado a cuarentena debido a un comentario de seguridad que informa de correo no deseado. Según el error, se vuelve a intentar enviar un correo a la dirección hasta que el contador de errores alcance 5 o se envía directamente a cuarentena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatarios de tamaño limitado </td> 
   <td> Ignorado </td> 
   <td> 17 </td> 
   <td> Se ha alcanzado el tamaño máximo de entrega para el destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dirección no autorizada </td> 
   <td> Ignorado </td> 
   <td> 15 </td> 
   <td> La dirección postal no se ha clasificado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inaccesible </td> 
   <td> Leve/Grave </td> 
   <td> 3 </td> 
   <td> Se ha producido un error en la cadena de entrega de mensajes. Podría ser un incidente en la retransmisión SMTP, un dominio al que no se puede acceder temporalmente, etc. Según el error, se vuelve a intentar enviar un correo a la dirección hasta que el contador de errores llegue a 5 o se envía directamente a cuarentena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Usuario desconocido </td> 
   <td> Grave </td> 
   <td> 1 </td> 
   <td> La dirección no existe. No se intenta realizar entregas adicionales para este perfil.<br /> </td> 
  </tr> 
 </tbody> 
</table>



## Tipos de error de las notificaciones push {#push-error-types}

A continuación se enumeran los posibles motivos del error de entrega en el canal de la aplicación móvil.

### Cuarentena de iOS {#ios-quarantine}

El protocolo HTTP/V2 permite los comentarios y el estado directo para cada notificación remota. Si se utiliza el conector de protocolo HTTP/V2, el flujo de trabajo **[!UICONTROL mobileAppOptOutMgt]** ya no se comunica con el servicio de comentarios. Un token de dispositivo se considera no registrado cuando se desinstala o se vuelve a instalar una aplicación móvil.

Sincrónicamente, si APNS devuelve el estado “no registrado” para un mensaje, el token de destino se pone inmediatamente en cuarentena.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Situación</strong><br /> </td> 
   <td> <strong>Estado</strong><br /> </td> 
   <td> <strong>Mensaje de error</strong><br /> </td> 
   <td> <strong>Tipo de error</strong><br /> </td> 
   <td> <strong>Motivo del error</strong><br /> </td> 
   <td> <strong>Reintento</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo de destino encendido<br /> </td> 
   <td> OK<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo de destino apagado<br /> </td> 
   <td> OK<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> El usuario desactiva las notificaciones de la aplicación<br /> </td> 
   <td> OK<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Fase de creación/análisis de mensaje: carga útil demasiado grande<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> Carga útil demasiado grande<br /> </td> 
   <td> Leve<br /> </td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Fase de creación/análisis de mensaje: problema de formato inesperado del contenido<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> Varios mensajes de error según el error<br /> </td> 
   <td> Leve<br /> </td> 
   <td> Sin definir<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Problema de certificado (contraseña, corrupción, etc.) y conexión de prueba a un problema de APNS<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> Varios mensajes de error según el error<br /> </td> 
   <td> Leve<br /> </td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Se perdió la conexión de red durante la entrega<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> Error de conexión<br /> </td> 
   <td> Sin definir<br /> </td> 
   <td> Inaccesible<br /> </td> 
   <td> Sí<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo de mensaje APNS: cancelación del registro<br /> el usuario ha eliminado la aplicación o el token ha caducado<br />. </td> 
   <td> Fallo<br /> </td> 
   <td> No registrado<br /> </td> 
   <td> Grave<br /> </td> 
   <td> Usuario desconocido<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo de mensaje de APNS: todos los demás errores<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> La causa del rechazo del error está presente en el mensaje de error.<br /> </td> 
   <td> Leve<br /> </td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Cuarentena de Android {#android-quarantine}

**Para Android V1**

Para cada notificación, Adobe Campaign recibe los errores sincrónicos directamente desde el servidor FCM. Adobe Campaign los gestiona sobre la marcha y genera errores graves o leves según la gravedad del error y los reintentos que se puedan realizar:

* Longitud de la carga útil excedida, problema de conexión, problema de disponibilidad del servicio: con reintento, error leve, el motivo del error es **[!UICONTROL Refused]**.
* Se ha superado la cuota de dispositivo: sin reintento, error leve, el motivo del error es **[!UICONTROL Refused]**.
* Token inválido o no registrado, error inesperado, problema con la cuenta del remitente: sin reintento, error grave, el motivo del error es **[!UICONTROL Refused]**.

El flujo de trabajo **[!UICONTROL mobileAppOptOutMgt]** se ejecuta cada 6 horas para actualizar la tabla de **AppSubscriptionRcp**. En el caso de los tokens declarados no registrados o ya no válidos, el campo **Deshabilitado** se establece en **Verdadero** y la suscripción vinculada a ese token de dispositivo se excluye automáticamente de futuros entregas.

Durante el análisis de la entrega, todos los dispositivos excluidos del destino se añaden automáticamente a la tabla **excludeLogAppSubRcp**.

>[!NOTE]
>
>Para los clientes que utilicen el conector Baidu, los distintos tipos de errores son:
>
>* Problema de conexión al principio del envío: tipo de error **[!UICONTROL Undefined]**, motivo del error **[!UICONTROL Unreachable]**, con reintento.
>* Se ha perdido la conexión durante un envío: error de software, motivo del error **[!UICONTROL Refused]**, con reintento.
>* Error sincrónico devuelto por Baidu durante el envío: error de hardware, motivo del error **[!UICONTROL Refused]**, sin reintento.
>
>Adobe Campaign se pone en contacto con el servidor Baidu cada 10 minutos para recuperar el estado del mensaje enviado y actualiza los broadlogs. Si se declara un mensaje como enviado, el estado del mensaje en los broadlogs se establece en **[!UICONTROL Received]**. Si Baidu declara un error, el estado se establece en **[!UICONTROL Failed]**.

**Para Android V2**

El mecanismo de cuarentena de Android V2 utiliza el mismo proceso que Android V1; lo mismo se aplica a las suscripciones y a la actualización de las exclusiones. Para obtener más información, consulte la sección de [Android V1](#android-quarantine).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Situación</strong><br /> </td> 
   <td> <strong>Estado</strong><br /> </td> 
   <td> <strong>Mensaje de error</strong><br /> </td> 
   <td> <strong>Tipo de error</strong><br /> </td> 
   <td> <strong>Motivo del error</strong><br /> </td> 
   <td> <strong>Reintento</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Fase de creación/análisis de mensaje: palabras clave no válidas utilizadas en los campos personalizados<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> Las siguientes palabras clave no se pueden utilizar: {1}<br /> </td> 
   <td> Leve<br /> </td> 
   <td> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Fase de creación/análisis de mensaje: carga útil demasiado grande<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> La notificación es demasiado pesada: {1} bits, mientras que solo se autorizan {2}<br />. </td> 
   <td> Leve<br /> </td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Se perdió la conexión de red durante la entrega<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> No hay respuesta del servicio Firebase Cloud Messaging en la dirección: {1}<br /> </td> 
   <td> Leve<br /> </td> 
   <td> Inaccesible<br /> </td> 
   <td> Sí<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo de mensaje FCM: El servidor FCM no está disponible temporalmente (por ejemplo, con tiempos de espera). <br /> </td> 
   <td> Fallo<br /> </td> 
   <td> El servicio de Firebase Cloud Messaging no está disponible temporalmente<br /> </td> 
   <td> Leve<br /> </td> 
   <td> Inaccesible<br /> </td> 
   <td> Sí<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo de mensaje FCM: Error al autenticar la cuenta del remitente<br />. </td> 
   <td> Fallo<br /> </td> 
   <td> Error al identificar la cuenta de desarrollador, compruebe su ID y contraseña<br /> </td> 
   <td> Leve<br /> </td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo de mensaje FCM: Se excedió la cuota de dispositivo<br />. </td> 
   <td> Fallo<br /> </td> 
   <td> </td> 
   <td> Leve<br /> </td> 
   <td> Rechazado<br /> </td> 
   <td> Sí<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo de mensaje FCM: Registro no válido / no registrado<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> </td> 
   <td> Grave<br /> </td> 
   <td> Usuario desconocido<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo de mensaje FCM: Todos los demás errores<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> El servidor Firebase Cloud Messaging ha devuelto un código de error inesperado: {1} </td> 
   <td> </td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
    <tr> 
   <td> Rechazo de mensaje de FCM: argumento no válido<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> INVALID_ARGUMENT </td> 
   <td> Ignorado</td> 
   <td> Sin definir<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Rechazo de mensaje de FCM: error de autenticación de terceros<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> THIRD_PARTY_AUTH_ERROR </td> 
   <td> Ignorado</td>
   <td> Rechazado<br /> </td> 
   <td> Sí<br /> </td> 
  </tr>
    <tr> 
   <td> Rechazo de mensaje de FCM: el ID del remitente no coincide<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> SENDER_ID_MISMATCH </td> 
   <td> Leve</td>
   <td> Usuario desconocido<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Rechazo de mensaje de FCM: no registrado<br /> </td> 
   <td> Fallo<br /> </td>
   <td> NO REGISTRADO </td> 
   <td> Grave</td> 
   <td> Usuario desconocido<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Rechazo de mensaje de FCM: interno<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> INTERNAL </td> 
   <td> Ignorado</td> 
   <td> Rechazado<br /> </td> 
   <td> Sí<br /> </td> 
  </tr>
    <tr> 
   <td> Rechazo de mensaje de FCM: no está disponible<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> UNAVAILABLE</td> 
   <td> Ignorado</td> 
   <td> Rechazado<br /> </td> 
   <td> Sí<br /> </td> 
  </tr>
    <tr> 
   <td> Rechazo de mensaje de FCM: código de error inesperado<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> unexpected error code</td> 
   <td> Ignorado</td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr>
  <tr> 
   <td> Autenticación: problema de conexión<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> No es posible conectarse al servidor de autenticación </td> 
   <td> Ignorado</td>
   <td> Rechazado<br /> </td> 
   <td> Sí<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticación: cliente o ámbito no autorizado en la solicitud.<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> unauthorized_client </td> 
   <td> Ignorado</td>
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticación: el cliente no tiene autorización para recuperar los token de acceso mediante este método o no está autorizado para ninguno de los ámbitos solicitados.<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> authorized_client </td> 
   <td> Ignorado</td>
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticación: acceso denegado<br /> </td> 
   <td> Fallo<br /> </td>
   <td> access_denied</td> 
   <td> Ignorado</td>
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticación: correo electrónico no válido<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> invalid_grant </td> 
   <td> Ignorado</td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticación: JWT no válido<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> invalid_grant </td> 
   <td> Ignorado</td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticación: firma JWT no válida<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> invalid_grant </td> 
   <td> Ignorado</td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticación: audiencia de ámbito de OAuth o token de ID no válida proporcionada<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> authorized_client</td> 
   <td> Ignorado</td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Autenticación: cliente OAuth deshabilitado<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> disabled_client</td> 
   <td> Ignorado</td> 
   <td> Rechazado<br /> </td> 
   <td> No<br /> </td> 
  </tr>
 </tbody> 
</table>

## Cuarentenas de SMS {#sms-quarantines}

**Para conectores estándar**

Las particularidades del canal SMS se enumeran a continuación.

>[!NOTE]
>
>La tabla **[!UICONTROL Delivery log qualification]** no se aplica al conector **Extended generic SMPP**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Situación</strong><br /> </td> 
   <td> <strong>Estado</strong><br /> </td> 
   <td> <strong>Mensaje de error</strong><br /> </td> 
   <td> <strong>Tipo de error</strong><br /> </td> 
   <td> <strong>Motivo del error</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Enviado al proveedor<br /> </td> 
   <td> Enviado<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Recibido en el móvil<br /> </td> 
   <td> Recibido<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Error devuelto por el proveedor<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> Error al recibir datos (SR o MO)<br /> </td> 
   <td> Leve<br /> </td> 
   <td> Inaccesible<br /> </td> 
  </tr> 
  <tr> 
   <td> Reconocimiento de MT no válido<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> Error “{1}” durante el procesamiento del marco de reconocimiento de la consulta de entrega<br /> </td> 
   <td> Leve<br /> </td> 
   <td> Inaccesible<br /> </td> 
  </tr> 
  <tr> 
   <td> Error al enviar el MT<br /> </td> 
   <td> Fallo<br /> </td> 
   <td> Error al enviar mensajes<br /> </td> 
   <td> Leve<br /> </td> 
   <td> Inaccesible<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Para el conector SMPP genérico extendido**

Al utilizar el protocolo SMPP para enviar mensajes SMS, la administración de errores se gestiona de forma distinta.

El conector SMPP recupera los datos del mensaje de SR (informe de estado) que se devuelve utilizando expresiones regulares (regex) para filtrar su contenido. Estos datos se corresponden con la información que se encuentra en la tabla **[!UICONTROL Delivery log qualification]** (disponible a través del menú **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]**).

Antes de que se clasifique un nuevo tipo de error, el motivo del error se establece siempre como **Rechazado** de forma predeterminada.

>[!NOTE]
>
>Los tipos de errores y los motivos del error son los mismos que para los correos electrónicos.
>
>Solicite a su proveedor una lista de estados y códigos de error para establecer tipos y motivos de error adecuados para los errores en la tabla de clasificación de registros de entregas.

Ejemplo de mensaje generado:

```
SR Generic DELIVRD 000|#MESSAGE#
```

* Todos los mensajes de error empiezan por **SR** para distinguir entre los códigos de error de los SMS y códigos de error de los correos electrónicos.
* La segunda parte (**Generic** en este ejemplo) del mensaje de error hace referencia al nombre de la implementación de SMSC, como se define en el campo **[!UICONTROL SMSC implementation name]** de la cuenta externa de SMS.

   Dado que el mismo código de error puede tener un significado diferente para cada proveedor, este campo permite saber qué proveedor genera el código de error. Después se puede buscar el error en la documentación del proveedor correspondiente.

* La tercera parte (**DELIVRD** en este ejemplo) del mensaje de error corresponde al código de estado recuperado del SR mediante las regex de extracción de estado definidas en la cuenta externa de SMS.

   Esta regex se especifica en la pestaña **[!UICONTROL SMSC specificities]** de la cuenta externa.
De manera predeterminada, la regex extrae el campo **stat:** como se define en la sección **Apéndice B** de la **especificación de SMPP 3.4**.

* La cuarta parte (**000** en este ejemplo) del mensaje de error corresponde al código de error extraído del SR mediante la regex de extracción de código de error definida en la cuenta externa de SMS.

   Esta regex se especifica en la pestaña **[!UICONTROL SMSC specificities]** de la cuenta externa.

   De manera predeterminada, la regex extrae el campo **err:** tal y como se define en la sección **Apéndice B** de la **especificación de SMPP 3.4**.

* Todo lo que aparece después del símbolo de barra vertical (|) se muestra solo en la columna **[!UICONTROL First text]** de la tabla **[!UICONTROL Delivery log qualification]**. Este contenido siempre se sustituye por **#MESSAGE#** después de normalizar el mensaje. Este proceso evita tener varias entradas para errores similares y funciona igual que para los correos electrónicos.

El conector genérico extendido SMPP aplica un método heurístico para buscar valores predeterminados coherentes: si el estado comienza con **DELIV**, se considera un éxito porque coincide con los estados comunes utilizados por la mayoría de los proveedores **DELIVRD** o **DELIVERED.** Cualquier otro estado conlleva un error grave.
