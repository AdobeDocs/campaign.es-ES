---
title: Información general de monitorización de Campaign
description: Obtenga información sobre cómo monitorizar entregas, flujos de trabajo y la instancia de Campaign
feature: Monitoring
role: User
level: Beginner
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 3%

---

# Información general de monitorización de Campaign {#monitor-campaign}

Adobe Campaign ofrece un conjunto completo de funciones para monitorizar los procesos, las entregas y el entorno a fin de garantizar un rendimiento óptimo y solucionar problemas de forma proactiva.

>[!NOTE]
>
>Como administrador de Campaign, también puede usar [Panel de control de Campaign de Campaign](#control-panel) para supervisar las instancias, administrar el rendimiento y configurar opciones con capacidades de autoservicio.

## Monitorización de entregas {#monitor-deliveries}

La monitorización de las entregas una vez enviadas es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes. Después de realizar una entrega, puede monitorizar su estado y rastrear las métricas clave en el panel de entrega. El panel proporciona acceso a los registros de envío, los registros de exclusión, los registros de seguimiento y otras funcionalidades de monitorización para ayudarle a analizar el rendimiento de su envío en todos los canales.

**Envíos de correo electrónico**: supervise el estado de envío de los correos electrónicos, realice un seguimiento de las métricas clave y acceda a los registros detallados. Obtenga más información sobre [supervisión de entregas en la interfaz de usuario de Campaign](../send/delivery-dashboard.md), [estados de entrega](../send/delivery-statuses.md) y [supervisión de entregas por correo electrónico](../send/send.md#email-monitoring).

**Envíos de SMS**: rastree el estado de envío de SMS y supervise las métricas clave en el panel de envío de SMS. Más información sobre la [supervisión de SMS](../send/sms/sms-monitor.md).

**Notificaciones push**: supervise las entregas de notificaciones push para garantizar que lleguen a los usuarios de su aplicación móvil de forma eficaz. Más información sobre la [supervisión de notificaciones push](../send/push.md#push-test).

**Mensajes transaccionales**: para los mensajes activados por eventos, supervise el estado de procesamiento de eventos, la ejecución de mensajes y el estado de envío. Más información sobre la [supervisión de mensajes transaccionales](../send/delivery-execution.md#monitor-messages).

**Errores de entrega**: comprender por qué falló una entrega es fundamental para mantener una base de datos limpia y garantizar buenas tasas de entrega. Los errores de entrega se clasifican en rechazos graves, rechazos leves y mensajes ignorados. Más información sobre [errores y cuarentenas de entregas](../send/delivery-failures.md).

## Monitorización de la capacidad de entrega {#monitor-deliverability}

La monitorización de la capacidad de entrega le ayuda a garantizar que los mensajes lleguen a las bandejas de entrada de los destinatarios y evitar filtros de correo no deseado. Adobe Campaign proporciona varias herramientas integradas para monitorizar y mejorar la capacidad de entrega, incluidos informes de entrega, procesamiento de la bandeja de entrada, pruebas de SpamAssassin y estadísticas de difusión. Seguir las prácticas recomendadas de envío, como mantener una lista de correo electrónico limpia, monitorizar la reputación del remitente y autenticar los dominios de envío es fundamental para mantener buenas tasas de envío.

Obtenga más información sobre las [herramientas de monitorización de capacidad de envío](../send/monitoring-deliverability.md) y las [prácticas recomendadas de capacidad de envío](../send/about-deliverability.md).

## Monitorización de flujos de trabajo {#monitor-workflows}

Los flujos de trabajo son esenciales para automatizar las campañas de marketing y el procesamiento de datos. La monitorización de la ejecución del flujo de trabajo le ayuda:

* Garantizar que los flujos de trabajo se completen correctamente
* Identificar y solucionar errores
* Optimización del rendimiento del flujo de trabajo

### Funcionalidades de monitorización del flujo de trabajo {#workflow-monitoring}

**Supervisar los siguientes elementos de flujo de trabajo:**

**Estado de ejecución del flujo de trabajo**: efectúe el seguimiento de si los flujos de trabajo se están ejecutando, están en pausa, han fallado o se han completado. [Más información sobre la ejecución del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=es){target="_blank"}

**Registros de ejecución de actividades**: acceda a los registros detallados de cada actividad de flujo de trabajo para solucionar problemas y optimizar el rendimiento.

**Mapa de calor del flujo de trabajo**: visualice los patrones de ejecución del flujo de trabajo, identifique los cuellos de botella y supervise los flujos de trabajo simultáneos. El mapa de calor del flujo de trabajo está disponible para los administradores de Campaign. [Más información sobre el mapa de calor del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=es){target="_blank"}

**Historial del flujo de trabajo**: haga un seguimiento de todas las ejecuciones y modificaciones del flujo de trabajo a lo largo del tiempo para comprender el comportamiento y el rendimiento del flujo de trabajo.

## Monitorización de la instancia {#monitor-instance}

La monitorización de instancias ayuda a garantizar el estado y el rendimiento de su entorno de Adobe Campaign.

### Pista de auditoría {#audit-trail}

La interfaz de autoservicio Pista de auditoría permite monitorizar los cambios realizados en la instancia de Adobe Campaign. La pista de auditoría captura, en tiempo real, una lista completa de las acciones y eventos que se producen dentro de la instancia.

**Usar pista de auditoría para:**

* **Rastrear cambios de componentes**: supervise lo que ha sucedido a sus flujos de trabajo, esquemas, opciones y otros componentes
* **Identificar quién hizo cambios**: Ver quién actualizó por última vez un elemento específico y cuándo
* **Comprender las acciones del usuario**: revise lo que los usuarios hicieron en la instancia para solucionar problemas o auditar
* **Mantener el cumplimiento**: haga un seguimiento de todos los cambios de configuración por motivos de cumplimiento y seguridad

Se puede acceder a la pista de auditoría a través de la consola del cliente de Campaign y proporciona información detallada sobre las acciones realizadas por los usuarios.

Más información sobre [Pista de auditoría](../reporting/audit-trail.md)

### Monitorización del rendimiento {#performance-monitoring}

La versión 8 de Campaign proporciona varias funciones de monitorización para rastrear el rendimiento de la instancia y garantizar un funcionamiento óptimo:

**Supervisión de bases de datos**: supervise el uso y la capacidad de las bases de datos mediante el Panel de control de Campaign para garantizar un rendimiento y una administración del almacenamiento óptimos. [Más información acerca de la supervisión de bases de datos](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html?lang=es){target="_blank"}

**Supervisión de perfiles activos**: realice un seguimiento del uso de perfiles activos en relación con los límites contractuales para mantener el cumplimiento y optimizar la asignación de recursos. [Más información sobre los perfiles activos](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=es){target="_blank"}

**Supervisión del flujo de trabajo**: supervise el estado de ejecución del flujo de trabajo para identificar flujos de trabajo de larga duración y garantizar que todos los flujos de trabajo técnicos se ejecuten correctamente. [Más información sobre flujos de trabajo técnicos](#technical-workflows)

**Rendimiento y latencia de entrega** - Rastree el rendimiento de entrega (mensajes enviados por hora) y la latencia para comunicaciones transaccionales a través del Panel de control de Campaign. [Más información sobre la supervisión del rendimiento](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html?lang=es){target="_blank"}

>[!NOTE]
>
>En Campaign v8 Managed Cloud Services, Adobe supervisa y administra la infraestructura del servidor (CPU, memoria, disco).

### Flujos de trabajo técnicos {#technical-workflows}

Los flujos de trabajo técnicos son procesos esenciales que se ejecutan en segundo plano para mantener la instancia de Campaign.

**Supervisar que los flujos de trabajo técnicos son:**

* Ejecución según lo programado
* Finalización correcta sin errores
* Procesamiento correcto de los datos

**Flujos de trabajo técnicos clave que supervisar:**

| Flujo de trabajo | Objetivo |
|----------|---------|
| **Seguimiento** | Procesa los datos de seguimiento de las entregas de correo electrónico |
| **Limpieza** | Quita los datos y registros antiguos para mantener el rendimiento de la base de datos |
| **Actualización de la capacidad de envío** | Actualiza las reglas de envío y los patrones de filtro de spam |
| **Limpieza de base de datos** | Purga los registros de envío y seguimiento antiguos |

Más información sobre [flujos de trabajo técnicos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=es){target="_blank"}

### Panel de control de Campaign {#control-panel}

El Panel de control de Campaign de trabajo de Campaign proporciona a los administradores funciones de autoservicio para monitorizar y administrar instancias de Campaign.

| Tipo de supervisión | Funcionalidades |
|-----------------|--------------|
| **Rendimiento** | Rastree el uso activo del perfil, monitorice el uso y la capacidad de la base de datos, vea el estado de ejecución del flujo de trabajo, monitorice el rendimiento de entrega y la latencia |
| **Infraestructura** | Monitorización de la capacidad de almacenamiento SFTP, seguimiento de la configuración de subdominios, monitorización de la caducidad del certificado SSL, administración de la lista de IP permitidas |
| **Instancia** | Ver la versión de compilación y los paquetes instalados, supervisar la configuración del sistema y administrar los dominios externos autorizados |

Obtenga más información sobre [Panel de control de Campaign](../config/self-service.md) y [supervisión del rendimiento del Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=es){target="_blank"}

>[!NOTE]
>
>En Campaign v8 Managed Cloud Services, Adobe supervisa y administra la infraestructura del servidor, el sistema operativo y la capa de aplicaciones. Puede utilizar las funcionalidades de monitorización descritas en esta página y Panel de control de Campaign para monitorizar el rendimiento de las instancias, los flujos de trabajo y los envíos.

## Seguimiento y creación de informes {#tracking-reporting}

### Seguimiento de mensajes {#message-tracking}

Realice un seguimiento del comportamiento de los destinatarios y mida la eficacia de sus campañas:

* **Aperturas**: Rastrea cuándo los destinatarios abren tus correos electrónicos
* **Clics**: Supervise qué vínculos hacen clic los destinatarios
* **Cancelaciones de suscripción**: Rastrear solicitudes de exclusión
* **Vistas de página espejo**: Ver cuántos destinatarios ven el correo electrónico en un explorador

Más información sobre [seguimiento de mensajes](../send/tracking.md)

### Informes de envío {#delivery-reports}

Adobe Campaign proporciona un completo conjunto de informes para analizar el rendimiento de su entrega:

* **Resumen de envíos**: Información general sobre envíos, envíos y errores
* **Indicadores de seguimiento**: Aperturas, clics y tasas de pulsaciones
* **URL y flujos de clics**: Vínculos más populares en las entregas
* **Clics activos**: representación visual de dónde hicieron clic los destinatarios en el correo electrónico

Más información sobre [informes de envío](../reporting/delivery-reports.md)

### Informes globales {#global-reports}

Acceda a informes globales para analizar el rendimiento de todas las campañas y envíos:

* **Rendimiento de entrega**: mensajes enviados a lo largo del tiempo
* **Rechazos y no entregables**: análisis de los envíos fallidos
* **Actividades de usuario**: Abre, hace clic y cancela la suscripción en todas las campañas

Más información sobre [informes globales](../reporting/global-reports.md)

## Temas relacionados {#related-topics}

* [Prácticas recomendadas para envíos](delivery-best-practices.md)
* [Administración de cuarentena](../send/quarantines.md)
* [Configuración y envío de entregas](../send/configure-and-send.md)
* [Introducción a la creación de informes](../reporting/gs-reporting.md)

