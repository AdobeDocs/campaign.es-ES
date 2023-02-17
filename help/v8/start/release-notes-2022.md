---
title: Notas de la versión de Campaign v8 de 2022
description: Lista de funciones y mejoras incluidas en las versiones de Campaign v8 de 2022
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
source-git-commit: e7f4982a9b13fe5413b6cce0a1cc58e2b3a6afa4
workflow-type: ht
source-wordcount: '1839'
ht-degree: 100%

---

# Notas de la versión de 2022{#2022-rn}

Esta página lista las nuevas funcionalidades, mejoras y correcciones que se proporcionan con las **versiones de Campaign v8 de 2022**.

## Versión 8.4.2 {#release-8-4-2}

_28 de octubre de 2022_

**Mejoras**

* Se ha corregido un problema que impedía que el indicador de envío de éxito se actualizara correctamente al usar el MTA mejorado de Adobe Campaign. (NEO-50462)

## Versión 8.4.1 {#release-8-4-1}

_30 de septiembre de 2022_

**Novedades**

<table> 
<thead>
<tr> 
<th> <strong>Integración de Adobe Campaign con Adobe Experience Platform</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Los nuevos conectores de origen y destino ya están disponibles para una integración optimizada entre Adobe Campaign y Adobe Experience Platform:</p>
<ul><li>Utilice el conector de destino de Adobe Campaign Managed Cloud Services para enviar segmentos de Experience Platform a Adobe Campaign para su activación,</li>
<li>Utilice el conector de destino de Adobe Campaign Managed Cloud Services para enviar los registros de envío y seguimiento de Adobe Campaign a Adobe Experience Platform.</li>
</ul>
<p>Para obtener más información, consulte la <a href="../connect/ac-aep.md">documentación detallada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilidad del canal Twitter</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>El <a href="../send/twitter.md">Canal social de Twitter</a> ya está disponible con Campaign v8. Puede hacer lo siguiente:</p>
<ul> 
<li><p>Enviar mensajes en Twitter: Adobe Campaign permite publicar mensajes directamente en la cuenta de Twitter. También puede enviar mensajes directos a todos sus seguidores. 
</p></li>
<li><p>Recopile nuevos contactos: Adobe Campaign puede recuperar automáticamente los datos de perfil, lo que le permite llevar a cabo campañas de objetivos e implementar estrategias multicanal.
</p></li>
</ul>
<p>Obtenga información sobre cómo conectar Campaign y Twitter en la <a href="../connect/ac-tw.md">documentación detallada</a>.</p>
<p>Aprenda a publicar tweets y a enviar mensajes directos con Campaign en <a href="../connect/ac-tw.md">esta página</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Mejora de la seguridad**

Para optimizar la seguridad, los tokens de seguridad se han eliminado de las direcciones URL generadas por Campaign:

* Este cambio solo se aplica a las direcciones URL de GET. Otros tipos, incluidas las direcciones URL de POST, no se ven afectados.
* Si utiliza un código personalizado, los tokens de seguridad ya no se recuperan del parámetro del token de seguridad de URL de GET. Debe generar un nuevo token de seguridad utilizando el siguiente código JSSP:

   ```getNewSecurityToken(jsspContext.getSessionToken(), jsspContext.getSecurityToken(), true);```

   También puede utilizar la API de inicio de sesión para recuperar tokens de seguridad.
* No hay cambios en la administración de tokens de sesión.

**Mejoras**

* Tras el fin de vida útil de Microsoft Internet Explorer 11, el motor de renderización de HTML en la consola utiliza ahora **Microsoft Edge Chromium**. Además, la instalación del tiempo de ejecución de **Microsoft Edge WebView 2** es ahora necesaria para cualquier instalación de la consola del cliente.
* Se ha mejorado la ejecución del flujo de trabajo con alta disponibilidad, lo que permite ejecutar flujos de trabajo simultáneos en diferentes contenedores para evitar la pérdida del servicio del flujo de trabajo y los errores de ejecución relacionados. **Nota**: esta nueva funcionalidad se lanza con disponibilidad limitada solo para un conjunto de clientes.
* Las solicitudes de privacidad se realizan ahora en lote para un área de nombres de privacidad determinada. Esta mejora aumenta el tiempo de ejecución de las solicitudes de eliminación de RGPD/privacidad.

**Actualizaciones de compatibilidad**

* El SDK de Campaign v8 ya es compatible con iOS 16 para las notificaciones push.

Consulte la [Matriz de compatibilidades de Campaign](compatibility-matrix.md).

**Parches**

* Se ha corregido un problema que afectaba a las actualizaciones de estado del registro de envío en la instancia MID, cuando la opción FeatureFlag_GZIP_Compression estaba activada. (NEO-49183)
* Se ha corregido un problema que podía hacer que los envíos permanecieran en el estado **Pendiente** incluso si se había llegado a la fecha de contacto. (NEO-48079)
* Se ha corregido un problema en los flujos de trabajo que podía impedir que los archivos se actualizaran en el servidor al usar la actividad **Carga de datos (archivo)**. El proceso se detuvo al 100 % pero nunca se finalizó. (NEO-47269)
* Se ha corregido un problema durante la posactualización en entornos japoneses. (NEO-46640)
* Se ha corregido un problema que se podía producir si una envío alcanzaba un tamaño específico durante el proceso de MTA. (NEO-46097)
* Se ha corregido un problema que impedía que los registros de seguimiento devolvieran datos relacionados con el explorador del destinatario. (NEO-46612)
* Se ha corregido un problema que provocaba problemas de personalización al enviar mensajes SMS mediante un modo de envío externo. (NEO-46415)
* Se ha corregido un problema que podía generar duplicados en los registros de seguimiento. (NEO-46409)
* Se ha corregido un problema que impedía que el flujo de trabajo técnico **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) no se detuviera aunque se produjese un error durante su ejecución. (NEO-46280)
* Para evitar una lentitud al enviar la prueba a las direcciones semilla, todas las réplicas consecutivas de los miembros semilla ahora se agrupan en una solicitud de replicación. (NEO-44844)
* Se ha corregido un problema que mostraba un error al intentar previsualizar una entrega en cualquier evento archivado del Centro de mensajes. (NEO-43620)
* Se ha corregido un problema que se producía al insertar datos en la base de datos de nube de Snowflake con una actividad de **Consulta de Campaign** y una actividad de **Cambiar fuente de datos**: el proceso fallaba cuando había un carácter de barra invertida presente en los datos. La cadena de fuente no se escapó y los datos no se procesaron correctamente en Snowflake. (NEO-45549)
* Se ha corregido un problema que se producía al usar la actividad **Consulta** y filtrar una tabla. Cuando un nombre de columna contenía la palabra &quot;Actualización&quot;, se producía un error de compilación con un identificador no válido y el siguiente mensaje: &quot;número de filas actualizado&quot;. (NEO-46485)
* El flujo de trabajo técnico para la **Limpieza de base de datos** ahora también gestiona los esquemas de ensayo personalizados. (NEO-48974)
* Se ha corregido un problema que podía ralentizar el análisis de envío, durante el paso de exclusión de destinatarios incluida en la lista de bloqueados, al dirigirse a grandes volúmenes de destinatarios. (NEO-48019)
* Se ha mejorado la estabilidad al gestionar cadenas XML no válidas durante las llamadas SOAP. (NEO-48027)
* Se ha corregido un problema que provocaba la creación de elementos DeliveryParts innecesarios cuando el envío utilizaba modos de calendario y división. (NEO-48634)
* Se ha corregido un problema de rendimiento al usar olas basadas en calendario. (NEO-48451)
* Se ha corregido un problema que podría provocar un mensaje de error en la pantalla de la lista de envíos después de crear una nueva asignación de destino en un esquema personalizado. (NEO-49237)
* Se ha corregido un problema que podía causar pérdida de datos si el flujo de trabajo de preparación era erróneo y el periodo de retención había transcurrido por completo. (NEO-48975)

## Versión 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> La actualización de la consola de cliente es obligatoria. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#download-ac-console).

_7 de octubre de 2022_

**Mejoras**

* Se ha corregido un problema que afectaba a las actualizaciones de estado del registro de envío en la instancia MID, cuando la opción FeatureFlag_GZIP_Compression estaba activada. (NEO-49183)
* El flujo de trabajo técnico para la **Limpieza de base de datos** ahora también gestiona los esquemas de ensayo personalizados. (NEO-48974)
* Se ha corregido un problema que podía ocasionar que los envíos permanecieran en el estado **Pendiente** aunque se hubiera alcanzado la fecha de contacto. (NEO-48079, NEO-48251)
* Se ha mejorado la estabilidad al gestionar cadenas XML no válidas durante las llamadas SOAP. (NEO-48027)
* Se ha corregido un problema que podía ralentizar el análisis de envío, durante el paso de exclusión de destinatarios incluida en la lista de bloqueados, al dirigirse a grandes volúmenes de destinatarios. (NEO-48019)
* Para evitar la lentitud al enviar la prueba a las direcciones semilla, todas las réplicas consecutivas de los miembros semilla ahora se agrupan en una solicitud de réplica. (NEO-44844)
* Se ha corregido un problema que provocaba problemas de personalización al enviar mensajes SMS mediante un modo de envío externo. (NEO-46415)
* Se ha corregido un problema que mostraba un error al intentar previsualizar una entrega en cualquier evento archivado del Centro de mensajes. (NEO-43620)
* Se ha corregido un problema en los flujos de trabajo que podía impedir que los archivos se actualizaran en el servidor al usar la actividad **Carga de datos (archivo)**. El proceso se detuvo al 100 % pero nunca se finalizó. (NEO-47269)
* Se ha corregido un problema que provocaba la creación de elementos DeliveryParts innecesarios cuando el envío utilizaba modos de calendario y división. (NEO-48634)
* Se ha corregido un problema de rendimiento al usar olas basadas en calendario. (NEO-48451)
* Se ha corregido un problema que podría provocar un mensaje de error en la pantalla de la lista de envíos después de crear una nueva asignación de destino en un esquema personalizado. (NEO-49237)
* Se ha corregido un problema que se podía producir si una envío alcanzaba un tamaño específico durante el proceso de MTA. (NEO-46097)
* Se ha corregido un problema que impedía que los registros de seguimiento devolvieran datos relacionados con el explorador del destinatario. (NEO-46612)
* Se ha corregido un problema durante la posactualización en entornos japoneses. (NEO-46640)
* Se ha corregido un problema que se producía al usar la actividad **Consulta** y filtrar una tabla. Cuando un nombre de columna contenía la palabra &quot;Actualización&quot;, se producía un error de compilación con un identificador no válido y el siguiente mensaje: &quot;número de filas actualizado&quot;. (NEO-46485)
* Se ha corregido un problema que impedía que el flujo de trabajo técnico **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) no se detuviera aunque se produjese un error durante su ejecución. (NEO-46280)
* Se ha corregido un problema que podía causar pérdida de datos si el flujo de trabajo de preparación era erróneo y el periodo de retención había transcurrido por completo. (NEO-48975)
* Se ha corregido un problema que se producía al insertar datos en la base de datos de nube de Snowflake con una actividad de **Consulta de Campaign** y una actividad de **Cambiar fuente de datos**: el proceso fallaba cuando había un carácter de barra invertida presente en los datos. La cadena de fuente no se escapó y los datos no se procesaron correctamente en Snowflake. (NEO-45549)

## Versión 8.3.8 {#release-8-3-8}

_18 de mayo de 2022_

**Novedades**

<table> 
<thead>
<tr> 
<th> <strong>Notificaciones con distinción de tiempo</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Con iOS 15, Apple ha agregado una noción de notificaciones importantes que permite al desarrollador de la aplicación controlar el modo de evitar el enfoque cuando una notificación se considera importante y necesita llegar al usuario en tiempo real.</p>
<p>Para obtener más información, consulte la <a href="../send/push.md#send-notifications-on-ios">documentación detallada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Integración de Privacy Service Core</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>La versión 8 de Campaign ahora se integra con el servicio principal de privacidad de Adobe. A través de la integración del Servicio principal de privacidad: las solicitudes de privacidad enviadas desde el Servicio principal de privacidad a todas las soluciones de Experience Cloud las gestiona Campaign de forma automática a través de un flujo de trabajo dedicado.</p>
<p>Para obtener más información, consulte la <a href="privacy.md">documentación detallada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table>
<thead>
<tr>
<th><strong>Gestor de respuestas</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>La gestión de respuestas de campañas permite medir el éxito y el ROI de las campañas de marketing u ofrecer propuestas en todos los canales: correo electrónico, móvil, correo directo, etc.</p>
<p>Para obtener más información, consulte la <a href="../start/campaigns.md#response-manager-add-on">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Marketing distribuido</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>El marketing distribuido de Campaign permite implementar campañas de colaboración entre entidades centrales (sede central, departamentos de marketing, etc.) y entidades locales (puntos de venta, agencias regionales, etc.). A través de un espacio de trabajo compartido (paquetes de campañas), puede crear plantillas de campaña y proponerlas a las entidades locales.</p>
<p>Para obtener más información, consulte la <a href="../start/campaigns.md#distributed-marketing-add-on">documentación detallada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Actualizaciones de compatibilidad**

* El SDK de la versión 8 de Campaign ahora es compatible con Android 12 y iOS 15 para las notificaciones push.
* La versión 8 de Campaign ahora es compatible con Windows 11.

Consulte la [Matriz de compatibilidades de Campaign](compatibility-matrix.md).

**Mejoras**

* La autenticación OAuth 2.0 de Microsoft Exchange Online para POP3 ahora es compatible con Campaign. [Más información](../config/external-accounts.md#bounce-mails-external-account)
* Se han aplicado correcciones críticas con respecto a la API web del conector de Microsoft Dynamics.
* Se ha añadido el nuevo derecho denominado Operator y group schema write (operatorWrite) para permitir a los usuarios insertar, actualizar y eliminar esquemas Operators (xtk:operator) y Operator groups (xtk:group).

<!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
<!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* Ahora se pueden configurar varias cuentas activas de LINE en un solo intermediario.
* El número de conexiones predeterminadas para el proceso web ha aumentado de 50 a 150.
* Campaign viene con un conjunto de nuevos mecanismos de protección para evitar la inserción de claves duplicadas en la base de datos de Snowflake. [Más información](../architecture/keys.md)

**Parches**

* Se ha corregido un problema que se producía al usar semillas y grupos de control en la misma entrega recurrente. (NEO-41197)
* Se ha corregido un problema en FDAC que provocaba que el envío de correo electrónico se bloqueara para todos los destinatarios que pertenecen a la misma deliveryPart durante el proceso de envío (hasta 256) cuando los bloques de personalización contenían uno de los siguientes caracteres: `' & < > "`. Estos caracteres ahora se admiten en bloques de personalización (ejemplo: firstname=&quot;Brian O&#39;Neil&quot;). (NEO-43184)
* Se ha corregido un problema que podría provocar un error en el flujo de trabajo de seguimiento al usar un esquema personalizado como asignación de destino. Ahora nos aseguramos de que el tipo del vínculo externo a un esquema de direccionamiento personalizado es correcto al generar el esquema broadLog mediante el asistente de asignación de destino. (NEO-43506)
* Se ha corregido un problema que podía provocar que los flujos de trabajo de implementación de FDAC fallaran en idiomas distintos del inglés. (NEO-44561)

## Versión 8.2.10 {#release-8-2-10}

_2 de febrero de 2022_

**Parches**

* Se ha corregido un problema que hacía que la preparación de la entrega fallara si se llegaba al número máximo de mensajes definido en las reglas de tipología.
* Se ha corregido un problema durante la configuración del conector de Adobe Analytics cuando la dirección de correo electrónico contenía un carácter “s”.
* Se ha corregido un problema durante la posactualización que podía provocar que la tabla deliveryMapping perdiera datos de una asignación de entrega personalizada.
* Se ha corregido un problema que podía hacer que los destinatarios recibieran el mismo mensaje varias veces para la misma entrega cuando la dirección de correo electrónico contenía un carácter de comillas simples (&#39;). Este carácter ahora se escapa. (NEO-41198)
* Se ha corregido un problema de generación de ID al enviar pruebas con direcciones semilla o de sustitución. (NEO-42637)
* Se ha corregido un problema que podía impedir que se enviaran pruebas utilizando el método de sustitución de direcciones. (NEO-40417)
* Se ha corregido un problema que impedía instalar el paquete LINE. (NEO-42503)
