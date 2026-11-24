---
title: Opciones de Campaign
description: Descubra cuáles son las opciones de Campaign, dónde se almacenan y cómo utilizar las opciones documentadas para Campaign v8
feature: Architecture
role: Admin, Developer
level: Intermediate
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 92bab89570eca3eb13d6010db0deec74e7860c91
workflow-type: tm+mt
source-wordcount: '2849'
ht-degree: 3%
---
# Opciones de Campaign {#campaign-options}

Las opciones son parámetros que controlan el comportamiento de la instancia de Campaign, por ejemplo el límite de tamaño predeterminado de las imágenes en los correos electrónicos, el número de flujos de trabajo que se ejecutan al mismo tiempo o el proveedor de enrutamiento predeterminado de las plantillas de envío. Algunas opciones están integradas y otras se crean cuando es necesario. Las opciones disponibles dependen de los paquetes instalados en la instancia. Obtenga más información en [Paquetes integrados](built-in-packages.md).

>[!CAUTION]
>
>Modifique solo las opciones documentadas en la documentación de Campaign y solo como se describe. Las opciones que no están documentadas son internas y no deben modificarse. La modificación de opciones está reservada para usuarios expertos.

## Dónde se almacenan las opciones {#where-options-are-stored}

Las opciones se almacenan en la base de datos de Campaign, en la tabla **xtkOption** (esquema **xtk:option**). En Campaign Explorer, están disponibles en **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**. En la interfaz de usuario web de Campaign, están disponibles en **[!UICONTROL Administration]** > **[!UICONTROL Options]**. Ambas listas son idénticas. Obtenga más información en [Configurar opciones de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options){target="_blank"}.

## Usar opciones {#use-options}

1. En el explorador de Campaign, vaya a **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**.
1. Seleccione la opción y, a continuación, actualice su valor. Si la opción no existe, créela con el nombre exacto que aparece en la documentación.
1. Establezca un valor del tipo que espera la documentación. Por ejemplo, una opción de texto para la fecha de sincronización de CRM o una opción entera para la demora de reinicio del flujo de trabajo.

También puede crear sus propias opciones, por ejemplo, para almacenar datos intermedios de un flujo de trabajo. Introduzca un nombre, seleccione el tipo de datos y defina el valor. Obtenga más información en [Configurar opciones de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#create){target="_blank"}.

Algunas opciones contienen credenciales. Cifrar secretos con la función `cryptString`, tal como se describe en [Trabajar con páginas de aterrizaje de Campaign y Adobe Experience Platform](../connect/ac-aep-landing-pages.md). Al rotar las credenciales, rote también las almacenadas en las opciones. Obtenga más información en la [guía de rotación de credenciales](../../technotes/security/credential-rotation-guide.md#ac-options-credentials).

## Uso de opciones en flujos de trabajo y personalización {#use-options-in-processes}

Puede leer y escribir valores de opción a partir del código JavaScript, la personalización y las consultas.

* **JavaScript code**, como una actividad de flujo de trabajo de JavaScript code: `getOption('OptionName')` devuelve el valor de una opción y `setOption('OptionName', value, 'description')` la establece. Por ejemplo, `getOption('IMS_ORG_ID')`. Obtenga más información en [getOption](../../campaign-api/f-getoption.md) y [setOption](../../campaign-api/f-setoption.md).
* **Personalización de envío**: `<%@ include option='OptionName' %>` inserta el valor de una opción. Por ejemplo, `<%@ include option='NmsServer_URL' %>` incluye la dirección URL del servidor en un vínculo a una aplicación web en un mensaje de LINE. Más información en [Enviar mensajes directos de LINE con Adobe Campaign](../send/line/line.md).
* **Editor de consultas**: escriba `$(options:OPTION_NAME)` en el campo **Valor** para usar el valor de una opción. Obtenga más información en [Consultas de diseño](../start/design-queries.md).

## Opciones disponibles {#available-options}

Las siguientes tablas enumeran las opciones disponibles en Campaign v8, agrupadas por área. Cuando otra página de la documentación describe una opción, la tabla se vincula a ella. Algunas entradas son opciones informativas o de mantenimiento. Incluir una opción en la lista no significa que sea seguro cambiarla.

### Envíos {#delivery-options}

Estas opciones controlan cómo se preparan y envían los envíos. Cubren los límites de imágenes y archivos adjuntos, el proveedor de enrutamiento predeterminado, el umbral dividido intermediario, el script de seguimiento abierto, la URL del servidor público, la validez del envío, el manejo de duplicados y envíos retrasados, y los códigos de barras. Obtenga más información en [Adjuntar archivos](../send/attaching-files.md), [Parámetros de correo electrónico](../send/email-parameters.md), [Prácticas recomendadas de entrega](../start/delivery-best-practices.md), [Introducción a la arquitectura de Campaign](architecture.md#split), [Directrices sobre los píxeles de seguimiento de correo electrónico](../start/cnil-pixel-tracking.md) y [Enviar mensajes de LINE directo](../send/line/line.md).

| Opción | Descripción |
|---|---|
| NmsDelivery_MaxDownloadedImageSize | Tamaño máximo, en bytes, de una imagen descargada de una dirección URL personalizada y adjunta a un correo electrónico. El valor predeterminado es 100.000 bytes (100 KB). [Más información](../send/attaching-files.md) |
| NmsDelivery_MaxRecommendationsAttachments | Número máximo de archivos adjuntos en un correo electrónico o plantilla de correo electrónico transaccional antes de mostrar una advertencia. El valor predeterminado es 1. [Más información](../send/attaching-files.md) |
| NmsEmail_DefaultErrorAddress | Dirección de correo electrónico de error predeterminada de la instancia, utilizada cuando el envío deja vacía la dirección de error. [Más información](../send/email-parameters.md) |
| XtkEmail_Characters | Caracteres válidos para una dirección de correo electrónico. [Más información](../start/delivery-best-practices.md) |
| NmsBroadcast_DefaultProvider | Proveedor de enrutamiento predeterminado de las nuevas plantillas de envío. Configúrelo con el nombre de una cuenta externa dividida para utilizar la entrega dividida de forma predeterminada. [Más información](architecture.md#split) |
| NmsDelivery_MultiMidSplitThreshold | Tamaño desde el cual se divide un envío entre varias instancias intermediarias. El valor predeterminado es 100K. [Más información](architecture.md#split) |
| NmsTracking_OpenFormula | Script que calcula la dirección URL de seguimiento abierta. Defina una opción por cada propósito de píxel. [Más información](../start/cnil-pixel-tracking.md) |
| NmsServer_URL | URL base del servidor público de aplicaciones web. Se utiliza, por ejemplo, para incluir un vínculo de aplicación web en un mensaje de LINE. [Más información](../send/line/line.md) |
| NmsBroadcast_MsgValidityDuration | Período de validez predeterminado de un envío, en segundos. |
| NmsBroadcast_RemoveDuplicatesRecipients | Configúrelo en 1 para ignorar automáticamente los destinatarios duplicados. |
| NmsDelivery_ImageServerTimeout | Tiempo de espera, en segundos, para obtener una respuesta del servidor al recuperar una imagen descargada de una URL personalizada y adjunta a un correo electrónico. Si se supera el tiempo de espera, no se puede enviar el mensaje. El valor predeterminado es 60 segundos. |
| NmsDeliveryWizard_ShowDeliveryWeight | Muestra el peso del mensaje en el asistente de envíos. |
| NmsMTA_Alert_Delay | Retraso, en minutos, tras el cual un envío se considera retrasado. El valor predeterminado es 30 minutos. |
| NmsServer_MirrorPageUrl | URL del servidor de página espejo. Es el valor predeterminado de los envíos por correo electrónico cuando la definición de enrutamiento no especifica una dirección URL. De forma predeterminada, es idéntica a la URL del servidor de seguimiento. |
| XtkBarcode_SpecialChar | Habilita o deshabilita la compatibilidad de caracteres especiales para códigos de barras Code128. |
| NMS_ActivateOwnerConfirmation | Configúrelo en 1 para que el operador a cargo de la entrega pueda confirmar la entrega, cuando se designe un operador o grupo específico para iniciar la entrega. Configúrelo en 0 para desactivarlo: solo el operador o grupo designado, o un administrador, pueden confirmar el envío. |
| NmsDelivery_senderAddressMask | Lista separada por comas de las direcciones de remitente permitidas en el campo De correo electrónico de las entregas de correo electrónico. Cuando la opción tiene un valor, el campo se convierte en una lista desplegable. La restricción es global: se aplica a cada marca y plantilla de envíos y solo admite direcciones estáticas. [Más información](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#restrict-sender-address){target="_blank"} |

### Campañas y flujos de trabajo {#campaign-workflow-options}

Estas opciones controlan cómo se ejecutan las campañas y los flujos de trabajo. Cubren la confirmación del propietario de un envío, el número de trabajos procesados al mismo tiempo y la comprobación y el reinicio automático de los flujos de trabajo. También cubren la protección de las actividades SQL, la validez de campaña predeterminada y el logotipo de los informes exportados. Obtenga más información en [Envíos de campañas de marketing](../../automation/campaigns/marketing-campaign-deliveries.md), [Prácticas recomendadas de flujo de trabajo](../../automation/workflow/workflow-best-practices.md), [Supervisar la ejecución del flujo de trabajo](../../automation/workflow/monitor-workflow-execution.md), [Propiedades del flujo de trabajo](../../automation/workflow/workflow-properties.md), y [Código SQL y Código JavaScript](../../automation/workflow/sql-code-and-javascript-code.md#important-notes).

| Opción | Descripción |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | Créelo y configúrelo en 1 para que el propietario de la campaña pueda confirmar el envío, incluso si se han definido revisores. Configúrelo en 0 para desactivarlo. [Más información](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | Número máximo de trabajos de entrega, flujo de trabajo, hipótesis y simulación que procesa una campaña al mismo tiempo. El valor predeterminado es 10. [Más información](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | Número de días entre dos comprobaciones para flujos de trabajo en pausa. [Más información](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | Créela como una opción entera para cambiar el intervalo de 30 segundos en el que se comprueban y se reinician automáticamente los flujos de trabajo. [Más información](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | Configúrelo en 0 para desactivar la protección de las actividades de código SQL contra los métodos SQL bloqueados. [Más información](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | Lista de métodos SQL sobre los que las actividades SQL bloquean o advierten. [Más información](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| NmsOperation_Duration | Período de validez predeterminado de una campaña, en segundos. |
| NmsOperation_TimeRange | Período de tiempo para las condiciones de segmentación y extracción en el modo programado. |
| NmsOperation_OperationMgtDebug | Configúrelo en 1 para registrar la información de ejecución del flujo de trabajo técnico operationMgt en los registros de auditoría del flujo de trabajo. |
| NmsOperation_DeliveryPreparationWindow | Número de días por encima de los cuales los envíos con un estado incoherente se excluyen del recuento de envíos en ejecución mediante el flujo de trabajo técnico de operationMgt. El valor predeterminado es 7. |
| Workflow_AnalysisThreshold | Número de registros afectados tras los cuales las estadísticas de tabla se vuelven a calcular automáticamente. |
| XtkReport_Logo | El logotipo se muestra en la esquina superior derecha de los informes exportados. |

### Valores predeterminados de correo electrónico {#email-default-options}

Estas opciones definen las direcciones de remitente y respuesta predeterminadas y las etiquetas de los correos electrónicos. Campaign los utiliza cuando una entrega deja vacío el campo correspondiente. Obtenga más información en [Parámetros de correo electrónico](../send/email-parameters.md) y [Trabajo con plantillas de envíos](../send/create-templates.md).

| Opción | Descripción |
|---|---|
| NmsEmail_DefaultFromAddress | Dirección De predeterminada de la instancia, que se utiliza cuando el envío deja vacío. |
| NmsEmail_FromName | Etiqueta From predeterminada de la instancia, que se utiliza cuando el envío la deja vacía. |
| NmsEmail_DefaultReplyToAddress | Dirección de respuesta predeterminada de la instancia, que se utiliza cuando el envío deja vacío. |
| NmsEmail_ReplyToName | Etiqueta de respuesta predeterminada de la instancia, que se utiliza cuando el envío la deja vacía. |
| NmsEmail_DefaultErrorAddress | Dirección de error predeterminada de la instancia, que se utiliza cuando el envío deja vacío. [Más información](../send/email-parameters.md) |
| NmsDelivery_FromAddressMask | Sintaxis de la dirección remitente utilizada al enviar un mensaje. |
| NmsDelivery_ErrorAddressMask | Sintaxis de la dirección de error utilizada al responder a un mensaje. |
| NmsEmail_ExpOrganization | Nombre común de su organización, utilizado en algunos mensajes de advertencia mostrados a los destinatarios. |

### Errores leves y cuarentena {#error-options}

Estas opciones definen cuándo se pone en cuarentena un destinatario después de errores leves, que son errores de entrega temporales. Obtenga más información en [Administración de cuarentena en Campaign](../send/quarantines.md#soft-error-management) y [Errores de entrega en Campaign](../send/delivery-failures.md#retries).

| Opción | Descripción |
|---|---|
| NmsNPAI_EmailMaxError | Número máximo de errores leves aceptados en el canal de correo electrónico antes de que el destinatario se ponga en cuarentena. |
| NmsNPAI_EmailSignificantErrorDelay | Tiempo mínimo que debe transcurrir después del error leve anterior en el canal de correo electrónico antes de que se tenga en cuenta un nuevo error leve. |
| NmsNPAI_MobileMaxError | Número máximo de errores leves aceptados en el canal móvil antes de que el destinatario se ponga en cuarentena. |
| NmsNPAI_MobileSignificantErrorDelay | Tiempo mínimo que debe transcurrir después del error leve anterior en el canal móvil antes de que se tenga en cuenta un nuevo error leve. |

### Canales {#channel-options}

Estas opciones definen la dirección del remitente del correo postal, la configuración de los canales LINE y SMS y las direcciones de reenvío permitidas del correo electrónico entrante. Más información en [Envío de correos directos con Adobe Campaign](../send/direct-mail.md), [Envío de mensajes directos de LINE con Adobe Campaign](../send/line/line.md) y [Envío de SMS con Adobe Campaign](../send/sms/sms.md).

| Opción | Descripción |
|---|---|
| NmsPaper_SenderLine1, NmsPaper_SenderLine3, NmsPaper_SenderLine4, NmsPaper_SenderLine6, NmsPaper_SenderLine7 | Líneas 1, 3, 4, 6 y 7 de la dirección del remitente de las entregas de correo postal. |
| NmsLine_AESKey | Clave AES utilizada por el servlet lineImage para codificar direcciones URL en el canal LINE. |
| NmsLine_MessageCenterURL | URL del servidor del Centro de mensajes utilizada para enviar mensajes de bienvenida en el canal LINE. |
| NmsSMS_Priority | Prioridad de los mensajes SMS enviados, transmitidos a la puerta de enlace de SMS. |
| NmsInmail_AllowlistEmails | Direcciones de correo electrónico de reenvío autorizado del módulo de procesamiento de correo entrante, separadas por comas. Utilice * para permitir todas las direcciones. |

### Umbrales del centro de mensajes {#message-center-options}

Estas opciones definen los umbrales que generan una advertencia o una alerta cuando se degrada el procesamiento de eventos en tiempo real, que almacenan en déclencheur los mensajes transaccionales. Cada métrica tiene un umbral de advertencia y un umbral de alerta. El nombre de la opción termina con Warning o Alert, por ejemplo MC_RtEventErrorWarning y MC_RtEventErrorAlert. Obtenga más información en [Mensajería transaccional de Campaign](../send/transactional.md) y [Configuración de mensajería transaccional de Campaign](../config/transactional-msg-settings.md).

| Prefijo de nombre de opción | Métrica |
|---|---|
| MC_RtEventAvgDeliveryTime | Tiempo medio de envío de eventos en tiempo real. |
| MC_RtEventAvgProcessTime | Tiempo medio de procesamiento de los eventos en tiempo real. |
| MC_RtEventAvgQueueTime | Tiempo medio de cola de los eventos en tiempo real. |
| MC_RtEventAvgQueue | Promedio de eventos en tiempo real en cola. |
| MC_RtEventMaxQueue | Número máximo de eventos en tiempo real en cola. |
| MC_RtEventMinQueue | Número mínimo de eventos en tiempo real en cola. |
| MC_RtEventQueue | Cola de eventos en tiempo real pendientes. El umbral de alerta es la condición crítica. |
| MC_RtEventError | Procesamiento de errores de eventos en tiempo real. |
| MC_RtEventThroughput | Rendimiento de los eventos en tiempo real. |

### Retención de datos y base de datos {#database-options}

El flujo de trabajo de limpieza purga los registros antiguos para evitar que la base de datos crezca. Estas opciones definen cuánto tiempo mantiene Campaign cada tipo de datos. Se crea automáticamente una opción de retraso de depuración al cambiar el retraso en la interfaz. Si lo edita desde la lista de opciones, exprese el valor en segundos. Obtenga más información en [Arquitectura general](general-architecture.md) y [Directrices de seguridad](../config/security.md#consent).

Solo los administradores pueden modificar las opciones de retraso de depuración. Los valores adecuados dependen del entorno, por lo que compruebe el valor actual de la instancia y no asuma un valor predeterminado universal.

| Opción | Descripción |
|---|---|
| NmsCleanup_BroadLogPurgeDelay | Retraso tras el cual se borran los registros de envío (broadlogs). |
| NmsCleanup_TrackingLogPurgeDelay | Retraso tras el cual se borran los registros de seguimiento. |
| NmsCleanup_TrackingStatPurgeDelay | Retraso tras el cual se borran las estadísticas de seguimiento. |
| NmsCleanup_EventPurgeDelay | Retraso tras el cual se borran los eventos. |
| NmsCleanup_EventHistoPurgeDelay | Retraso tras el cual se borra el historial de eventos. |
| NmsCleanup_EventStatPurgeDelay | Retraso tras el cual se borran las estadísticas de eventos. |
| NmsCleanup_PropositionPurgeDelay | Retraso tras el cual se borran las propuestas. |
| NmsCleanup_QuarantineMailboxFull | Retraso tras el cual se borran las cuarentenas. |
| NmsCleanup_RecycledDeliveryPurgeDelay | Retraso tras el cual se borran los envíos reciclados. |
| NmsCleanup_RejectsPurgeDelay | Retraso tras el cual se borran los rechazos. |
| NmsCleanup_VisitorPurgeDelay | Retraso tras el cual se borran los visitantes. |
| NmsCleanup_WorkflowResultPurgeDelay | Retraso tras el cual se borran los resultados del flujo de trabajo. |
| WdbcKillSessionPolicy | Comportamiento de la detención incondicional de flujos de trabajo en PostgreSQL. 0 (predeterminado): detiene el proceso de flujo de trabajo sin afectar a la base de datos. 1: detiene el proceso y cancela la consulta (pg_cancel_backend). 2: detiene el proceso y finaliza la consulta (pg_terminate_backend). |
| XtkSequence_AutoGeneration | Se aplica a los esquemas personalizados creados después de establecer esta opción, con autopk=&quot;true&quot; y sin atributo pkSequence: Campaign genera la secuencia automáticamente. |

### Personalización del centro de mensajes {#message-center-customization}

Estas opciones permiten personalizar la forma en que Campaign enriquece y enruta los eventos en tiempo real y por lotes. Obtenga más información en [Mensajería transaccional de Campaign](../send/transactional.md) y [Configuración de mensajería transaccional de Campaign](../config/transactional-msg-settings.md).

| Opción | Descripción |
|---|---|
| MC_EnrichmentCustomJs | Biblioteca de JavaScript que enriquece los eventos. Debe implementar enrichRtEvents(aiEventId) para eventos en tiempo real y enrichBatchEvents(aiEventId) para eventos por lotes. Ambas funciones enriquecen los eventos y los guardan en la base de datos. |
| MC_RoutingCustomJs | Biblioteca de JavaScript que enruta eventos. Debe implementar RtEvent(iEventId) y patchBatchEvent(iEventId), que devuelven el nombre interno del mensaje transaccional seleccionado para el evento de lote o en tiempo real. |
| NmsMessageCenter_RoutingBatchSize | Tamaño de los grupos utilizados para el enrutamiento de eventos. |
| NmsTracking_RT_ClickFormula, NmsTracking_RT_OpenFormula | Fórmulas utilizadas para el rastreo de clics y aperturas de envíos en tiempo real (RT) cuando se activa la marca. Se configuran en la instancia de control RT. [Más información](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |
| Branding_RT_ListXtkOptions_toPublish | Lista de las opciones, separadas por comas, que contienen las fórmulas de seguimiento personalizadas, para que los envíos de RT puedan aplicarlas. [Más información](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |

### Interacción (gestión de ofertas) {#interaction-options}

Estas opciones se aplican a Campaign Interaction, el módulo de administración de ofertas. Controlan cómo se escriben las propuestas y cómo se sincronizan las instancias de control y ejecución. Obtenga más información en [Interacción de campaña - Administración de ofertas](../interaction/interaction.md) y en las [opciones de mantenimiento](../interaction/interaction-architecture.md#maintenance-options) de la arquitectura de interacción.

| Opción | Descripción |
|---|---|
| NmsInteraction_UseDaemon | Configúrelo en 1 para habilitar la escritura asincrónica de propuestas o en 0 para deshabilitarlo. |
| NmsInteraction_MapWorkflowId | Lista de todos los flujos de trabajo de sincronización generados. Opción de mantenimiento informativo de la instancia de control: no la modifique. |
| NmsExecutionInstanceId | Identificador de la instancia de ejecución. Opción informativa disponible en instancias de ejecución: no la modifique. |

Las siguientes opciones también son opciones de mantenimiento de la instancia de control:

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: última fecha en la que se sincronizó un entorno en una instancia determinada.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: última fecha en la que se sincronizaron las propuestas de un esquema de una instancia a otra.

>[!CAUTION]
>
>Utilice las opciones de mantenimiento solo para casos de mantenimiento específicos.

Las siguientes opciones se aplican a los cupones, que no están disponibles en implementaciones de Enterprise (FDAC). Más información en [Cupones personalizados](../send/personalized-coupons.md).

| Opción | Descripción |
|---|---|
| NmsModule_CouponsEnabled | Activa los cupones. |
| NmsCoupons_MaxPerTransaction | Número de cupones actualizados por transacción SQL. |

### Solicitudes de privacidad {#privacy-options}

Estas opciones controlan cómo Campaign procesa las solicitudes de privacidad, como la confirmación de eliminaciones, la cantidad de errores permitidos y cuánto tiempo se conservan los datos de solicitud. Obtenga más información en [Administrar solicitudes de privacidad en Campaign](../start/privacy.md).

| Opción | Descripción |
|---|---|
| Privacy_Request_ConfirmDeletePending | Configúrelo en 1 para confirmar cada eliminación manualmente en la interfaz en un segundo paso. De lo contrario, los datos se eliminan sin confirmación. |
| Privacy_Request_ConfirmDeletePendingDelay | Retraso tras el cual se cancela una solicitud que espera la confirmación de eliminación. |
| Privacy_Request_MaxErrorAllowed | Número máximo de errores permitidos al procesar o eliminar una solicitud de privacidad. |
| Privacy_Request_PurgeDelay | Retraso entre la creación de una solicitud en la cola y la eliminación de sus datos. |
| realtimeReporting_collectPII | Elección del acuerdo de información de identificación personal (PII) para el sistema de informes dinámico. El valor 1 corresponde a Preguntarme más tarde, 2 a Rechazar y 3 a Aceptar. [Más información](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reporting/dynamic-reporting/pii-agreement){target="_blank"} |

### Pista de auditoría {#audit-trail-options}

La pista de auditoría registra los cambios realizados en las entidades de Campaign. Utilice estas opciones para habilitarlo o deshabilitarlo para una entidad, por ejemplo, para ahorrar espacio en la base de datos. Establezca el valor en 1 para activar la pista de auditoría y en 0 para desactivarla. Más información en [Pista de auditoría](../reporting/audit-trail.md#enable-disable-audit-trail).

| Opción | Entidad auditada |
|---|---|
| XtkAudit_Workflows | Flujos de trabajo |
| XtkAudit_DataSchema | Esquemas |
| XtkAudit_Option | Opciones |
| XtkAudit_Delivery | Envíos |
| XtkAudit_ExtAccount | Cuentas externas |
| XtkAudit_DeliveryMapping | Asignaciones de envíos |
| XtkAudit_WebApp | Aplicaciones web |
| XtkAudit_Offer | Ofertas |
| XtkAudit_Operator | Operadores |
| XtkAudit_Enable_All | Todas las entidades |

### Integraciones y encuestas {#integration-options}

Estas opciones almacenan la configuración de las integraciones y las encuestas: las credenciales de Adobe Developer Console para las páginas de aterrizaje, la última fecha de sincronización de la actividad del conector CRM y la copia de seguridad predeterminada de las respuestas a las encuestas. Obtenga más información en [Actualizar perfiles de Adobe Experience Platform desde las páginas de aterrizaje de Adobe Campaign](../connect/ac-aep-landing-pages.md), [Sincronización de datos de conectores de CRM](../connect/crm-data-sync.md) y [Administrar respuestas](../dev/surveys/managing-answers.md).

| Opción | Descripción |
|---|---|
| IMS_CLIENT_ID, IMS_CLIENT_SECRET, IMS_ORG_ID, IMS_CLIENT_API_KEY | Credenciales de Adobe Developer Console utilizadas para las páginas de aterrizaje con Adobe Experience Platform. [Más información](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_ seguido del nombre interno de la instancia y el nombre de la actividad | Fecha de la última sincronización de la actividad genérica del conector CRM. Créela manualmente como una opción de texto, con el formato `yyyy/MM/dd hh:mm:ss`. [Más información](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | Créelo y establézcalo en 1 para guardar una copia de las respuestas sin procesar de forma predeterminada para todas las encuestas. [Más información](../dev/surveys/managing-answers.md) |
| AEMResourceTypeFilter | Tipos de recursos de Adobe Experience Manager que se pueden utilizar en Campaign, separados por comas. [Más información](../connect/ac-aem.md) |
| nmsPipeline_config | Configuración de Adobe Experience Cloud déclencheur en formato JSON. Créela como una opción de texto largo. [Más información](../connect/ac-triggers.md) |
| TNT_EdgeServer | Servidor de Adobe Target utilizado para la integración, configurado de forma predeterminada. Es el servidor de dominio de Adobe Target seguido de /m2, por ejemplo tt.omtrdc.net/m2. [Más información](../connect/ac-at.md) |
| TNT_TenantName | Nombre de la organización de Adobe Target (cliente). [Más información](../connect/ac-at.md) |
| AAM_DataSourceId, AAM_DestinationId | Identificadores utilizados por la integración con Adobe Audience Manager. [Más información](../start/shared-audiences.md) |
| WdbcCapabilities_AzureDw | Opciones del conector Azure Synapse (Azure SQL Data Warehouse). [Más información](../connect/fda.md) |

## Temas relacionados {#related-topics}

* [Paquetes integrados](built-in-packages.md)
* [Principios globales](general-architecture.md)
* [Guía de rotación de credenciales](../../technotes/security/credential-rotation-guide.md)
