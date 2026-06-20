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
source-git-commit: e8438b85eec144e83b2660f9d66444c1a01863ab
workflow-type: tm+mt
source-wordcount: 2101
ht-degree: 4%

---

# Información general de monitorización de Campaign {#monitor-campaign}

Adobe Campaign le ofrece visibilidad en todos los niveles, desde si se entregó un mensaje individual, hasta por qué falló un flujo de trabajo o cuánta capacidad de base de datos le queda. Esta página asigna todas las funcionalidades de monitorización para que sepa dónde buscar cuando algo necesita atención. Como administrador de Campaign, también puede usar [Panel de control de Campaign de Campaign](#control-panel) para supervisar las instancias, administrar el rendimiento y configurar opciones con capacidades de autoservicio.

>[!TIP]
>
>**¿No está seguro de por dónde empezar?**
>
>- Comprobando una campaña por parte de un experto en marketing→ [Supervise sus envíos](#monitor-deliveries)
>- Solucionar problemas de un flujo de trabajo → [Supervisar flujos de trabajo](#monitor-workflows)
>- El administrador está comprobando el estado de la instancia → [Supervise su instancia](#monitor-instance)

## Monitorización de entregas {#monitor-deliveries}

La monitorización de las entregas una vez enviadas es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Después de realizar una entrega, puede realizar un seguimiento de su progreso y diagnosticar problemas desde el panel de entrega. El panel le permite acceder a los registros de envío, los registros de exclusión, los registros de seguimiento y otros datos de cada canal que utilice.

>[!NOTE]
>
>**Nuevo en Campaign?** El panel de entregas es la pantalla principal del día a día. Abra cualquier entrega enviada, haga clic en la pestaña **Registros** y verá qué destinatarios recibieron el mensaje, cuáles se excluyeron y por qué, y quién hizo clic o abrió.

**Envíos de correo electrónico**: supervise el estado de envío de los correos electrónicos, realice un seguimiento de las métricas clave y acceda a los registros detallados. Obtenga más información sobre [supervisión de entregas en la interfaz de usuario de Campaign](../send/delivery-dashboard.md), [estados de entrega](../send/delivery-statuses.md) y [supervisión de entregas por correo electrónico](../send/send.md#email-monitoring).

**Envíos de SMS**: efectúe el seguimiento del estado de envío de SMS y supervise las métricas clave en el panel de envío de SMS. Más información sobre la [supervisión de SMS](../send/sms/sms-monitor.md).

**Notificaciones push**: supervise las entregas de notificaciones push para garantizar que lleguen a los usuarios de su aplicación móvil de forma eficaz. Más información sobre la [supervisión de notificaciones push](../send/push.md#push-test).

**Mensajes transaccionales**: para los mensajes activados por eventos, supervise el estado de procesamiento de eventos, la profundidad de cola y los resultados de ejecución. Más información sobre la [supervisión de mensajes transaccionales](../send/delivery-execution.md#monitor-messages).

**Errores de entrega**: Es fundamental comprender por qué ha fallado una entrega para mantener una base de datos limpia y garantizar tasas de entrega correctas. Los errores de entrega se clasifican en tres tipos: comprender la diferencia le ayuda a decidir qué acción realizar:

| Tipo de error | Lo que significa | Qué hace Campaign |
| --- | --- | --- |
| **Rechazo fuerte** | La dirección no es válida de forma permanente (no existe, dominio desconocido) | El contacto se pone automáticamente en cuarentena: no se segmentará en entregas futuras |
| **Rebote suave** | Un problema temporal (buzón lleno, servidor no disponible temporalmente) | Reintentos de Campaign automáticamente durante un periodo configurado |
| **Ignorado** | La dirección ya se había puesto en cuarentena o en una lista de bloqueados antes de enviarse | No se realiza ningún intento; se cuenta por separado de las devoluciones |

Más información sobre [errores y cuarentenas de entregas](../send/delivery-failures.md).

## Monitorización de la capacidad de entrega {#monitor-deliverability}

La capacidad de entrega mide el éxito con que los mensajes llegan a las bandejas de entrada de los destinatarios, en lugar de filtrarse como correo no deseado o rechazarse. Adobe Campaign proporciona varias herramientas integradas para ayudarle a comprender y mejorar las tasas de colocación de la bandeja de entrada.

>[!NOTE]
>
>Un mensaje contabilizado como &quot;entregado&quot; significa que fue aceptado por el servidor receptor; no garantiza la colocación en la bandeja de entrada. La monitorización de la capacidad de entrega indica si la autenticación del dominio de envío, la reputación de la IP y el contenido del correo electrónico cumplen los estándares del proveedor de la bandeja de entrada.

Adobe Campaign proporciona las siguientes herramientas de envío integradas:

- **Informes de envío**: informes integrados que muestran el volumen de envío, las tasas de salida hacia otro sitio y las bajas de suscripción a lo largo del tiempo.
- **Procesamiento de la bandeja de entrada**: obtenga una vista previa de cómo aparece el correo electrónico en los principales clientes (Gmail, Outlook, Apple Mail) antes o después de enviarlo.
- **Prueba de SpamAssassin**: puntúe el contenido del correo electrónico con respecto a las reglas comunes de filtro de correo no deseado para detectar problemas antes de la entrega.
- **Estadísticas de difusión**: datos de envío agregados en sus volúmenes de envío y reputación de IP.

Las siguientes prácticas recomendadas sobre la capacidad de envío, como mantener una lista de correo electrónico limpia, monitorizar la reputación del remitente y autenticar los dominios de envío, son esenciales para mantener buenas tasas de envío.

Obtenga más información sobre las [herramientas de monitorización de capacidad de envío](../send/monitoring-deliverability.md) y las [prácticas recomendadas de capacidad de envío](../send/about-deliverability.md).

## Monitorización de flujos de trabajo {#monitor-workflows}

Los flujos de trabajo son el motor de las automatizaciones de marketing y del procesamiento de datos. Su monitorización garantiza que las actividades programadas se completen según lo esperado y que los errores se detecten antes de que afecten a las entregas o a la calidad de los datos.

>[!TIP]
>
>Si un flujo de trabajo muestra el estado **Failed**, ábralo, haga clic con el botón derecho en la actividad roja y seleccione **Display logs**. El mensaje de error identifica exactamente qué ha fallado y en qué registro.

### Funcionalidades de monitorización del flujo de trabajo {#workflow-monitoring}

**Supervisar los siguientes elementos de flujo de trabajo:**

**Estado de ejecución del flujo de trabajo**: efectúe el seguimiento de si los flujos de trabajo se están ejecutando, están en pausa, han fallado o se han completado. Vea los flujos de trabajo atascados o de larga duración de un vistazo. [Más información sobre la ejecución del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=es){target="_blank"}

**Registros de ejecución de actividad**: explore en profundidad los registros por actividad para comprender qué ha sucedido en cada paso. Resulta útil para solucionar problemas de transiciones fallidas o salidas de datos inesperadas.

**Mapa de calor del flujo de trabajo**: una descripción general visual de todos los flujos de trabajo que se ejecutan simultáneamente en la instancia. Utilícelo para identificar períodos de carga máxima, flujos de trabajo puntuales que consumen recursos desproporcionados y planificar la programación para evitar conflictos de ejecución. Disponible solo para administradores de Campaign. [Más información sobre el mapa de calor del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=es){target="_blank"}

**Historial del flujo de trabajo**: realice un seguimiento de todas las ejecuciones y modificaciones de flujos de trabajo a lo largo del tiempo para comprender el comportamiento del flujo de trabajo y los patrones de rendimiento.

## Monitorización de la instancia {#monitor-instance}

La monitorización de instancias cubre el estado del entorno de Campaign: capacidad de la base de datos, uso del perfil, rendimiento e infraestructura. En el caso de los servicios administrados en la nube de Campaign v8, Adobe supervisa y administra la infraestructura subyacente en su nombre, pero mantiene una visibilidad completa a través de la consola de cliente y el Panel de control de Campaign. Más información sobre la [supervisión administrada por Adobe](#adobe-cloud-monitoring).

### Pista de auditoría {#audit-trail}

La interfaz de autoservicio Pista de auditoría permite monitorizar todos los cambios significativos realizados en la instancia de Adobe Campaign. La pista de auditoría captura, en tiempo real, una lista completa de las acciones y eventos que se producen dentro de la instancia.

**Usar pista de auditoría para:**

- **Rastrear cambios de componentes**: supervise lo que ha sucedido a sus flujos de trabajo, esquemas, opciones y otros componentes
- **Identificar quién realizó un cambio** — Ver qué usuario modificó un elemento por última vez y a qué hora
- **Solucionar problemas de comportamiento inesperado**: realice un seguimiento de las acciones del usuario para averiguar cuándo y cómo se introdujo un problema
- **Cumplimiento de la asistencia y auditorías**: mantenga un registro completo y a prueba de manipulaciones de todos los cambios de configuración

Se puede acceder a la pista de auditoría a través de la consola del cliente de Campaign y proporciona información detallada sobre las acciones realizadas por los usuarios.

Más información sobre [Pista de auditoría](../reporting/audit-trail.md)

### Monitorización del rendimiento {#performance-monitoring}

La versión 8 de Campaign proporciona varias funciones de monitorización para rastrear el rendimiento de la instancia y garantizar un funcionamiento óptimo:

**Supervisión de bases de datos**: supervise el uso y la capacidad de las bases de datos mediante el Panel de control de Campaign para garantizar un rendimiento y una administración del almacenamiento óptimos. [Más información acerca de la supervisión de bases de datos](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html?lang=es){target="_blank"}

**Supervisión de perfiles activos**: realice un seguimiento del uso de perfiles activos en relación con los límites contractuales para mantener el cumplimiento y optimizar la asignación de recursos. [Más información sobre los perfiles activos](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=es){target="_blank"}

**Supervisión del flujo de trabajo**: supervise el estado de ejecución del flujo de trabajo para identificar los flujos de trabajo de larga duración y garantizar que todos los flujos de trabajo técnicos se ejecuten correctamente. [Más información sobre flujos de trabajo técnicos](#technical-workflows)

**Rendimiento y latencia de entrega** — Rastrea el rendimiento de entrega (mensajes enviados por hora) y la latencia para comunicaciones transaccionales a través del Panel de control de Campaign. [Más información sobre la supervisión del rendimiento](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html?lang=es){target="_blank"}

>[!NOTE]
>
>En Campaign v8 Managed Cloud Services, Adobe supervisa y administra la infraestructura del servidor (CPU, memoria, disco). Las funcionalidades de monitorización descritas en esta página y en Panel de control de Campaign son complementarias: le proporcionan visibilidad de sus datos y configuración sin necesidad de acceso a la infraestructura. Algunas acciones realizadas por Adobe aparecen en los registros de Campaign bajo el usuario **campaign-loginmonitor**. Más información sobre la [supervisión administrada por Adobe](#adobe-cloud-monitoring).

### Monitorización administrada por Adobe {#adobe-cloud-monitoring}

Adobe Campaign Cloud Services proporciona una asistencia esencial para las necesidades de entrega de las experiencias de los clientes más exigentes a través de una infraestructura de nube flexible. Esto permite a las organizaciones iniciar, monitorizar y optimizar las experiencias de los clientes sin administrar ni operar con la propia infraestructura de Campaign.

Adobe monitoriza los entornos de Cloud Services de Campaign las 24 horas del día, los 7 días de la semana para detectar problemas técnicos y minimizar las interrupciones. Al detectar un problema, el sistema utiliza mecanismos de reinicio automático e inicio automático para intentar la corrección. Si el sistema no se corrige automáticamente, el equipo de ingeniería de Adobe On-Call interviene en función de los runbooks de alertas predefinidos.

>[!TIP]
>
>Puede suscribirse a las alertas de instancias en tiempo real a través de [Panel de control de Campaign de Campaign](#control-panel) y recibir los pasos de corrección recomendados para los problemas detectados; por ejemplo, los certificados SSL están a punto de expirar.

**Niveles de supervisión**

Adobe supervisa su entorno en tres niveles. Los problemas de nivel 1 tienen el mayor impacto y reciben la respuesta más rápida:

| Nivel | Grupo | Qué puede experimentar |
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
>Adobe Campaign Cloud Services se basa en una estrategia de varias nubes con implementaciones en AWS y Azure. Las funcionalidades de supervisión difieren entre AWS, Azure y otras implementaciones de centros de datos. La tabla anterior se aplica a los clientes de Cloud Services de Campaign alojados en AWS a menos que se indique lo contrario. Actualmente, Adobe Campaign no expone a los clientes todos los datos de monitorización utilizados por el departamento de ingeniería On-Call.

### Flujos de trabajo técnicos {#technical-workflows}

Los flujos de trabajo técnicos se ejecutan silenciosamente en segundo plano para mantener la instancia de Campaign. No los crean los usuarios, sino que se envían con el producto. Si un flujo de trabajo técnico falla, puede afectar directamente a las entregas y a la calidad de los datos.

Compruebe que cada flujo de trabajo técnico se ejecuta según lo programado, se completa sin errores y procesa los datos correctamente.

| Flujo de trabajo | Objetivo | Si falla |
| --- | --- | --- |
| **Seguimiento** | Procesa los datos de seguimiento de las entregas de correo electrónico | Las métricas de clic y apertura dejan de actualizarse en los informes |
| **Limpieza** | Quita los datos y registros antiguos para mantener el rendimiento de la base de datos | El crecimiento de la base de datos es descontrolado, lo que degrada el rendimiento de consultas y entregas |
| **Actualización de la capacidad de envío** | Actualiza las reglas de envío y los patrones de filtro de spam | Las reglas se quedan obsoletas; la precisión del filtrado puede degradarse |
| **Limpieza de base de datos** | Purga los registros de envío y seguimiento antiguos | La acumulación de registros ralentiza las consultas y los informes con el tiempo |

Más información sobre [flujos de trabajo técnicos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=es){target="_blank"}

### Panel de control de Campaign {#control-panel}

El Panel de control de Campaign de trabajo de Campaign proporciona a los administradores funciones de autoservicio para monitorizar y administrar instancias de Campaign, sin necesidad de un ticket de asistencia.

| Tipo de monitorización | Funcionalidades |
| --- | --- |
| **Rendimiento** | Uso de perfil activo frente a límite de contrato, uso y capacidad de la base de datos, estado de ejecución del flujo de trabajo, rendimiento del envío y latencia |
| **Infraestructura** | Capacidad de almacenamiento SFTP, configuración de subdominios, alertas de caducidad de certificados SSL, lista de IP permitidas |
| **Instancia** | Versión de compilación y paquetes instalados, información general sobre la configuración del sistema, dominios externos autorizados |

Obtenga más información sobre [Panel de control de Campaign](../config/self-service.md) y [supervisión del rendimiento del Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=es){target="_blank"}

>[!NOTE]
>
>En Campaign v8 Managed Cloud Services, Adobe supervisa y administra la infraestructura del servidor, el sistema operativo y la capa de aplicaciones. Las funcionalidades de monitorización que se describen en esta página y en el Panel de control de Campaign son complementarias: le proporcionan visibilidad de los datos y la configuración sin necesidad de acceder a la infraestructura.

## Seguimiento y creación de informes {#tracking-reporting}

### Seguimiento de mensajes {#message-tracking}

El seguimiento registra cómo interactúan los destinatarios con los mensajes después de la entrega. Todos los eventos rastreados se almacenan en registros de seguimiento y aparecen en informes de envío.

- **Aperturas** — Se registra cuando se carga el píxel de seguimiento (solo correo electrónico)
- **Clics**: registrados para cada vínculo rastreado en el mensaje
- **Cancela la suscripción** — Solicitudes de exclusión a través del vínculo de cancelación de suscripción
- **Vistas de página espejo**: Destinatarios que vieron el correo electrónico en un explorador

Más información sobre [seguimiento de mensajes](../send/tracking.md)

### Informes de envío {#delivery-reports}

Adobe Campaign proporciona un completo conjunto de informes para analizar el rendimiento de su entrega:

- **Resumen de envío**: información general sobre envíos, envíos y errores de un solo envío
- **Indicadores de seguimiento**: abre, hace clic y tasa de pulsaciones con una tendencia en el tiempo
- **URL y flujos de clics**: clasificación de los vínculos en los que se hizo clic más, con recuentos y porcentajes.
- **Clics activos**: superposición visual que muestra dónde hicieron clic los destinatarios dentro del cuerpo del correo electrónico

Más información sobre [informes de envío](../reporting/delivery-reports.md)

### Informes globales {#global-reports}

Acceda a informes globales para analizar el rendimiento de todas las campañas y envíos:

- **Rendimiento de entrega**: mensajes enviados por hora en todas las entregas durante un periodo
- **Rechazos y no entregables**: desglose de los envíos fallidos por tipo y motivo de error
- **Actividades de usuario**: abre, hace clic y cancela la suscripción acumuladas en todas las campañas

Más información sobre [informes globales](../reporting/global-reports.md)

## Temas relacionados {#related-topics}

- [Prácticas recomendadas para envíos](delivery-best-practices.md)
- [Administración de cuarentena](../send/quarantines.md)
- [Configuración y envío de entregas](../send/configure-and-send.md)
- [Introducción a la creación de informes](../reporting/gs-reporting.md)
