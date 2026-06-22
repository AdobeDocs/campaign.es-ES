---
title: Información general de monitorización de Campaign
description: Obtenga información sobre cómo monitorizar entregas, flujos de trabajo y la instancia de Campaign
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 6cf587ecc9cc1e4cf9b3de0d2067e0c4562afe01
workflow-type: tm+mt
source-wordcount: 2206
ht-degree: 4%

---

# Información general de monitorización de Campaign {#monitor-campaign}

Adobe Campaign le ofrece visibilidad en todos los niveles, desde si se entregó un mensaje individual, hasta por qué falló un flujo de trabajo o cuánta capacidad de base de datos le queda. Esta página asigna todas las funcionalidades de monitorización para que sepa dónde buscar cuando algo necesita atención.

>[!NOTE]
>
>Como administrador de Campaign, también puede usar [Panel de control de Campaign de Campaign](#control-panel) para supervisar las instancias, administrar el rendimiento y configurar opciones con capacidades de autoservicio.

>[!TIP]
>
>**¿No está seguro de por dónde empezar?**
>
>- Comprobando una campaña por parte de un experto en marketing→ [Supervise sus envíos](#monitor-deliveries)
>- Solucionar problemas de un flujo de trabajo → [Supervisar flujos de trabajo](#monitor-workflows)
>- El administrador está comprobando el estado de la instancia → [Supervise su instancia](#monitor-instance)

## Monitorización de entregas {#monitor-deliveries}

La monitorización de las entregas una vez enviadas es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Después de realizar una entrega, puede monitorizar su estado y rastrear las métricas clave en el panel de entrega. El panel proporciona acceso a los registros de envío, los registros de exclusión, los registros de seguimiento y otras funcionalidades de monitorización para ayudarle a analizar el rendimiento de su envío en todos los canales.

>[!NOTE]
>
>**Nuevo en Campaign?** El panel de entregas es la pantalla principal del día a día. Abra cualquier entrega enviada, haga clic en la pestaña **Registros** y verá qué destinatarios recibieron el mensaje, cuáles se excluyeron y por qué, y quién hizo clic o abrió.

**Envíos de correo electrónico**: supervise el estado de envío de los correos electrónicos, realice un seguimiento de las métricas clave y acceda a los registros detallados. Obtenga más información sobre [supervisión de entregas en la interfaz de usuario de Campaign](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/monitor/delivery-dashboard), [estados de entrega](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/monitor/delivery-statuses) y [supervisión de entregas por correo electrónico](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/emails/send#email-monitoring).

**Envíos de SMS**: rastree el estado de envío de SMS y supervise las métricas clave en el panel de envío de SMS. Más información sobre la [supervisión de SMS](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/sms/sms-monitor).

**Notificaciones push**: supervise las entregas de notificaciones push para garantizar que lleguen a los usuarios de su aplicación móvil de forma eficaz. Más información sobre la [supervisión de notificaciones push](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/push/push#push-test).

**Mensajes transaccionales**: para los mensajes activados por eventos, supervise el estado de procesamiento de eventos, la ejecución de mensajes y el estado de envío. Más información sobre la [supervisión de mensajes transaccionales](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/real-time/event/delivery-execution#monitor-messages).

**Errores de entrega**: comprender por qué falló una entrega es fundamental para mantener una base de datos limpia y garantizar buenas tasas de entrega. Los errores de entrega se clasifican en tres tipos: comprender la diferencia le ayuda a decidir qué acción realizar:

| Tipo de error | Lo que significa | Qué hace Campaign |
| --- | --- | --- |
| **Rechazo fuerte** | La dirección no es válida de forma permanente (no existe, dominio desconocido) | El contacto se pone automáticamente en cuarentena: no se segmentará en entregas futuras |
| **Rebote suave** | Un problema temporal (buzón lleno, servidor no disponible temporalmente) | Reintentos de Campaign automáticamente durante un periodo configurado |
| **Ignorado** | La dirección ya se había puesto en cuarentena o en una lista de bloqueados antes de enviarse | No se realiza ningún intento; se cuenta por separado de las devoluciones |

Más información sobre [errores y cuarentenas de entregas](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/monitor/delivery-failures).

## Monitorización de la capacidad de entrega {#monitor-deliverability}

>[!NOTE]
>
>Un mensaje contabilizado como &quot;entregado&quot; significa que fue aceptado por el servidor receptor; no garantiza la colocación en la bandeja de entrada. La monitorización de la capacidad de entrega indica si la autenticación del dominio de envío, la reputación de la IP y el contenido del correo electrónico cumplen los estándares del proveedor de la bandeja de entrada.

La monitorización de la capacidad de entrega le ayuda a garantizar que los mensajes lleguen a las bandejas de entrada de los destinatarios y evitar filtros de correo no deseado. Adobe Campaign proporciona varias herramientas integradas para monitorizar y mejorar la capacidad de entrega, incluidos informes de entrega, procesamiento de la bandeja de entrada, pruebas de SpamAssassin y estadísticas de difusión. Seguir las prácticas recomendadas de envío, como mantener una lista de correo electrónico limpia, monitorizar la reputación del remitente y autenticar los dominios de envío es fundamental para mantener buenas tasas de envío.

Obtenga más información sobre las [herramientas de monitorización de capacidad de envío](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/deliverability-management/monitoring-deliverability) y las [prácticas recomendadas de capacidad de envío](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/deliverability-management/about-deliverability).

## Monitorización de flujos de trabajo {#monitor-workflows}

Los flujos de trabajo son esenciales para automatizar las campañas de marketing y el procesamiento de datos. La monitorización de la ejecución del flujo de trabajo le ayuda:

- Garantizar que los flujos de trabajo se completen correctamente
- Identificar y solucionar errores
- Optimización del rendimiento del flujo de trabajo

>[!TIP]
>
>Si un flujo de trabajo muestra el estado **Failed**, ábralo, haga clic con el botón derecho en la actividad roja y seleccione **Display logs**. El mensaje de error identifica exactamente qué ha fallado y en qué registro.

### Funcionalidades de monitorización del flujo de trabajo {#workflow-monitoring}

**Supervisar los siguientes elementos de flujo de trabajo:**

**Estado de ejecución del flujo de trabajo**: efectúe el seguimiento de si los flujos de trabajo se están ejecutando, están en pausa, han fallado o se han completado. [Más información sobre la ejecución del flujo de trabajo](https://experienceleague.adobe.com/es/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#_blank)

**Registros de ejecución de actividades**: acceda a los registros detallados de cada actividad de flujo de trabajo para solucionar problemas y optimizar el rendimiento.

**Mapa de calor del flujo de trabajo**: una descripción general visual de todos los flujos de trabajo que se ejecutan simultáneamente en la instancia. Utilícelo para identificar períodos de carga máxima, flujos de trabajo puntuales que consumen recursos desproporcionados y planificar la programación para evitar conflictos de ejecución. Disponible solo para administradores de Campaign. [Más información sobre el mapa de calor del flujo de trabajo](https://experienceleague.adobe.com/es/docs/campaign/automation/workflows/monitoring-workflows/heatmap#_blank)

**Historial del flujo de trabajo**: haga un seguimiento de todas las ejecuciones y modificaciones del flujo de trabajo a lo largo del tiempo para comprender el comportamiento y el rendimiento del flujo de trabajo.

## Monitorización de la instancia {#monitor-instance}

La monitorización de instancias ayuda a garantizar el estado y el rendimiento de su entorno de Adobe Campaign. En el caso de los servicios administrados en la nube de Campaign v8, Adobe también supervisa y administra la infraestructura en su nombre. Más información sobre la [supervisión administrada por Adobe](#adobe-cloud-monitoring).

### Pista de auditoría {#audit-trail}

La interfaz de autoservicio Pista de auditoría permite monitorizar los cambios realizados en la instancia de Adobe Campaign. La pista de auditoría captura, en tiempo real, una lista completa de las acciones y eventos que se producen dentro de la instancia.

**Usar pista de auditoría para:**

- **Rastrear cambios de componentes**: supervise lo que ha sucedido a sus flujos de trabajo, esquemas, opciones y otros componentes
- **Identificar quién hizo cambios**: Ver quién actualizó por última vez un elemento específico y cuándo
- **Comprender las acciones del usuario**: revise lo que los usuarios hicieron en la instancia para solucionar problemas o auditar
- **Mantener el cumplimiento**: haga un seguimiento de todos los cambios de configuración por motivos de cumplimiento y seguridad

Se puede acceder a la pista de auditoría a través de la consola del cliente de Campaign y proporciona información detallada sobre las acciones realizadas por los usuarios.

Más información sobre [Pista de auditoría](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/analytics/audit-trail)

### Monitorización del rendimiento {#performance-monitoring}

La versión 8 de Campaign proporciona varias funciones de monitorización para rastrear el rendimiento de la instancia y garantizar un funcionamiento óptimo:

**Supervisión de bases de datos**: supervise el uso y la capacidad de las bases de datos mediante el Panel de control de Campaign para garantizar un rendimiento y una administración del almacenamiento óptimos. [Más información acerca de la supervisión de bases de datos](https://experienceleague.adobe.com/es/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring#_blank)

**Supervisión de perfiles activos**: realice un seguimiento del uso de perfiles activos en relación con los límites contractuales para mantener el cumplimiento y optimizar la asignación de recursos. [Más información sobre los perfiles activos](https://experienceleague.adobe.com/es/docs/control-panel/using/performance-monitoring/active-profiles-monitoring#_blank)

**Supervisión del flujo de trabajo**: supervise el estado de ejecución del flujo de trabajo para identificar flujos de trabajo de larga duración y garantizar que todos los flujos de trabajo técnicos se ejecuten correctamente. [Más información sobre flujos de trabajo técnicos](#technical-workflows)

**Rendimiento y latencia de entrega** - Rastree el rendimiento de entrega (mensajes enviados por hora) y la latencia para comunicaciones transaccionales a través del Panel de control de Campaign. [Más información sobre la supervisión del rendimiento](https://experienceleague.adobe.com/es/docs/control-panel/using/performance-monitoring/throughputs-latencies#_blank)

>[!NOTE]
>
>En Campaign v8 Managed Cloud Services, Adobe supervisa y administra la infraestructura del servidor (CPU, memoria, disco). Más información sobre la [supervisión administrada por Adobe](#adobe-cloud-monitoring).

### Monitorización administrada por Adobe {#adobe-cloud-monitoring}

Adobe Campaign Cloud Services proporciona una asistencia esencial para las necesidades de entrega de las experiencias de los clientes más exigentes a través de una infraestructura de nube flexible. Esto permite a las organizaciones iniciar, monitorizar y optimizar las experiencias de los clientes sin necesidad de administrar u operar la infraestructura de Campaign por sí mismas.

Adobe supervisa los entornos de Cloud Services de Campaign para ayudar a administrar varios problemas y minimizar las interrupciones detectando problemas técnicos y proporcionando información continua sobre el rendimiento y los proyectos en curso.

**Cómo responde Adobe**

Adobe supervisa todos los equipos de red esenciales en la red de Campaign las 24 horas del día, los 7 días de la semana, y recibe notificaciones de los sistemas de monitorización cuando se necesitan correcciones o escalaciones. Al detectar un problema, el sistema utiliza mecanismos de reinicio automático e inicio automático para intentar la corrección. Si el sistema no se corrige automáticamente, el equipo de ingeniería de Adobe On-Call interviene para realizar la resolución de problemas en función de los runbooks de alertas predefinidos.

>[!NOTE]
>
>Algunas acciones de monitorización realizadas por Adobe aparecen en los registros de Campaign bajo el usuario **campaign-loginmonitor**.

Además de la supervisión interna de Adobe, puede acceder a las funciones de supervisión directamente a través de la consola del cliente de Campaign o el [Panel de control de Campaign de Campaign](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/permissions/self-service). Con el Panel de control de Campaign, puede suscribirse a alertas en tiempo real sobre sus instancias y recibir pasos de corrección recomendados para incidentes identificados (por ejemplo, certificados SSL próximos a la caducidad).

**Supervisando taxonomía**

Adobe supervisa su entorno en tres niveles:

| Nivel | Grupo | Impacto potencial en la empresa |
| --- | --- | --- |
| **Nivel 1: Infraestructura** | Agotamiento del espacio de base de datos | Problemas de rendimiento, incluida la incapacidad para iniciar sesión, ejecutar envíos por lotes o ejecutar consultas |
| **Nivel 1: Infraestructura** | Disponibilidad de base de datos | Es posible que los usuarios y servicios no puedan utilizar el sistema |
| **Nivel 1: Infraestructura** | Sobrecarga de base de datos (saldo de ráfaga) | Problemas de rendimiento, incluida la incapacidad para iniciar sesión, ejecutar envíos por lotes o ejecutar consultas |
| **Nivel 1: Infraestructura** | Secuencia de base de datos y agotamiento de ID de transacción | No se pueden crear nuevos flujos de trabajo, envíos o enviar correos electrónicos por lotes |
| **Nivel 1: Infraestructura** | Almacenamiento SFTP | No se pueden actualizar o recuperar datos en los servidores SFTP |
| **Nivel 2: plataforma y web** | Inicio de sesión | Es posible que los usuarios no puedan iniciar sesión; es posible que las actividades programadas y los flujos de trabajo no se ejecuten |
| **Nivel 2: plataforma y web** | Bloqueo de API | Es posible que los usuarios o servicios no puedan autenticar ni ejecutar operaciones |
| **Nivel 2: plataforma y web** | Web | No se pueden crear nuevas conexiones a Campaign |
| **Nivel 2: plataforma y web** | Red de centros de datos | Problemas de rendimiento o no disponibilidad completa para los usuarios del centro de datos |
| **Nivel 3: Software** | Seguimiento de una entrega | El procesamiento de los registros de seguimiento no está disponible |
| **Nivel 3: Software** | inMail | Sin comentarios sobre errores y devoluciones de envíos de correo electrónico |
| **Nivel 3: Software** | Estado del centro de mensajes | No se pueden enviar envíos transaccionales |
| **Nivel 3: Software** | MTA | No se pueden enviar envíos de correo electrónico programados y específicos |
| **Nivel 3: Software** | Estado del servidor de flujo de trabajo | No se pueden ejecutar flujos de trabajo |
| **Nivel 3: Software** | Disponibilidad de API web | No se pueden procesar solicitudes HTTP ni ejecutar llamadas API |
| **Nivel 3: Software** | Interacciones entrantes | No se pueden procesar las interacciones entrantes |

>[!NOTE]
>
>Adobe Campaign Cloud Services se basa en una estrategia de varias nubes y ofrece implementaciones en AWS y Azure. Debido a las diferencias de proveedor, las capacidades de monitorización difieren entre AWS, Azure y otras implementaciones de centros de datos. La tabla anterior se aplica a los clientes de Cloud Services de Campaign alojados en AWS a menos que se indique lo contrario. Tenga en cuenta también que Adobe Campaign no expone actualmente a los clientes todos los datos de monitorización utilizados por el ingeniería de llamadas.

### Flujos de trabajo técnicos {#technical-workflows}

Los flujos de trabajo técnicos son procesos esenciales que se ejecutan en segundo plano para mantener la instancia de Campaign.

**Supervisar que los flujos de trabajo técnicos son:**

- Ejecución según lo programado
- Finalización correcta sin errores
- Procesamiento correcto de los datos

**Flujos de trabajo técnicos clave que supervisar:**

| Flujo de trabajo | Objetivo | Si falla |
| --- | --- | --- |
| **Seguimiento** | Procesa los datos de seguimiento de las entregas de correo electrónico | Las métricas de clic y apertura dejan de actualizarse en los informes |
| **Limpieza** | Quita los datos y registros antiguos para mantener el rendimiento de la base de datos | El crecimiento de la base de datos es descontrolado, lo que degrada el rendimiento de consultas y entregas |
| **Actualización de la capacidad de envío** | Actualiza las reglas de envío y los patrones de filtro de spam | Las reglas se quedan obsoletas; la precisión del filtrado puede degradarse |
| **Limpieza de base de datos** | Purga los registros de envío y seguimiento antiguos | La acumulación de registros ralentiza las consultas y los informes con el tiempo |

Más información sobre [flujos de trabajo técnicos](https://experienceleague.adobe.com/es/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows#_blank)

### Panel de control de Campaign {#control-panel}

El Panel de control de Campaign de trabajo de Campaign proporciona a los administradores funciones de autoservicio para monitorizar y administrar instancias de Campaign.

| Tipo de supervisión | Funcionalidades |
| --- | --- |
| **Rendimiento** | Rastree el uso activo del perfil, monitorice el uso y la capacidad de la base de datos, vea el estado de ejecución del flujo de trabajo, monitorice el rendimiento de entrega y la latencia |
| **Infraestructura** | Monitorización de la capacidad de almacenamiento SFTP, seguimiento de la configuración de subdominios, monitorización de la caducidad del certificado SSL, administración de la lista de IP permitidas |
| **Instancia** | Ver la versión de compilación y los paquetes instalados, supervisar la configuración del sistema y administrar los dominios externos autorizados |

Obtenga más información sobre [Panel de control de Campaign](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/permissions/self-service) y [supervisión del rendimiento del Panel de control de Campaign](https://experienceleague.adobe.com/es/docs/control-panel/using/performance-monitoring/about-performance-monitoring#_blank)

>[!NOTE]
>
>En Campaign v8 Managed Cloud Services, Adobe supervisa y administra la infraestructura del servidor, el sistema operativo y la capa de aplicaciones. Más información sobre la [supervisión administrada por Adobe](#adobe-cloud-monitoring). Puede utilizar las funcionalidades de monitorización descritas en esta página y Panel de control de Campaign para monitorizar el rendimiento de las instancias, los flujos de trabajo y los envíos.

## Seguimiento y creación de informes {#tracking-reporting}

### Seguimiento de mensajes {#message-tracking}

Realice un seguimiento del comportamiento de los destinatarios y mida la eficacia de sus campañas:

- **Aperturas**: Rastrea cuándo los destinatarios abren tus correos electrónicos
- **Clics**: Supervise qué vínculos hacen clic los destinatarios
- **Cancelaciones de suscripción**: Rastrear solicitudes de exclusión
- **Vistas de página espejo**: Ver cuántos destinatarios ven el correo electrónico en un explorador

Más información sobre [seguimiento de mensajes](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/analytics/tracking/tracking)

### Informes de envío {#delivery-reports}

Adobe Campaign proporciona un completo conjunto de informes para analizar el rendimiento de su entrega:

- **Resumen de envíos**: Información general sobre envíos, envíos y errores
- **Indicadores de seguimiento**: Aperturas, clics y tasas de pulsaciones
- **URL y flujos de clics**: Vínculos más populares en las entregas
- **Clics activos**: representación visual de dónde hicieron clic los destinatarios en el correo electrónico

Más información sobre [informes de envío](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/analytics/reports/ac-reports/delivery-reports)

### Informes globales {#global-reports}

Acceda a informes globales para analizar el rendimiento de todas las campañas y envíos:

- **Rendimiento de entrega**: mensajes enviados a lo largo del tiempo
- **Rechazos y no entregables**: análisis de los envíos fallidos
- **Actividades de usuario**: Abre, hace clic y cancela la suscripción en todas las campañas

Más información sobre [informes globales](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/analytics/reports/ac-reports/global-reports)

## Temas relacionados {#related-topics}

- [Prácticas recomendadas para envíos](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/delivery-best-practices)
- [Administración de cuarentena](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/monitor/quarantines)
- [Configuración y envío de entregas](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/send/validate/configure-and-send)
- [Introducción a la creación de informes](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/analytics/reports/gs-reporting)
