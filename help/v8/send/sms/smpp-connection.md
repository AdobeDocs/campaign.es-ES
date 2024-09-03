---
title: Validación de una conexión SMPP
description: Obtenga información sobre cómo validar una conexión SMPP
feature: SMS
role: User
level: Intermediate
badge: label="Disponibilidad limitada" type="Informative"
source-git-commit: dde669980493b996c80baacc8726db87353585ad
workflow-type: tm+mt
source-wordcount: '4439'
ht-degree: 16%

---


# Validación de una conexión SMPP {#validate-smpp-connection}

A continuación se indican algunas comprobaciones para asegurarse de que la conexión SMPP sea correcta.

## Cosas que hay que comprobar antes de empezar {#check-go-live}

Antes de empezar, asegúrese de que su configuración de SMPP es correcta con la lista de comprobaciones a continuación.

>[!IMPORTANT]
>
>Esta lista de comprobación no es exhaustiva. Cuantos más controles realice, mejor.

>[!NOTE]
>
>Habilite los seguimientos detallados del SMPP durante las comprobaciones, lo que le ayudará a usted y al equipo de asistencia a comprender los problemas.

### Comprobación de conflictos en la cuenta externa {#sms-external-accounts-check}

Compruebe que no le quedan cuentas externas de SMS. Elimine las cuentas de prueba para eliminar posibles conflictos.

Compruebe que ninguna otra instancia se conecte a la cuenta externa. En particular, asegúrese de que el entorno de producción previa no se conecta a la cuenta externa de producción.

Si necesita tener varias cuentas en la misma instancia de Campaign que se conecten al mismo proveedor, póngase en contacto con el proveedor para asegurarse de que realmente se distinguen las conexiones entre estas cuentas. Si tiene varias cuentas con el mismo inicio de sesión necesita una configuración adicional.

Compruebe que todas las cuentas externas de SMS habilitadas tengan habilitada la configuración de proceso dedicado. No puede mezclar entre los 2 tipos de cuentas (con y sin proceso dedicado) en la misma instancia.

### Haga una prueba en el mundo real {#real-test}

Intente enviar algunos SMS en diferentes móviles.

**Enviar SMS con todo tipo de caracteres**

Si necesita enviar SMS con caracteres que no sean GSM o ASCII, intente enviar algunos mensajes con los caracteres más diversos posibles. Si configura una tabla de asignación de caracteres personalizada, envíe al menos un SMS para todos los valores posibles de data_coding.

**Compruebe que SR se procesa correctamente**

El SMS debe marcarse como recibido en el registro de envíos. El registro de envío debe tener el siguiente aspecto: &quot;*SR yourProvider stat=DELIVRD err=000|#MESSAGE#*&quot;.

Compruebe que ha establecido correctamente el campo &quot;*SMSC Implementation name*&quot;: el registro de envío nunca debe contener &quot;*SR Generic*&quot; en entornos de producción.

**Compruebe que se han procesado los MO**

Envíe algunos SMS para todas las palabras clave de respuesta automática y compruebe que la respuesta sea rápida (no más de unos segundos).

Compruebe que los MO estén insertados en la base de datos *nms:inSms*. Si tiene TLV personalizados, asegúrese de que también estén insertados correctamente y tengan el formato correcto.

Compruebe en el registro que Campaign responde con un *DELIVER_SM_RESP correcto (command_status=0)*.

**Realizar una prueba de carga**

Esto es especialmente importante si envía muchos mensajes o si utiliza la mensajería en tiempo real.

Realice una prueba que cargue la conexión al 100 % durante al menos 5 segundos. Usted tendrá que enviar mensajes reales si el proveedor no tiene una manera de conectarse a una cuenta falsa para las pruebas. Una manera de lograrlo es monitorizar de cerca la primera entrega lo suficientemente grande con mensajes SMPP detallados habilitados.

El número mínimo de mensajes que se van a enviar se puede calcular de esta manera:

*Rendimiento máximo de MT * Número total de conexiones de transmisores/transceptores * 5*

Una vez finalizada la entrega, compruebe lo siguiente:

* Comprobar que todos los mensajes se hayan enviado (no necesariamente recibidos)
* Debe haber una PDU absolutamente cero con command_status no 0x00000000, a menos que el proveedor lo indique explícitamente como operación normal
* Las conexiones deben permanecer absolutamente estables (sin PDU BIND) durante todo el proceso de entrega.
* Compruebe que todos los mensajes tengan un SR y que se haya procesado correctamente (consulte [Comprobar que SR se haya procesado correctamente](#real-test)). Si un pequeño porcentaje tiene errores, compruebe que estos eran errores que devolvían el SR real, no errores durante el envío o el procesamiento, en el lado de Campaign.
* Si no está seguro del rendimiento, compruebe que la latencia sea razonable, especialmente entre una PDU y su RESP correspondiente, tener una latencia de más de 500 ms puede ser un problema para un alto rendimiento. Utilice esa latencia para comprobar la fórmula de la ventana de envío (consulte la configuración de la ventana de envío para obtener más información)

### Compruebe las PDU {#pdu}

Compruebe que las PDU están formateadas correctamente.

>[!IMPORTANT]
>
>Este paso es muy recomendable cuando se conecta a un proveedor que no estaba conectado a Campaign anteriormente.

**ENLAZAR**

Compruebe que las PDU BIND_* se envían correctamente. Lo más importante que hay que comprobar es que el proveedor siempre devuelve PDU BIND_*_RESP correctas (command_status = 0).

Compruebe que no haya demasiadas PDU BIND_*. Si hay demasiados, podría indicar que la conexión es inestable. Consulte la sección de solución de problemas de conexiones inestables a continuación para obtener más información al respecto.

**ENQUIRE_LINK**

Compruebe que las PDU ENQUIRE_LINK se intercambian regularmente cuando la conexión está inactiva.

**SUBMIT_SM / DELIVER_SM**

Envíe un mensaje y, a continuación, busque en los registros sus PDU SUBMIT_SM, SUBMIT_SM_RESP, DELIVER_SM y DELIVER_SM_RESP correspondientes.

Con la *PDU SUBMIT_SM*:

* Compruebe que data_coding es correcto (0 de forma predeterminada).
* Compruebe que short_message esté codificado correctamente: intente descodificarlo con un convertidor hexadecimal que admita varias codificaciones (hay algunas disponibles en línea).
* Si utiliza message_payload para mensajes largos, compruebe que el contenido esté presente en el campo opcional y no en el campo short_message.

Con la *PDU SUBMIT_SM_RESP*:

* Compruebe que se ha realizado correctamente (command_status = 0).
* Compruebe que su cuerpo contiene un ID formateado correctamente seguido de un byte &#39;0&#39;.

Con la *PDU DELIVER_SM*:

* Descodificar el campo hexadecimal short_message (hay herramientas en línea para ello).
* Compruebe con una herramienta de comprobación de regex que la expresión regular definida en Extracción de regex del ID en el SR devuelve exactamente un grupo de captura y que captura el ID completo en el mensaje.
* Compruebe que el ID extraído coincide con el de SUBMIT_SM_RESP.
* Compruebe que la expresión regular definida en la Regex de extracción del estado en el SR devuelve el contenido del campo de estadística.
* Compruebe que la expresión regular definida en la Regex de extracción del error en el SR devuelve el contenido del campo error.

Con la *PDU DELIVER_SM_RESP*:

* Compruebe que se envió rápidamente después de recibir la PDU DELIVER_SM (normalmente menos de 1 segundo).
* Compruebe que se ha realizado correctamente (command_status = 0).

### Prueba en directo con el proveedor {#sms-live-test}

Una práctica recomendada antes de lanzarse es hacer una prueba en directo con el proveedor, con ambas partes mirando los registros durante la ejecución.

>[!IMPORTANT]
>
>Este paso es muy recomendable cuando se conecta a un proveedor que nunca antes se había conectado a Campaign.

### Deshabilite los seguimientos detallados del SMPP {#sms-disable-smpp}

Una vez completadas todas las comprobaciones, la última acción que se debe realizar es deshabilitar los seguimientos detallados del SMPP para que no genere demasiados registros.

## Solución de problemas de SMS {#sms-troubleshooting}

### Procedimiento general de localización de averías {#sms-general-troubleshooting}

El conector SMS incluye 3 entidades: el proveedor SMPP, el Adobe y usted.
El principal experto en SMS es el proveedor de SMPP, por lo que debe participar en todos los problemas relacionados con el tráfico de SMS (problemas de conexión, mensajes perdidos, problemas de codificación, reglas específicas del país, etc.).

#### Habilitar proceso dedicado {#sms-dedicated-process}

>[!IMPORTANT]
>
>Asegúrese de que **[!UICONTROL Send messages through a dedicated process]** esté habilitado en todas las cuentas de SMS activas.

Si tiene problemas con el conector antiguo (basado en MTA) (proceso dedicado deshabilitado), debe considerar la posibilidad de migrar al conector de proceso dedicado. Tiene un rendimiento mucho mejor, es más estable y proporciona una mejor retroalimentación en sus registros.

#### Conflicto entre diferentes cuentas externas {#sms-conflict-external-accounts}

Si la instancia tiene varias cuentas externas SMS, compruebe que los problemas no sean causados por un conflicto entre cuentas.

Para aislar la cuenta externa que causa problemas:

1. Deshabilitar todas las cuentas externas
1. Habilitar una cuenta externa
1. Intente reproducir el problema
1. Si el problema no aparece con esa sola cuenta, desactívela y vuelva a empezar en el paso 2 de la siguiente cuenta. Una vez que ha comprobado cada cuenta individualmente, existen dos escenarios posibles:

**El problema apareció en una o varias cuentas**

En este caso, puede aplicar otros procedimientos de resolución de problemas en cada cuenta de forma individual. Es mejor deshabilitar otras cuentas al diagnosticar una cuenta, a fin de reducir el tráfico de red y la cantidad de registros.

**El problema no aparecía cuando solo una cuenta estaba activa en cualquier momento**

Tiene un conflicto entre cuentas. Adobe Campaign trata las cuentas individualmente, pero el proveedor puede tratarlas como una sola cuenta.

*Utiliza diferentes combinaciones de inicio de sesión y contraseña entre todas las cuentas*
Tendrá que ponerse en contacto con el proveedor para diagnosticar posibles conflictos de su parte.

*Algunas cuentas externas comparten la misma combinación de inicio de sesión y contraseña*
El proveedor no tiene forma de saber de qué cuenta externa proviene la PDU BIND, por lo que trata todas las conexiones de las cuentas múltiples como una sola, por lo que probablemente enrute MO y SR aleatoriamente a través de las 2 cuentas, lo que provoca problemas aparentemente aleatorios.

Si el proveedor admite varios códigos cortos para la misma combinación de inicio de sesión y contraseña, tendrá que preguntarle dónde colocar ese código corto en la PDU BIND. Tenga en cuenta que esta parte de información debe colocarse dentro de la PDU BIND, y no en SUBMIT_SM, porque la PDU BIND es el único lugar que permitirá enrutar los MO correctamente.

Consulte la sección [Información en cada tipo de PDU](#pdu) anterior para saber qué campos están disponibles en la PDU BIND; por lo general, colocaría el código corto en *address_range*, pero eso requiere asistencia especial del proveedor. Póngase en contacto con ellos para saber cómo esperan enrutar varios códigos cortos de forma independiente.

Adobe Campaign admite el manejo de varios códigos cortos en la misma cuenta externa muy bien, por lo que a menudo solo el uso de una sola cuenta para todo el tráfico funcionará bien.

#### Una cuenta externa ha dejado de funcionar {#sms-external-account-not-working}

En general, las conexiones SMPP tienden a ser muy estables a lo largo del tiempo y, una vez configuradas correctamente, deben seguir funcionando.

* Investigue si el conector se ha cambiado recientemente y quién lo ha cambiado (compruebe las Cuentas externas como grupo).
* Investigue si el sistema se actualizó y cuándo.
* Investigue si algún paquete que afecte a SMS pudo haberse actualizado recientemente.

Si ninguna de estas comprobaciones produce una causa raíz, póngase en contacto con el proveedor. A veces, cuando los proveedores actualizan sus plataformas, el conector se comporta de forma ligeramente diferente. Esto podría interrumpir la configuración optimizada e introducir regresiones.

Se recomienda mantenerse en contacto con el proveedor, que a menudo comunican los cambios importantes por adelantado.

#### Problema con el intermediario (alojado)  {#sms-issue-hosted}

* Si el problema se produce en un entorno de intermediario, asegúrese de que el envío y los broadlogs se crean y actualizan correctamente en el servidor intermediario. Si no es así, el problema no es un problema de SMS.
* Asegúrese de que el nombre del operador medio esté estrictamente en minúsculas; de lo contrario, el envío permanecerá en estado pendiente.
* Si todo funciona en el servidor central y los SMS se envían correctamente, pero la instancia de marketing no se actualiza correctamente, tiene un problema de sincronización intermedia.

#### Problema al conectarse al proveedor {#sms-issue-connection}

* Si la PDU BIND devuelve un código *command_status* distinto de cero (lo que significa que hay un error) o si no hay ninguna PDU BIND_RESP, pregunte al proveedor por qué sucede esto.
* Compruebe que la red está configurada correctamente para que la conexión TCP se pueda establecer con el proveedor.
* Pida al proveedor que compruebe que ha permitido correctamente las direcciones IP de la instancia de Adobe Campaign (la mayoría de los proveedores lo requieren).
* Compruebe la configuración de la cuenta externa. Pregunte al proveedor en caso de duda sobre el valor de algunos campos.
* Si la conexión es correcta pero inestable, compruebe [Problemas con conexiones inestables](#unstable-connections). más abajo.
* Si los problemas de conexión son difíciles de diagnosticar, una captura de red le proporcionará mucha información. Asegúrese de que la captura de red se ejecuta simultáneamente mientras aparece el problema para que se pueda analizar de forma eficaz. También debe anotar la hora exacta en la que aparece el problema para que sea más fácil encontrarlo en las capturas de red.

#### Problemas con conexiones inestables {#unstable-connections}

**Cómo diagnosticar conexiones inestables:**

Una conexión se considera inestable si ocurre alguna de estas cosas:

* La conexión dura menos de 1 hora.
* Reiniciar el proceso de SMS &quot;arreglará&quot; las cosas temporalmente. Probablemente significa que una conexión inestable déclencheur con la restricción, al reiniciar el proceso del SMS se borra la restricción y luego vuelve a ocurrir hasta que se encuentra la causa raíz.
* El proveedor envía PDU UNBIND. El proveedor nunca debe enviar PDU UNBIND en funcionamiento normal.
* *enquire_link* agota el tiempo de espera, ya sea en el lado de Campaign o en el del proveedor. Puede que vea o no INQUIRE_LINK_RESP con un código de error distinto de cero en ese caso.
* Hay muchas PDU BIND. No debe haber más de unas pocas durante un día (depende del número de conexiones). Más de una PDU BIND por hora y por conexión debería llamar su atención.

**Solucionar problemas de estabilidad de conexión:**

* Las conexiones inestables rara vez son la causa principal, a menudo es el resultado de otro problema que desencadena una desconexión de una manera u otra. La prioridad es encontrar la causa raíz.
* Habilite seguimientos detallados del SMPP. Los necesitará para ver qué está pasando cuando se reinicie la conexión.
* Si el proveedor envía PDU UNBIND, probablemente haga algo mal. Pregúnteles por qué envían UNBIND y probablemente lleve a la causa raíz.
* Realizar una captura de red es, a veces, la única manera de ver cómo se cierra la conexión.
* Si el proveedor cierra las conexiones (enviando un paquete TCP FIN o TCP RST), pregúntele por qué lo hace. Esto debería indicarle la causa raíz del problema.
* Si el proveedor cierra la conexión después de enviar un error limpio (como DELIVER_SM_RESP con un código de error), debe corregir su conector, ya que esto evita que se transmitan otros tipos de mensajes y almacenará en déclencheur la limitación de MTA. Esto es especialmente importante en el modo transceptor, donde el cierre de la conexión afecta tanto a MT como SR.
* Si hay tiempos de espera (tiempos de espera BIND, SUBMIT_SM), es posible que Campaign esté enviando mensajes demasiado rápido para ese proveedor. Intente reducir la configuración de *rendimiento máximo de MT* y compruebe si se resuelve el problema.

#### Problema al enviar un MT (SMS regular enviado a un usuario final)

* Compruebe que la conexión sea estable: una conexión SMPP debe permanecer activa durante al menos 1 hora de forma continua. Consulte la sección &quot;Problema con conexiones inestables&quot; anterior.
* Si al reiniciar el proceso de SMS hace que el envío de MT vuelva a funcionar por un período de tiempo corto, es probable que tenga un estrangulamiento debido a una conexión inestable. Consulte la sección &quot;Problema con conexiones inestables&quot; anterior.
* Compruebe que el registro general está presente y en el estado correcto con las fechas correctas. Si no es así, no se trata de un problema de SMS, sino de un problema de envío o de preparación de envíos (que está fuera del ámbito de este documento).
* Compruebe que el conector SMS está vinculado con el equipo del proveedor. Pídale información al proveedor para asegurarse de que todos los sistemas se comunican correctamente. Consulte PDU BIND_TRANSMITTER y BIND_TRANSCEIVER para obtener información sobre el proceso de enlace. Es posible que deba habilitar los seguimientos del SMPP para la correcta resolución de problemas.
* Con los seguimientos del SMPP activados, compruebe que la PDU SUBMIT_SM contenga la información correcta (consulte la documentación anterior).
* Compruebe que el proveedor responde con una PDU SUBMIT_SM_RESP con un valor &quot;OK&quot; (código 0). Asegúrese de que la PDU llega con un retraso razonable: cualquier valor superior a 1 segundo es sospechoso y debe ser consultado con el proveedor, normalmente llega en menos de 100 ms.
* Si todos estos pasos funcionan, puede estar seguro de que el problema está en el lado del proveedor. Tendrán que resolver problemas en su plataforma.
* Si funciona pero el rendimiento es inconsistente, intente ajustar la ventana de envío y reducir el rendimiento de MT. Tendrá que trabajar con el proveedor para ajustarlo. Campaign puede enviar mensajes muy rápidamente, por lo que pueden surgir problemas de rendimiento en el equipo del proveedor.

#### MT están duplicados (el mismo SMS se envía varias veces seguidas)

Los duplicados suelen deberse a reintentos. Es normal tener duplicados al reintentar mensajes, por lo que debe concentrar sus esfuerzos en eliminar la causa raíz de los reintentos.

* Si ve duplicados enviados exactamente con 60 segundos de diferencia (o cualquier otro período sospechosamente &quot;regular&quot;), probablemente sea un problema en el lado del proveedor, no envían un SUBMIT_SM_RESP lo suficientemente rápido.
* Si ve muchos BIND/UNBIND, tiene una conexión inestable: vea la sección [Problemas con conexiones inestables](#unstable-connections) para obtener soluciones antes de intentar resolver los problemas de mensajes duplicados.
* Compruebe que todas las PDU SUBMIT_SM tengan SUBMIT_SM_RESP coincidente poco después. Si no lo hacen o SUBMIT_SM_RESP es demasiado lento, el problema está en el lado del proveedor.

Mitigación de la cantidad de duplicados cuando hay un reintento:

* Reduzca la *ventana de envío*. La ventana de envío debe ser lo suficientemente grande como para cubrir la latencia SUBMIT_SM_RESP, pero no demasiado grande. Su valor representa la cantidad máxima de mensajes que se pueden duplicar si se produce un error mientras la ventana está llena.

#### Problema al procesar SR (recibos de entrega)

* Necesitará los seguimientos del SMPP activados para realizar cualquier tipo de resolución de problemas de SR.
* Compruebe que la PDU DELIVER_SM proviene del proveedor y que está bien formada.
* Compruebe que Campaign responde con una PDU DELIVER_SM_RESP correcta de manera oportuna. Esto garantiza que el SR se ha insertado en la tabla providerMsgStatus para que el proceso SMS lo procese de forma diferida.

Si la PDU DELIVER_SM no se reconoce correctamente, debe comprobar algunas cosas:

* Compruebe las expresiones regulares (regex) relacionadas con la extracción de ID y el procesamiento de errores en la cuenta externa. Es posible que tenga que validarlas con el contenido de la PDU DELIVER_SM.
* Compruebe que los errores estén aprovisionados correctamente en la tabla broadLogMsg (la documentación de Campaign lo explica en detalle).

Si el conector SMPP extendido ACC ha reconocido la PDU DELIVER_SM pero el broadLog no se actualiza correctamente, compruebe el proceso de reconciliación de ID descrito en la sección Coincidencia de las entradas de MT, SR y broadlog anterior.

Si ha corregido todo, pero algunos SR no válidos siguen en los búferes del proveedor, puede omitirlos con la opción Número de confirmación de ID no válido. Debe utilizarse con cuidado y restablecerse a 0 lo antes posible después de que los búferes estén limpios.

Si el procesamiento de SR es lento, intente clasificar los mensajes de estado más comunes de la tabla BroadLogMsg.

Si solo se reciben algunos SR, pero no todos, compruebe que ningún otro sistema se conecte a la cuenta del proveedor, como un sistema de prueba. SR se puede enrutar en cualquier conexión, por lo que algunos de ellos se pueden enrutar a este otro sistema. El proveedor puede ayudarle a encontrar dónde se conecta este otro sistema a la cuenta.

#### Problema al procesar MO (y cuarentena/respuesta automática)

* Habilite los seguimientos del SMPP durante las pruebas. Si no habilita TLS, siempre es mejor realizar una captura de red al solucionar problemas de MO para comprobar que las PDU contienen la información correcta y tienen el formato correcto.
* Al capturar tráfico de red o analizar los seguimientos del SMPP, asegúrese de capturar toda la conversación con el MO y su mensaje MT de respuesta (si se configura una respuesta).
* Si el MO (DELIVER_SM PDU) no aparece en los seguimientos, puede estar seguro de que el problema está en el lado del proveedor. Tendrán que resolver problemas en su plataforma.
* Si aparece la PDU DELIVER_SM, compruebe que Campaign la reconoce con una PDU DELIVER_SM_RESP correcta (código 0). Este RESP garantiza que Campaign ha aplicado toda la lógica de procesamiento (respuesta automática y cuarentena). Si no es el caso, busque un mensaje de error en los registros de proceso de los SMS.
* Si las respuestas automáticas están habilitadas, compruebe que SUBMIT_SM se haya enviado al proveedor. Si no es así, se garantiza que encontrará un mensaje de error en los registros de proceso de los SMS.
* Si la PDU SUBMIT_SM MT que contiene la respuesta se encuentra en los seguimientos, pero el SMS no llega al teléfono móvil, tendrá que ponerse en contacto con el proveedor para obtener ayuda sobre la resolución de problemas porque el problema probablemente esté de su lado.

#### Problema durante la preparación de la entrega sin excluir destinatarios en cuarentena (en cuarentena por la función de respuesta automática)

* Compruebe que el formato del número de teléfono es exactamente el mismo en la tabla de cuarentenas y en el registro de envíos. Si no es así, consulte la configuración &quot;Enviar número de teléfono completo&quot; anterior si tiene problemas con el prefijo más del formato de número de teléfono internacional.
* Comprobar códigos cortos: las exclusiones se producen si el código corto del destinatario es el mismo que se define en la cuenta externa o si está vacío (vacío = cualquier código abreviado). Si solo se utiliza un código corto para toda la instancia de Campaign, es más fácil dejar vacíos todos los campos de &quot;código corto&quot;.

#### Problemas de codificación  {#sms-encoding-issues}

Los problemas de codificación son frecuentes en los SMS. A continuación se indican algunos pasos básicos.

**Paso 1: Ponerse en contacto con el proveedor**

El proveedor es el experto que sabe cómo funcionan los SMS. Póngase en contacto con ellos y vea con ellos lo que está mal. Deben poder decirle si el problema está de su lado o en Campaign. Si el problema está en Campaign, deben poder decirle exactamente qué campo es incorrecto, lo que ayuda enormemente.

**Paso 2: Saber qué hay en el mensaje**

Tendrá que saber qué hay en su mensaje. Esa frase puede sonar fácil, pero no lo es. Unicode permite tantas variantes para caracteres similares que Campaign no puede manejarlos todos.

La fuente más común de problemas es copiar y pegar desde un procesador de textos, que cambia los caracteres habituales a versiones tipográficamente correctas: los espacios cambian a espacios sin saltos, las comillas dobles cambian a comillas de apertura y cierre, los signos menos cambian a varios tipos de guiones...

No copie y pegue el mensaje durante la prueba, escríbalo siempre directamente en la interfaz.

**No se deje intimidar por hexadecimales**. Hexadecimal se ve extraño y antinatural, pero tiene una calidad muy distinta: se puede decir la diferencia entre caracteres similares. Una L minúscula, una I mayúscula, O, 0, todos los diferentes tipos de comillas, codificaciones no latinas o incluso diferentes tipos de espacios pueden verse igual (o incluso no mostrarse). Hexadecimal muestra todo y ayuda a comparar cosas.

Para convertir unicode a hexadecimal, puede utilizar las herramientas en línea.

**Al abrir tickets** acerca de problemas de codificación, ya sea con el proveedor o con la compatibilidad con Campaign, **incluya una versión hexadecimal** de lo que escribe y lo que ve.

**Paso 3: Saber lo que debe enviar**

Determine la codificación que espera usar y busque en línea su tabla de caracteres. Compruebe que los caracteres que desea enviar están disponibles en la página de código de destinatario. Compruebe que el campo data_coding es correcto y coincide con lo que usted y el proveedor esperan.

**Paso 4: Saber lo que realmente ha enviado**

Necesitará la salida de depuración del conector para ver exactamente qué bytes envía al proveedor. Los problemas de codificación aparecen en las PDU SUBMIT_SM, por lo que asegúrese de registrarlos. Envíe mensajes muy distintos que sean fáciles de encontrar en el registro.

No dude en enviar diferentes tipos de caracteres especiales al realizar pruebas. Por ejemplo, la codificación GSM7 tiene caracteres extendidos que son muy distintos en su forma hexadecimal, por lo que son fáciles de identificar porque no aparecen en ninguna otra codificación.

#### Problemas de rendimiento {#sms-performance-issues}

>[!NOTE]
>
>El rendimiento es un tema muy amplio. En esta sección se proporcionan algunas comprobaciones básicas que se deben realizar antes de intentar escalar o realizar otros proyectos grandes.

**Problemas de rendimiento al enviar MT**

* Compruebe que todas las configuraciones en la sección Throughput and delays de la cuenta externa sean correctas y que coincidan con la configuración permitida por el proveedor.
* Compruebe que no haya reintentos.
* Compruebe que la infraestructura del proveedor no esté saturada. Compruebe si hay errores RMSGQFUL o RTHROTTLED en las PDU RESP.
* Compruebe la configuración de serverConf. Comience con los valores predeterminados y aumente los parámetros lentamente y uno a uno.
* Compruebe que el proceso del SMS no se reinicie todo el tiempo cuando esté bajo carga. Si es así, es posible que deba aumentar *maxSMSMemoryMb*, *maxProcessMemoryAlertMb* y *maxProcessMemoryWarningMb* en el archivo serverConf.

**Problemas de rendimiento al recibir SR**

Si el proveedor se queja de la sobrecarga de búfer por su parte, esto puede deberse a que Campaign no recibe SR lo suficientemente rápido.

* Compruebe que la base de datos de instancias no esté sobrecargada. El procesamiento SR depende en gran medida del rendimiento de la base de datos.
* Pida al proveedor que aumente la ventana de envío para DELIVER_SM de su lado. Lo ideal es que sea tan grande como el valor *batchUpdateSize* en serverConf.

### Elementos que se deben incluir al comunicar un problema de SMS

Siempre que busque ayuda sobre un problema de SMS (ya sea abriendo una entrada de asistencia en Adobe Campaign, al proveedor de SMS o cualquier tipo de comunicación sobre el tema), deberá incluir al menos la siguiente información para asegurarse de que esté debidamente clasificado. Los problemas debidamente calificados son la clave para resolverlos más rápido, por lo que dedicar un poco más de tiempo a tratar de comprender la situación y proporcionar información significativa dará un gran salto en eficiencia.

* Habilite mensajes SMPP detallados durante el momento en que aparezca el problema. La mayoría de los problemas de SMS son prácticamente imposibles de resolver sin esto.
* Si el problema está relacionado con el tráfico de SMS, póngase en contacto primero con el proveedor. Son los más conocedores y su plataforma suele ser adecuada para un diagnóstico eficiente de los problemas de tráfico SMS en tiempo real.
* Incluya una descripción breve pero objetiva del problema.
* Incluya una descripción del resultado esperado.
* Incluya todos los comentarios del proveedor.
* Incluya registros relevantes o capturas de red. Al realizar capturas, asegúrese de reproducir el problema durante la captura o no servirá de nada.
* Si incluye registros, seguimientos o capturas, indique la ubicación exacta en el archivo cuando aparezca el problema, así como la ubicación exacta de un ejemplo en funcionamiento, si hay alguno. Las capturas o los rastros pueden ser grandes y tediosos de ver, por lo que cualquier cosa que ayude a encontrar información en ellos es útil.
* Si hace referencia a mensajes, PDU o registros, indique claramente su marca de tiempo para que sean fáciles de encontrar por otras personas.
* Intente reproducir el problema en un entorno de prueba. Si no está seguro de un ajuste, pruébelo en el entorno de prueba y compruebe el resultado con los seguimientos del SMPP. Generalmente es mejor informar de problemas replicados en entornos de prueba que informar directamente de los problemas en entornos de producción.
* Incluya cualquier cambio o ajuste realizado en la plataforma: incluso un pequeño cambio puede tener enormes impactos. Además, incluya cualquier cambio que el proveedor pueda haber realizado de su parte.

#### ¿Cuándo es útil una captura de red?

No siempre se necesita una captura de red. Con mucha frecuencia, los mensajes SMPP detallados son suficientes. Estas son algunas directrices que le ayudarán a determinar si vale la pena realizar una captura de red:

* Problemas de conexión, pero los mensajes detallados no muestran ninguna PDU BIND_RESP.
* Desconexiones inexplicables sin mensaje de error (ese es el comportamiento del conector cuando detecta un error de protocolo de bajo nivel).
* El proveedor se queja del proceso de desvinculación/desconexión.
* Hay problemas de codificación en los campos TLV opcionales.
* Se sospecha que el tráfico se mezcla entre diferentes conexiones.

En todas las demás situaciones, intente analizar primero los mensajes SMPP detallados y solicite una captura de red solo si está claro que falta información en los registros detallados.

#### ¿Cuándo es inútil una captura de red?

En algunos casos, capturar el tráfico de la red es inútil o simplemente una pérdida de tiempo. Estas son las situaciones más comunes:

* TLS habilitado: Por definición, el tráfico TLS está cifrado para que no se pueda capturar.
* Problemas de rendimiento: Los registros contienen toda la información necesaria para rastrear los problemas de rendimiento.
* Problemas de temporización (vuelva a intentar el tiempo, enquire_link_period, límite de rendimiento, etc.)
* Análisis y procesamiento de SR: Los registros detallados proporcionan mucho más contexto y una mejor presentación.
* Procesamiento de MO (respuestas automáticas, cuarentena).
* Errores que no implican tráfico SMPP real: Preparación de envíos, problemas de API de centros de mensajes, problemas de flujo de trabajo, etc.
