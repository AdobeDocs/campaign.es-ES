---
title: Conector SMPP en propiedades de entrega
description: Acerca de la configuración del conector SMPP en envíos
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="Disponibilidad limitada" type="Informative"
source-git-commit: 36bb1e2c9e2391065360c3cd2ad97612373ec0c2
workflow-type: tm+mt
source-wordcount: '1326'
ht-degree: 5%

---


# Descripción del conector SMPP {#smpp-connector-desc}

>[!IMPORTANT]
>
>Esto se aplica a Adobe Campaign 8.7.2 y versiones posteriores.
>
>Para ver las versiones anteriores, consulte la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## Flujo de datos del conector SMS {#sms-data-flow}

En esta sección se describe cómo gestiona los datos el proceso SMS.

Este es un diagrama de bloque de alto nivel que resume cómo el proceso SMS interactúa con su entorno.

![](assets/smsv2_highlevel.png){zoomable="yes"}

El proceso SMS aloja 2 componentes importantes: el propio conector SMPP que gestiona la comunicación con el proveedor SMPP y una tarea en segundo plano para la reconciliación SR.

### Flujo de datos para cuentas SMPP {#sms-data-flow-smpp-accounts}

El proceso del SMS sondea nms:extAccount y genera nuevas conexiones en su conector SMPP, pasando la configuración de cada cuenta. La frecuencia de sondeo se puede ajustar en serverConf, en la configuración *configRefreshMillis*.

Para cada cuenta SMPP activa, el conector SMPP intenta mantener las conexiones activas todo el tiempo. Se vuelve a conectar si se pierde la conexión.

### Flujo de datos al enviar mensajes {#sms-data-flow-sending-msg}

* El proceso de SMS selecciona los envíos activos analizando nms:delivery. Una entrega está activo cuando:
   * Su estado implica que se pueden enviar mensajes
   * Su periodo de validez no ha caducado
   * En realidad es una entrega (por ejemplo, no es una plantilla, no se elimina)
   * El conector SMPP podría abrir al menos una conexión para la cuenta externa vinculada al envío
* Para cada entrega, el proceso SMS carga las partes de la entrega. Si la parte del envío se envió parcialmente, el proceso de SMS comprueba qué mensajes ya se enviaron comprobando el registro general.
* El proceso de SMS expande la plantilla con datos de personalización de la parte del envío.
* El conector SMPP genera una MT (SUBMIT_SM PDU) que coincide con el contenido y otras configuraciones.
* El conector SMPP envía la MT a través de una conexión de transmisor (o transceptor).
* El proveedor devuelve un ID para este MT. Se inserta en nms:providerMsgId.
* El proceso del SMS actualiza el registro general al estado enviado.
* En caso de error final, el proceso del SMS actualiza el registro general en consecuencia y puede crear un nuevo tipo de error en nms:broadLogMsg.

### Flujo de datos al recibir SR {#sms-data-flow-sr}

* El conector SMPP recibe y descodifica el SR (PDU DELIVER_SM). Utiliza expresiones regulares definidas en la cuenta externa para obtener el ID y el estado del mensaje.
* El ID y el estado del mensaje se insertan en nms:providerMsgStatus
* Después de insertarse, el conector SMPP responde con una PDU DELIVER_SM_RESP.
* Si algo salió mal durante el proceso, el conector SMPP envía una PDU DELIVER_SM_RESP negativa y registra un mensaje.

### Flujo de datos mientras se recibe un MO {#sms-data-flow-mo}

* El conector SMPP recibe y descodifica el MO (PDU DELIVER_SM).
* La palabra clave se extrae del mensaje. Si coincide con cualquier palabra clave declarada, se ejecutan las acciones correspondientes. Puede escribir en nms:address para actualizar la cuarentena.
* Si se declaran los TLV personalizados, se descodifican según su configuración respectiva.
* El MO completamente descodificado y procesado se inserta en la tabla nms:inSms.
* El conector SMPP responde con una PDU DELIVER_SM_RESP. Si se detecta algún error, se devuelve un código de error al proveedor.

### Flujo de datos mientras se reconcilian MT y SR {#sms-reconciling-mt-sr}

* El componente de reconciliación SR lee periódicamente nms:providerMsgId y nms:providerMsgStatus. Los datos de ambas tablas se unen.
* Para todos los mensajes que tienen una entrada en ambas tablas, se actualiza la entrada correspondiente nms:broadLog.
* La tabla nms:broadLogMsg puede actualizarse en el proceso si se detecta un nuevo tipo de error, o para actualizar los contadores de errores que no se hayan clasificado manualmente.

## Entradas de MT, SR y “broadlog” que coinciden {#sms-matching-entries}

Este es un diagrama que describe todo el proceso:

![](assets/message_processing.png){zoomable="yes"}

**Fase 1**

* El mensaje se analiza, se formatea y se transmite al conector SMPP.
* El conector SMPP lo formatea como una SUBMIT_SM MT PDU.
* El MT se envía al proveedor del SMPP.
* El proveedor responde con SUBMIT_SM_RESP. SUBMIT_SM y SUBMIT_SM_RESP coinciden con su número de secuencia.
* SUBMIT_SM_RESP proporciona un ID proveniente del proveedor. Este ID se inserta junto con el ID de registro general en la tabla nms:providerMsgId.

**Fase 2**

* El proveedor envía una PDU SR DELIVER_SM.
* El SR se analiza para extraer el ID del proveedor, el estado y el código de error. Este paso utiliza expresiones regulares de extracción.
* El ID del proveedor y su estado correspondiente se insertan en nms:providerMsgStatus.
* Cuando todos los datos se insertan de forma segura en la base de datos, el conector SMPP responde con DELIVER_SM_RESP. DELIVER_SM y DELIVER_SM_RESP coinciden con su número de secuencia.

**Fase 3**

* El componente de reconciliación SR del proceso SMS analiza periódicamente las tablas nms:providerMsgId y nms:providerMsgStatus.
* Si alguna fila tiene ID de proveedor coincidentes en ambas tablas, las dos entradas se unen. Esto permite hacer coincidir el ID de registro general (almacenado en providerMsgId) con el estado (almacenado en providerMsgStatus)
* El registro general se actualiza con el estado correspondiente.

## Afinidades y el conector de proceso dedicado {#sms-affinities}

El conector de proceso dedicado ignora las afinidades, solo se ejecuta dentro del proceso SMS.

## opciones de serverConf {#sms-serverconf-options}

Algunos ajustes se pueden ajustar en serverConf.xml. Al igual que cualquier otra configuración de este archivo, debe especificarse en el archivo config-instance.xml. Todos los ajustes se encuentran en el elemento &lt; mta2 >.

Esta tabla resume todas las configuraciones. Los valores sensatos mín./máx. dan una idea aproximada del rango que se debe tener en cuenta en la mayoría de los casos. El valor de depuración es el valor que se debe elegir al intentar encontrar problemas que no están relacionados con el rendimiento.

| Configuración | Descripción | Predeterminado | Valor razonable mínimo | Valor sensato máximo | Valor de depuración |
|:-:|:-:|:-:|:-:|:-:|:-:|
| batchUpdateSize | Tamaño de los microlotes de actualización | 5000 | 100: Latencia muy baja | maxWaitingMessages/updateThreads: Sobrepasar este valor no sirve de nada porque maxWaitingMessages limitará el almacenamiento en búfer de todas formas | 1: Deshabilitar el microagrupamiento, actualizar los mensajes uno por uno |
| configRefreshMillis | Periodo para la recarga de configuración en milisegundos | 10000 | pollPeriodMillis: baja latencia | 600000: No vuelva a cargar demasiado rápido para guardar los recursos | 500: La baja latencia permite probar nuevos ajustes más rápido |
| deliveryPartRetryCount | Número máximo de veces que deliveryPart se vuelve a intentar o se pospone. Precaución: al reiniciar el proceso de envío se cuenta como un reintento, los bloqueos también se pueden contar como un reintento. | 20 | 1: Deshabilitar los reintentos | 50: Hacer que los mensajes sean más persistentes para evitar proveedores inestables | 1: Deshabilitar los reintentos. 1000: Evite vaciar los mensajes fallidos. |
| deliveryPartRetryDelaySeconds | Retraso mínimo antes de volver a intentar una deliveryPart. Se trata de procesos cruzados y contenedores cruzados. El retraso se expresa en segundos. | 60 | 0: Reintentos inmediatos | 3600: Reintentos muy lentos (1 hora entre cada reintento) | 1: Facilita los reintentos en registros ocupados. |
| logOutput | Enviar datos de monitorización y generación de perfiles en la salida de registro principal. | verdadero | false: puede aumentar un poco el rendimiento. Desanimado. | true: habilitar el registro. | verdadero |
| maxWaitingMessages | Número máximo de mensajes procesados en cualquier momento | 50000 | 256: Suficiente para un solo deliveryPart | 200000: limitado por la longitud de la consulta SQL (64 k) | 1: Procesar los mensajes uno por uno |
| pollPeriodMillis | Frecuencia de sondeo de base de datos (en milisegundos) para comprobar si hay mensajes nuevos | 2000 | 500: Latencia muy baja | 10000: Lotes más grandes | 500: La baja latencia facilita la depuración. |
| prepareThreads | Número máximo de hilos para la preparación del mensaje | 3 | 1: Un solo hilo | Número de CPU. Tenga cuidado con el uso de RAM. Para aumentar por encima de 6 puede ser necesario aumentar maxSMSMemoryMb, maxProcessMemoryAlertMb y maxProcessMemoryWarningMb | 1: Un solo subproceso genera registros más limpios. |
| profDeliveryStat | Registra varias estadísticas agregadas sobre los aspectos internos del proceso de SMS | verdadero | false: puede aumentar un poco el rendimiento. Desanimado. | true: registro de poca profundidad | verdadero |
| profLogPerMessage | Registra cada paso de procesamiento de cada mensaje | falso | false: Reduzca la amplitud del registro. | true: registro de gran nivel de detalle. **Usar solo cuando sea absolutamente necesario**. Gran impacto en el rendimiento. **Deshabilite esta configuración tan pronto como se hayan recopilado suficientes datos**. | verdadero |
| providerIdScanPeriod | Período en segundos entre análisis para buscar nuevos id de proveedor para conciliar | 10 | 1: Baja latencia | 60: Lotes más grandes para obtener más rendimiento | 1: La baja latencia ayuda a depurar el procesamiento de mensajes. |
| providerIdThreads | Número de subprocesos para la reconciliación del identificador de proveedor. 1 subproceso por instancia es suficiente. Defina como 0 para deshabilitarlo en este contenedor. | 1 | 0: Deshabilitar en este contenedor | 1 | 1 |
| sendingThreads | Número máximo de hilos de envío | 1 | 1: Un solo hilo | Número de CPU. Demasiados hilos suelen dañar el rendimiento. | 1: Un solo subproceso genera registros más limpios. |
| updateThreads | Número máximo de subprocesos para actualizar la base de datos | 1 | 1: Un solo hilo | Número de CPU. Cada subproceso crea su propia conexión DB. | 1: Un solo subproceso genera registros más limpios. |
| verifyMode | Simular el envío de mensajes. Los mensajes no se envían realmente. Útil para la depuración | falso | falso | verdadero | false: ejecute el sistema normalmente. true: Probar solo el acceso a la base de datos y la preparación de mensajes. |
