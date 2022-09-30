---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: c1a5dd3fcad5d377acb2f9df3a090897ed3b533e
workflow-type: tm+mt
source-wordcount: '2754'
ht-degree: 80%

---

# Última versión{#latest-release}

Esta página lista las nuevas funcionalidades, mejoras y correcciones que se proporcionan con la **última versión de Campaign v8**.

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
<td><p>Los nuevos conectores de origen y destino ya están disponibles para permitir una integración perfecta entre Adobe Campaign y Adobe Experience Platform:</p>
<ul><li>Utilice el conector de fuentes de nube administradas de Adobe Campaign para enviar segmentos de Experience Platform a Adobe Campaign para su activación.</li>
<li>Utilice el conector de destino de Adobe Campaign Managed Cloud para enviar los registros de envío y seguimiento de Adobe Campaign a Adobe Experience Platform.</li>
</ul>
<p>Para obtener más información, consulte la <a href="../connect/ac-aep.md">documentación detallada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilidad del canal twitter</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>La variable <a href="../send/twitter.md">Canal social de twitter</a> ya está disponible con Campaign v8. Puede hacer lo siguiente:</p>
<ul> 
<li><p>Enviar mensajes en Twitter: Adobe Campaign permite anunciar mensajes directamente en la cuenta de twitter. También puede enviar mensajes directos a todos sus seguidores de 
</p></li>
<li><p>Recopile nuevos contactos: Adobe Campaign puede recuperar automáticamente los datos de perfil, lo que le permite llevar a cabo campañas de objetivos e implementar estrategias multicanal.
</p></li>
</ul>
<p>Obtenga información sobre cómo conectar Campaign y Twitter en la <a href="../connect/ac-tw.md">documentación detallada</a>.</p>
<p>Aprenda a publicar tweets y enviar mensajes directos con Campaign en <a href="../connect/ac-tw.md">esta página</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Mejoras**

* Tras el fin de vida útil de Microsoft Internet Explorer 11, el motor de renderización del HTML de la consola ahora está utilizando **Microsoft Edge Chromium**. Además, la instalación de **Microsoft Edge WebView 2** el tiempo de ejecución ahora es necesario para cualquier instalación de la consola del cliente.
* Se ha mejorado la ejecución del flujo de trabajo con alta disponibilidad del flujo de trabajo, lo que permite ejecutar flujos de trabajo simultáneos en diferentes contenedores para evitar la pérdida del servicio del flujo de trabajo y los errores de ejecución relacionados. **Nota**: Esta nueva funcionalidad se presenta en Disponibilidad limitada a un conjunto de clientes solamente.
* Las solicitudes de privacidad ahora se realizan en lote para un área de nombres de privacidad determinada. Esta mejora aumenta el tiempo de ejecución de las solicitudes de eliminación de RGPD/privacidad.

**Actualizaciones de compatibilidad**

* El SDK de Campaign v8 ahora es compatible con iOS 16 para notificaciones push.

Consulte la [Matriz de compatibilidades de Campaign](compatibility-matrix.md).

**Parches**

* Se ha corregido un problema que afectaba a las actualizaciones de estado del registro de entrega en la instancia MID, cuando la opción FeatureFlag_GZIP_Compression estaba activada. (NEO-49183)
* Se ha corregido un problema que podía hacer que los envíos permanecieran en **Pendiente** incluso si se ha alcanzado la fecha de contacto. (NEO-48079)
* Se ha corregido un problema en los flujos de trabajo que podía impedir que los archivos se actualizaran en el servidor al usar la variable **Carga de datos (archivos)** actividad. El proceso se detuvo al 100% pero nunca terminó. (NEO-47269)
* Se ha corregido un problema durante la posactualización en entornos japoneses. (NEO-46640)
* Se ha corregido un problema que se podía producir si una entrega alcanzaba un tamaño preciso durante el proceso de MTA. (NEO-46097)
* Se ha corregido un problema que impedía que los registros de seguimiento devolvieran datos relacionados con el explorador del destinatario. (NEO-46612)
* Se ha corregido un problema que provocaba problemas de personalización al enviar mensajes SMS mediante un modo de envío externo. (NEO-46415)
* Se ha corregido un problema que podía generar duplicados en los registros de seguimiento. (NEO-46409)
* Se ha corregido un problema que impedía que la variable **[!UICONTROL Replicate Staging data]** El flujo de trabajo técnico (ffdaReplicateStagingData) no se detiene aunque se produzca un error durante su ejecución. (NEO-46280)
* Se ha corregido un problema que se podía producir si una entrega alcanzaba un tamaño preciso durante el proceso de MTA. (NEO-46097)
* Para evitar la lentitud al enviar la prueba a las direcciones semilla, todas las réplicas consecutivas de los miembros semilla ahora se agrupan en una solicitud de replicación. (NEO-44844)
* Se ha corregido un problema que mostraba un error al intentar previsualizar un envío en cualquier evento archivado del Centro de mensajes. (NEO-43620)
* Se ha corregido un problema que se producía al insertar datos en la base de datos de nube de Snowflake con una campaña **Consulta** actividad y **Cambiar fuente de datos** actividad: el proceso fallaba cuando había un carácter de barra invertida presente en los datos. La cadena de origen no se escapó y los datos no se procesaron correctamente en el Snowflake. (NEO-45549)
* Se ha corregido un problema que se producía al usar la variable **Consulta** actividad y filtrado de una tabla. Cuando un nombre de columna contenía la palabra &quot;Actualización&quot;, se producía un error de compilación con un identificador no válido y el siguiente mensaje: &quot;número de filas actualizadas&quot;. (NEO-46485)


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
* Campaign viene con un conjunto de nuevas protecciones para evitar la inserción de claves duplicadas en la base de datos de Snowflake. [Más información](../architecture/keys.md)

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

## Versión 8.2.8 {#release-8-2-8}

_28 de octubre de 2021_

<table>
<thead>
<tr>
<th><strong>Interacción entrante</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Real-time lnteraction Management ya está disponible para los canales entrantes. Utilice el módulo Interacción entrante de Campaign para presentar la mejor oferta a sus clientes cuando visiten su sitio web o contacten con su centro de llamadas. Esta capacidad viene como opción con Campaign v8 y requiere una configuración específica en la instancia. Póngase en contacto con el representante de Adobe para tener acceso al módulo de interacción entrante.</p>
<p>Para obtener más información, consulte la <a href="../interaction/interaction-architecture.md">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Optimización de la campaña</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Ya está disponible el módulo Optimización de la campaña. Este módulo permite controlar, filtrar y monitorizar la entrega de envíos. Para evitar conflictos entre campañas, Adobe Campaign puede probar distintas combinaciones mediante la aplicación de reglas de restricción específicas. Esto garantiza que los mensajes enviados respondan de la mejor forma a las necesidades y expectativas de los clientes, de acuerdo con las políticas de comunicación de la compañía.</p>
<p>Para obtener más información, consulte la <a href="https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=es#campaign-optimization">documentación detallada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Servicio de unicidad</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>El Servicio de unicidad es un nuevo componente del administrador de bases de datos de Cloud. Ayuda a los usuarios a preservar y controlar la integridad de las restricciones clave únicas dentro de las tablas de la base de datos de la nube. Esto le permite reducir el riesgo de insertar claves duplicadas.
<p>Como la base de datos de Cloud no impone restricciones de unicidad, el servicio de unicidad introduce en el nivel de aplicación, <b>un conjunto de nuevas barreras</b> que reduce el riesgo de insertar duplicados al administrar los datos con Adobe Campaign.</p> 
<p>El Servicio de unicidad inicia un nuevo flujo de trabajo integrado denominado <b>ffdaUnicity</b> para monitorizar las restricciones de unicidad y avisar cuando se detecten duplicados.</p>
<p>Para obtener más información, consulte la <a href="../architecture/keys.md">documentación detallada</a>.</p>
</td> </tr> 
</tbody> 
</table>


**Mejoras**

* El conector de Snowflake se ha mejorado en términos de rendimiento.
* A efectos de monitorización y pruebas, los registros de auditoría del flujo de trabajo **[!UICONTROL Replicate Staging data]** ahora incluyen el número de registros que se han enviado a la base de datos de FFDA (acceso de datos federado completo).
* La actividad de código SQL ahora le permite elegir en qué base de datos se almacenará el script SQL: la fuente de datos predeterminada o una cuenta externa de FDA activa seleccionada.
* Ya está disponible un conjunto de almacenes predefinidos que pueden utilizarse para ejecutar varias consultas en paralelo, como segmentación, ETL o picos. [Más información](../config/workflows.md)

**Otros cambios**

* La variable **[!UICONTROL Encrypted identifier]** se ha añadido al esquema del visitante (`nms:visitor`). Este campo se calcula y se utiliza para aplicaciones web.
* Se ha corregido un problema que hacía que el análisis de entrega fallara cuando existían algunas afinidades de IP en algunos contenedores de intermediario, pero no en todos ellos. Ahora todas las afinidades de IP se almacenan en la base de datos, de modo que cualquier contenedor pueda acceder a las afinidades presentes en todos los demás contenedores. (NEO-37564)
* Ahora puede importar un paquete con varios esquemas y nodos de árbol de navegación.

**Parches**

* Después de que un usuario eliminara, en un esquema de datos, la variable `<autoStg>` de un elemento de definición de tabla, o cambiara su valor de `true` a `false`, no se eliminaba la tabla de ensayo relacionada. Este problema se ha corregido.
* Se ha corregido un problema que provocaba un error al crear registros con un formulario dedicado debido a la administración de ID con un origen de datos de FFDA.
* Se ha corregido un problema que podía impedir que las ofertas se insertaran en una entrega si se gestionaban mediante una actividad de enriquecimiento en un flujo de trabajo.
* Se ha corregido un problema que podía ralentizar la importación de paquetes.
* Se ha corregido un problema que podía impedir que se enviaran entregas de correo electrónico con direcciones semilla.
* Se ha corregido un problema que podía impedir que las propuestas se guardaran en la tabla de propuestas de ofertas.
* Se ha corregido un problema que provocaba que los problemas de tiempo de espera de red se registraran incorrectamente como problemas de interrupción de secuencia de comandos en lugar de errores de red. Este problema ocurría en el caso de solicitudes HTTP incluidas en actividades JavaScript.
* Se ha corregido un problema que impedía que las ofertas se replicaran en el entorno de ofertas en directo en Snowflake.
* Se ha corregido un problema que ignoraba el atributo autoStg para esquemas integrados no ampliados.
* Se ha corregido un problema que impedía que los usuarios seleccionaran el vínculo **[!UICONTROL Country/Region]** al obtener una vista previa de un perfil.
* Se ha corregido un problema que provocaba que el selector de fecha en los informes personalizados produjera un error de script. (NEO-36345)
* Se ha corregido un problema que hacía que el sistema se bloqueara al regenerar la configuración en caso de archivos de configuración incorrectos.
* Se ha corregido un problema que impedía que las instancias de marketing y control se actualizaran correctamente.
* Se ha corregido un problema que podía provocar que el flujo de trabajo de facturación se bloqueara en las instancias de marketing.
* Se ha corregido un problema que podía provocar la duplicación de claves en tablas predeterminadas de Snowflake de FFDA. (NEO-38583)
* Se ha corregido un problema que podía provocar la pérdida de esquemas temporales de flujo de trabajo al editar dos actividades de anulación de duplicación una tras otra. (NEO-34063)
* Se ha corregido un problema que devolvía resultados incorrectos al ejecutar las funciones Amazon Redshift HoursDiff y MinutesDiff al intentar extraer el componente de tiempo.(NEO-31673)
* Se ha corregido un problema que podía impedir que los usuarios iniciaran sesión en la consola debido a un problema de configuración de proxy. (NEO-38388)
* Se ha corregido un problema de regresión que impedía que la funcionalidad **Purgar carpeta** funcionara correctamente. (NEO-37459)
* Se ha corregido un problema que podía impedir que previsualizara los envíos móviles adjuntos a un flujo de trabajo.
* Se ha corregido un problema que podía impedir que la actividad de flujo de trabajo **Leer lista** funcionara cuando la lista se identificaba en la base de datos con un ID negativo. (NEO-39607)

## Versión 8.1.20 {#release-8-1-20}

_7 de septiembre de 2021_

**Mejoras de seguridad**

* Se ha corregido un problema de seguridad para reforzar la protección contra ataques de salto de directorio. (NEO-28547)

**Mejoras**

* Tras finalizar su vida útil, se ha eliminado Flash de todas las funciones y componentes de Campaign relacionados y se ha sustituido por HTML5. Se ha eliminado el tipo de gráfico **Medición**. (NEO-30330) [Más información](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=es)
* Al instalar la consola del cliente en Windows, el instalador ahora comprueba si hay un nodo de registro principal y crea uno si falta. Esto evita posibles problemas al iniciar la consola. (NEO-34854)
* La función de firma de seguimiento se ha mejorado para evitar errores vinculados a la forma en que las herramientas de terceros (clientes de correo electrónico, navegadores de Internet, etc.) gestionan los caracteres especiales. Los parámetros de URL ahora están codificados.

**Otros cambios**

* Los conectores de Microsoft CRM retirados anteriormente (implementaciones de Office 365 y locales) se han eliminado de la interfaz. [Más información](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=es#configure-acc-for-microsoft)
* Después de la migración a Tomcat 8, el script de configuración de IIS se ha actualizado para solucionar los problemas de integración de IIS. (NEO-31019)
* Se ha agregado una protección para permitir que el [flujo de trabajo técnico de facturación](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=es#billing-report) se ejecute en la instancia de marketing.
* La identificación de la fuente de datos se ha mejorado en las pestañas de datos y esquema de la ventana **Ver población** de las transiciones de flujo de trabajo.
* Los índices de base de datos que faltaban se agregaron a los siguientes esquemas para evitar problemas de actualización de la base de datos: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Parches**

* Se ha corregido un problema que impedía que el informe **Clics activos** funcionara cuando las ofertas estaban vinculadas al envío. (NEO-26295)
* Se ha corregido un problema con la actividad **Flujo de trabajo secundario** cuando su ejecución no generaba una tabla de salida. (NEO-36242)
* Se han corregido varios problemas al exportar el informe **Análisis descriptivo** a PDF. (NEO-25847)
* Se ha corregido un problema que podría provocar errores en los envíos al utilizar un envío de correo externo. (NEO-37435)
* Se ha corregido un error al conectarse a Microsoft CRM mediante la API web. El mensaje de error se ha eliminado porque las funcionalidades no se vieron afectadas.
* Se ha corregido un problema de deduplicación del registro de seguimiento cuando el servidor mid se establecía como reenvío entre los servidores de seguimiento y marketing. (NEO-36285)
* Se ha corregido una regresión que impedía que Vault se usara como almacén de código específico.
* Se ha corregido un problema que impedía usar variables en una actividad de flujo de trabajo de **enriquecimiento** cuando la transición entrante era de una fuente de datos de FDA.
* Se ha corregido un problema con FDAC que impedía la replicación adecuada de los grupos de operadores y los derechos.
* Se ha corregido un problema que podía provocar el envío de un vínculo de baja incorrecto a través de la entrega.
* Se ha corregido un problema en la administración de la replicación que afectaba a la duración de la posactualización.
* Se ha corregido un problema que podía impedir que se mostrara **Clics activos**.
* Se ha corregido un problema que podía provocar URL rotas en los mensajes de correo electrónico.

## Versión 8.1.14 {#release-8-1-14}

_23 de julio de 2021_

**Novedades**

<table>
<thead>
<tr>
<th><strong>Nueva actividad de flujo de trabajo: Cambiar fuente de datos</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>La nueva actividad de flujo de trabajo <b>Cambiar fuente de datos</b> permite cambiar la fuente de datos de la tabla de trabajo de un flujo de trabajo. Esto proporciona una flexibilidad mejorada para administrar datos en diferentes fuentes de datos (FDA, FDAC y base de datos local).</p>
<p>En los flujos de trabajo de Adobe Campaign, los datos se administran mediante tablas de trabajo (o temporales). A medida que se ejecuta el flujo de trabajo, las tablas de trabajo comparten datos entre las actividades de flujo de trabajo. De forma predeterminada, las tablas de trabajo se crean en la misma base de datos que el origen de los datos que consultamos.</p>
<p>Con Campaign v8, la tabla de perfiles principales se almacena directamente en la base de datos de la nube. Por lo tanto, al consultar la tabla Perfiles también se creará una tabla de trabajo en la base de datos de la nube. En algunos casos, puede tener sentido mover la tabla de trabajo a otra fuente de datos para realizar operaciones específicas.</p>
<p>Para obtener más información, consulte la <a href="../config/workflows.md#change-data-source-activity">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilidad del canal LINE</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>El <a href="../send/line.md">canal LINE</a> ya está disponible con Campaign v8, e incluye las siguientes mejoras cuando se combina con el módulo <a href="../send/transactional.md">mensajería transaccional</a>:
<ul> 
<li><p>Se ha corregido un problema que podía impedir que los visitantes se dirigieran a una entrega LINE. 
</p></li>
<li><p>Se ha corregido un problema que podría provocar errores al recuperar visitantes de la instancia de ejecución a la instancia de marketing.
</p></li>
<li><p>Se han corregido problemas durante el procesamiento de eventos en tiempo real.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>


**Otras mejoras**

* Se ha corregido un problema que podía impedir que se mostrara el informe **Clics activos** para entregas específicas.
* Se ha corregido un problema con la actividad de flujo de trabajo **Anulación de duplicación** que podía provocar un recuento duplicado impreciso.
* Se ha corregido un problema que se producía al utilizar una consulta de flujo de trabajo con el filtro “El ID no está vacío”, lo que podía hacer que se mostrara un elemento vacío en la población de transición.
* Se ha corregido un problema que impedía que se crearan campos adicionales en una nueva asignación de destino.
