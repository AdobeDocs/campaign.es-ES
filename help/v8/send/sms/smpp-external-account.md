---
title: Configuración de cuenta externa de SMPP
description: Obtenga información sobre cómo configurar la cuenta externa de SMPP
feature: SMS
role: User
level: Intermediate
exl-id: 1f941b35-c7e0-4e8c-b6e5-a1a3e5354483
source-git-commit: 3ac2976839f084761ba56647b282062d8d457ff2
workflow-type: tm+mt
source-wordcount: '3650'
ht-degree: 27%

---

# Configuración de cuenta externa de SMPP {#smpp-external-account}

Adobe Campaign utiliza el protocolo SMPP para enviar SMS a un proveedor de servicios.

El conector SMS en Adobe Campaign proporciona muchas opciones para adaptar su comportamiento a fin de ser compatible con la mayoría de los proveedores de SMPP, que tienden a desviarse un poco de la especificación oficial.

>[!IMPORTANT]
>
>* Adobe Campaign es compatible con la versión 3.4 del protocolo SMPP.
>
>* La configuración de una conexión con un nuevo proveedor puede requerir algunas habilidades técnicas, conocimientos de TCP, representación binaria, hexadecimal y codificaciones de texto. También requerirá una cooperación activa con el proveedor.

El equipo de red en el lado del proveedor de servicios SMS suele conocerse como SMSC.

## Configuración de conexión {#smpp-connection-settings}

![](assets/smpp_connection_settings.png){zoomable="yes"}

Estos son los parámetros y su función necesarios para configurar la conexión:

* **Nombre de implementación SMSC**: establece el nombre de la implementación SMSC. Debe configurarse con el nombre de su proveedor. La función de este campo se describe en la sección de administración de errores del SMPP.
* **Servidor**: El nombre DNS o la dirección IP del servidor al que se va a conectar.
* **Puerto**: El puerto TCP al que se va a conectar.
* **Cuenta**: Inicio de sesión de la conexión. Pasado en el campo system_id de la PDU BIND.
* **Contraseña**: Contraseña de la conexión SMPP. Pasado en el campo de contraseña de la PDU BIND.
* **Tipo de sistema**: valor pasado en el campo system_type de la PDU BIND. Algunos proveedores necesitan un valor específico aquí.
* **Número de conexiones secundarias MTA**: Esto define cuántas conexiones se abren por subproceso de envío.
El número total de conexiones se puede calcular mediante esta fórmula:
  *Conexiones totales = Número de procesos SMS * número de subprocesos de envío * número de conexiones secundarias MTA*

   * El número de procesos SMS suele ser 1. En algunas instancias de alto rendimiento, es posible que se inicien varios procesos SMS en paralelo.
   * El número de subprocesos de envío está establecido en serverConf (configuración sendingThreads). El valor predeterminado es 1.
   * El número de conexiones secundarias MTA es esta configuración en la cuenta externa.

  Con los valores predeterminados, esta configuración establece directamente el número de conexiones.

En **modo transceptor**, este es el número total de conexiones.

En **modo transmisor+receptor**, define el número de pares transmisor+receptor (un par = un transmisor + un receptor).
No hay forma de cambiar el equilibrio entre transmisores y receptores.

* **Enviar mensajes mediante un proceso dedicado**:
Para Adobe Campaign v8.7.2 y posterior, esta opción siempre debe estar habilitada. Tiene muchos impactos en la forma en que se procesan los mensajes.
* **Modo de conexión SMPP**:
Configure la conexión en modo transceptor o en modo separado transmisor+receptor.
   * Transmisor+receptor (o TX+RX): se utilizan dos conexiones TCP independientes para transmitir y recibir mensajes.
   * Transceptor (o TRX): se utiliza una sola conexión TCP para transmitir y recibir mensajes.
* **Usar parámetros diferentes para el receptor**:
Disponible solo en modo transmisor+receptor.
Cuando la casilla está desmarcada, se utiliza la misma configuración para el transmisor y el receptor. Cuando se marca la casilla, la configuración estándar se aplica solo al transmisor, mientras que la configuración del receptor se aplica solo al receptor.
* **Servidor receptor, puerto, cuenta, contraseña, tipo de sistema**
Esta configuración se aplica al receptor cuando se encuentra en modo transmisor+receptor. Funcionan como la parte del transmisor, ver arriba [más detalles](#smpp-connection-settings).
* **Habilite seguimientos detallados del SMPP en el archivo de registro**
Cuando se habilita, se generan registros adicionales en el archivo de registro. Esto resulta muy útil para solucionar problemas, pero debe mantenerse deshabilitado en instancias de alto rendimiento si no se requiere solución de problemas.

## Configuración de canal SMPP {#smpp-channel-settings}

![](assets/smpp_channel_settings.png){zoomable="yes"}

### Autorizar transliteración de caracteres {#smpp-transliteration}

La transliteración es el proceso de encontrar caracteres equivalentes a los que faltan. Por ejemplo, el carácter francés &quot;ê&quot; (e con acento circunflejo) no aparece en la codificación GSM, pero se puede reemplazar por &quot;e&quot; sin afectar demasiado a la legibilidad.

Cuando esta casilla no está marcada, la codificación de texto fallará si no puede codificar la cadena exactamente como está.

Cuando esta casilla está activada, la codificación de texto intentará convertir la cadena a una versión aproximada en lugar de generar errores. Si algunos caracteres no tienen equivalente en la codificación de destinatario, la codificación de texto fallará.

Consulte la [Definición de una asignación específica de la configuración de codificaciones](#mapping-encodings) para obtener una explicación más general del proceso de codificación.

### Número de origen

Define la dirección de origen predeterminada para los mensajes. Esta configuración solo se aplica si el número de origen se ha dejado vacío en la entrega. De forma predeterminada, el campo de número de origen no se pasa, por lo que el proveedor lo sustituirá por el código corto.

Esto habilita la función de anulación de dirección de remitente/oADC.

### TON/NPI de origen, TON de destino/NPI

TON (tipo de número) y NPI (indicador del plan de numeración) (descritos en la sección 5.2.5 de la especificación del SMPP 3.4). Estos valores deben ajustarse a lo que el proveedor necesite.

Se transmiten tal cual en los campos source_addr_ton, source_addr_npi, dest_addr_ton y dest_addr_npi de la PDU SUBMIT_SM.

### Tipo de servicio

Este campo se transmite tal cual en el campo service_type de la PDU SUBMIT_SM. Configure esto según lo que necesite el proveedor.

## Rendimiento y retrasos {#smpp-delays}

![](assets/smpp_throughput.png){zoomable="yes"}

Esta configuración controla todos los aspectos de tiempo del canal SMPP. Algunos proveedores requieren un control muy preciso de la velocidad de mensajes, la ventana y los tiempos de reintento, por lo que esta configuración debe establecerse en valores que coincidan con la capacidad del proveedor y las condiciones indicadas en su contrato.

### Ventana de envío

La ventana es el número de PDU SUBMIT_SM que se pueden enviar sin esperar una SUBMIT_SM_RESP coincidente.

Ejemplo de una transmisión con una ventana máxima de 4:

![](assets/sms_sending_window.png){zoomable="yes"}

La ventana ayuda a aumentar el rendimiento cuando el vínculo de red tiene una latencia alta. El valor de la ventana debe ser al menos el número de SMS/s multiplicado por la latencia del vínculo (en segundos), de modo que el conector nunca está esperando a SUBMIT_SM_RESP antes de enviar el siguiente mensaje.

Si la ventana es demasiado grande, puede enviar más mensajes duplicados en caso de problemas de conexión (caso poco frecuente). Además, la mayoría de los proveedores tienen un límite muy estricto para la ventana y rechazan los mensajes que sobrepasan el límite.

Calcular la fórmula óptima de la ventana de envío:

Mida la latencia máxima entre SUBMIT_SM y SUBMIT_SM_RESP.
Multiplicar este valor (en segundos) al rendimiento máximo de MT: esto proporcionará el valor óptimo de la ventana de envío.
Ejemplo: Si tiene 300 SMS/s configurados en el rendimiento máximo de MT y hay una latencia de 100 ms entre SUBMIT_SM y SUBMIT_SM_RESP en promedio, el valor óptimo sería 300×0.1 = 30.

Cuando tenga dudas, prefiera una ventana más grande para evitar problemas de rendimiento.

### Rendimiento máximo de MT

Número máximo de MT por segundo y por conexión. Esta configuración se aplica estrictamente y el MTA nunca insertará mensajes más rápido que este límite. Resulta útil para los proveedores que requieren una limitación precisa.

Para conocer el límite de rendimiento total, multiplique este número por el número total de conexiones (consulte la fórmula anterior).

0 significa que no hay límite, el MTA enviará MT lo más rápido posible.

En general, se recomienda mantener esta configuración por debajo de 1000, ya que es imposible garantizar un rendimiento preciso por encima de este número, a menos que se haya realizado una evaluación adecuada de la arquitectura final y se haya solicitado específicamente al proveedor de SMPP. Puede ser mejor aumentar el número de conexiones para superar los 1000 MT/s.

### Tiempo antes de la reconexión

Cuando se pierde la conexión TCP, el conector esperará este número de segundos antes de intentar realizar una conexión.

### Período de caducidad del MT

Tiempo de espera entre SUBMIT_SM y su correspondiente SUBMIT_SM_RESP. Si el RESP no se recibe a tiempo, el mensaje se considerará fallido y se aplicará la política de reintentos global del MTA.

### Tiempo de espera de vínculo

Tiempo de espera entre el intento de conexión TCP y la respuesta BIND_*_RESP. Cuando se agota el tiempo de espera, la conexión se cierra mediante el conector de Campaign y esperará tiempo antes de volver a conectarse antes de intentarlo de nuevo.

### período enquire_link

enquire_link es un tipo especial de PDU enviado para mantener la conexión viva. Este período es en segundos. El conector de campaña solo envía enquire_link cuando la conexión está inactiva para conservar el ancho de banda. Si no se recibe ningún RESP después de dos veces este período, la conexión se considerará muerta y se activará un proceso de reconexión.

## Mapeo de codificaciones {#mapping-encodings}

Consulte la [sección de codificación de texto SMS](sms-channel.md#sms-text-encoding) para obtener detalles sobre la codificación de texto.

Esta configuración permite definir una asignación de codificación personalizada, diferente de la especificación. Podrá declarar una lista de codificaciones, junto con su valor data_coding. El MTA intentará codificar utilizando la primera codificación de la lista; si falla, intenta utilizar la siguiente codificación en la lista, etc. Si no se puede utilizar ninguna codificación para codificar el mensaje, se producirá un error. Una vez encontrada la codificación, el MTA creará la PDU SUBMIT_SM con el texto codificado y el campo data_coding establecido con el valor especificado en la tabla.

El orden de los elementos de la tabla es importante: las codificaciones se prueban de arriba abajo. Debe colocar la codificación más barata o recomendada en la parte superior de la lista, seguida de codificaciones más y más costosas (o menos deseables).

Tenga en cuenta que la UCS-2 nunca fallará, ya que puede codificar todos los caracteres admitidos en Campaign. Tenga en cuenta que la longitud máxima de un SMS UCS-2 es mucho menor (solo 70 caracteres).

También puede utilizar esta configuración para forzar que una codificación específica se utilice siempre declarando solo 1 línea en la tabla de asignación.

La asignación predeterminada que se utiliza cuando la casilla de verificación no está marcada equivale a la siguiente tabla:

| data_coding | Codificación |
|:-:|:-:|
| 0 | GSM |
| 8 | UCS-2 |

Esto significa que el MTA intentará codificar el mensaje en GSM, si lo consigue, lo enviará con data_coding establecido en 0.

Si el mensaje no se puede codificar en GSM, se codificará en UCS-2 y establecerá data_coding en 8.

## Especificaciones de SMSC {#smsc-specificities}

![](assets/smsc_specificities.png){zoomable="yes"}

### Activar message_payload

Cuando no se selecciona, los SMS largos se dividen por el MTA y se envían en varias PDU SUBMIT_SM con UDH. El mensaje será recompuesto por el teléfono móvil según los datos UDH.

Cuando se selecciona, se envían SMS largos en una PDU SUBMIT_SM, colocando el texto en el campo opcional message_payload (consulte la especificación SMPP para obtener detalles sobre esto).

Si esta función está habilitada, Campaign no podrá contar las partes del SMS de forma individual: todos los mensajes se contarán como enviados en una parte.

### Enviar el número de teléfono completo

Cuando esta casilla de verificación no está activada, solo se envían dígitos del número de teléfono al proveedor (campo destination_addr del campo SUBMIT_SM). Este es el comportamiento predeterminado porque el indicador de número internacional (normalmente un prefijo +) se reemplaza por los campos TON y NPI en el SMPP.

Cuando se marca la casilla de verificación, el número de teléfono se envía tal cual, sin preprocesamiento (y espacios potenciales, + prefijo o signos de almohadilla/asterisco).

Esta función también afecta al comportamiento de la función de cuarentena de respuesta automática: cuando la casilla de verificación no está marcada, se agrega un prefijo + a los números de teléfono insertados en la tabla de cuarentena para compensar la eliminación del prefijo + del número de teléfono por el propio protocolo SMPP.

### Enlazar TON/NPI

TON (tipo de número) y NPI (indicador del plan de numeración) (descritos en la sección 5.2.5 de la especificación del SMPP 3.4). Estos valores deben ajustarse a lo que el proveedor necesite.

Se transmiten tal cual en los campos addr_ton y addr_npi de la PDU BIND.

### Intervalo de direcciones

Se envía tal cual en el campo address_range del BIND PDU. Este valor debe ajustarse a lo que necesite el proveedor.

### Cuenta de reconocimiento de ID no válida

Limita el número de &quot;ID de mensaje no válido&quot; DELIVER_SM_RESP que se puede enviar para un único SR. **Esto solo debe usarse para solucionar problemas como solución alternativa** y se establece en 0 en condiciones normales.

Explicación detallada: supongamos que establece esta configuración en 2:

* El proveedor envía un SR (DELIVER_SM) con el ID &quot;1234&quot;
* No se encontró el ID &quot;1234&quot; en la base de datos
* El conector cuenta 1 error &quot;ID no válido&quot; para ese ID, por lo que envía DELIVER_SM_RESP con el código de error &quot;ID de mensaje no válido&quot; (comportamiento normal).
* El proveedor reintenta el mismo SR con el ID &quot;1234&quot;
* El ID &quot;1234&quot; aún no se encuentra en la base de datos
* El conector cuenta 2 errores &quot;ID no válido&quot; para ese ID, por lo que envía DELIVER_SM_RESP &quot;OK&quot;, aunque no se haya procesado correctamente.

Esta función está diseñada para vaciar los búferes SR en el lado del proveedor cuando un SR no válido bloquea los mensajes legítimos que no se pueden procesar.

Si este campo se establece en 0, se deshabilita el mecanismo y siempre se devuelve &quot;ID de mensaje no válido&quot;; este es un comportamiento normal.

Al establecer este campo en 1, el conector siempre responde &quot;OK&quot; aunque el ID no sea válido. Esto debe establecerse en 1 solo se utiliza bajo supervisión para la resolución de problemas y durante el mínimo tiempo, por ejemplo, para recuperarse de un problema del lado del proveedor.

### Extracción del regex del ID en el SR

El formato SR no se aplica estrictamente en la especificación de protocolo SMPP. Es solo una recomendación descrita en el apéndice B del pliego de condiciones. Debido a esto, algunos implementadores SMPP dan un formato diferente a este campo, por lo que Campaign necesita una forma de extraer el campo correcto.

De forma predeterminada, captura hasta 10 caracteres alfanuméricos después de &quot;id:&quot;.

El regex debe tener exactamente un grupo de captura (una parte que esté entre paréntesis). Los paréntesis deben rodear la parte que corresponde al ID. El formato regex es PCRE.

Al ajustar esta configuración, asegúrese de incluir el mayor contexto posible para evitar activaciones falsas. Si hay prefijos específicos (como &quot;id:&quot; en el estándar), inclúyalos en la regex. Utilice también delimitadores de palabras (\b) tanto como sea posible para evitar capturar texto en medio de una palabra.

No incluir suficiente contexto en la regex puede introducir un pequeño defecto de seguridad: el contenido real del mensaje se puede incluir en el SR, por lo que si solo coincide con un formato de ID específico sin contexto (por ejemplo, un UUID), puede que esté analizando el contenido de texto real (por ejemplo, un UUID incrustado en el campo de texto) en lugar del ID.

### Regex de extracción del estado en el SR

Esta regex captura el estado del campo de texto de los mensajes SR.

De forma predeterminada, captura entre 5 y 15 caracteres después de &quot;stat:&quot;.

El regex debe tener **exactamente un grupo de captura** (una parte incluida entre paréntesis). Los paréntesis deben rodear la parte que corresponde al estado. El formato regex es PCRE.

### Regex aplicado para determinar el estado correcto

Esta regex se aplica sobre el resultado de la regex anterior (&quot;Extracción de la regex del estado&quot;). Si la regex coincide, el mensaje se considera correcto.

De forma predeterminada, coincide con todo lo que comienza con &quot;DELIV&quot;. Coincide con el valor estándar &quot;DELIVRD&quot;.

### Regex aplicado para determinar el estado de error

Esta regex se aplica sobre el resultado de la regex anterior (&quot;Extracción de la regex del estado&quot;). Si la regex coincide, el mensaje se considera erróneo.

De forma predeterminada, coincide con todos los estados de error descritos en la especificación.

### Regex de extracción del código de error en el SR

Esta regex captura el código de error del campo de texto de los mensajes SR.

Los códigos de error se pueden clasificar en la calificación del registro de envío.

De forma predeterminada, captura 3 caracteres después de &quot;err:&quot;.

### Formato de ID en reconocimiento MT

Esto indica el formato del ID devuelto en el campo message_id de la PDU SUBMIT_SM_RESP.

* **No modificar**: El ID se almacena tal cual en la base de datos, como texto con codificación ASCII. No hay ningún procesamiento previo ni filtrado.
* **Número decimal** : Se espera que el ID sea un número decimal en formato ASCII. Cuando se utiliza este ajuste, se eliminan los espacios iniciales y finales y los ceros al inicio.
* **Número hexadecimal**: Se espera que el ID sea un número hexadecimal en formato ASCII, sin 0x inicial ni h final. El ID se convierte a continuación en un número decimal antes de almacenarse en la base de datos.
* **Cadena hexadecimal**: Se espera que el ID sea un texto con codificación ASCII que es en sí mismo una cadena de bytes codificados como hexadecimales. Por ejemplo, en la PDU encontrará 0x34 0x31 0x34 0x32 0x34 0x33, que se traduce como ASCII &quot;414243&quot;; entonces esta cadena se descodifica como una cadena hexadecimal de bytes, y obtiene &quot;ABC&quot; como resultado: almacenará el ID &quot;ABC&quot; en la base de datos.

### Formato de ID en el SR

Indica el formato del ID capturado por la regex de extracción del ID en el SR. Los valores tienen el mismo significado y el mismo comportamiento que el formato de MT anterior.

### ID de SR o código de error en el campo opcional

Si se selecciona, el contenido de los campos opcionales se anexará al texto procesado por las expresiones regulares anteriores. El texto tendrá el formato &quot; 0xTAG:VALUE&quot;, siendo 0xTAG el valor hexadecimal de 4 dígitos de la etiqueta en mayúsculas (por ejemplo, 0x002E).

Por ejemplo, es posible que desee capturar el ID en el campo recipient_message_id. Para ello, active esta casilla de verificación y el siguiente texto se agrega al estado:

0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739

En este ejemplo, 0x001E es la etiqueta del campo opcional y UUID es el valor del campo.

Para capturar este valor, ahora puede establecer la siguiente regex en la regex de Extracción del ID en el campo SR:

\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})\b

>[!IMPORTANT]
>
>Solo puede capturar campos opcionales que tengan valores de texto de 8 bits (ASCII/UTF-8). Concretamente, los campos binarios no se pueden capturar de forma fiable con el sistema regex actual.

### ID de SR o código de error en el campo de texto

Si se selecciona, el campo Texto: se mantendrá durante el procesamiento del texto de estado del SR. Esto resulta útil si el proveedor coloca datos importantes en este campo, como el ID o el estado. Normalmente, este campo se puede descartar de forma segura, ya que puede contener texto con una codificación que no sea ASCII e interrumpir el procesamiento de regex.

Si se habilita esta opción, puede que se produzca un error de seguridad muy pequeño si la regex de extracción del ID en el campo SR no es lo suficientemente específico: el contenido del campo Texto puede analizarse como un ID y un atacante puede utilizarlo para insertar ID falsificados, lo que puede conducir a una situación de denegación de servicio parcial.

### Etiqueta de ID de servicio

Permite añadir un TLV personalizado. Este campo establece la etiqueta, pasada como un valor hexadecimal en el formato **0x1234**.

El valor del TLV personalizado debe configurarse en la entrega en el campo &quot;ID de servicio o programa&quot; en los parámetros avanzados de la entrega. El valor se envía como texto codificado con UTF-8.

Esta configuración solo permite añadir una opción TLV por mensaje.

>[!NOTE]
>
>Esta opción está reemplazada por la configuración mucho más potente de **Parámetros SMPP opcionales (TLV)** en los parámetros de envío. Estas funciones son mutuamente excluyentes y no se pueden utilizar al mismo tiempo.

### Habilitar TLS en SMPP

Si se habilita, todas las conexiones al SMSC se cifrarán con TLS.

### Verificación del certificado

* **Verificación completa del certificado**: compruebe el certificado TLS y el nombre de host remoto al conectarse. Este valor proporciona el nivel más alto de seguridad.
* **Omitir la comprobación del nombre de host**: compruebe el certificado TLS remoto, pero no compruebe si el nombre de host remoto coincide. Reduce ligeramente la seguridad.
* **Omitir la verificación del certificado**: no compruebe el certificado TLS en absoluto. La conexión aún está cifrada, pero es vulnerable a ataques de intermediarios. Reduce mucho la seguridad.

## Tráfico entrante {#incoming-traffic}

![](assets/incoming_traffic.png){zoomable="yes"}

### Parámetros SMPP opcionales (TLV) en MO

Campaign permite recibir 3 campos adicionales en MO (tabla nms:inSms): SMS vinculados, alias y cuenta grande. Con el conector SMPP, estos campos se pueden rellenar con datos procedentes de cualquier parámetro SMPP opcional (TLV), con cualquier formato común.

Para cada campo, se puede establecer la etiqueta asociada, así como su formato. Solicite esta información al proveedor de servicios SMPP.

* Etiqueta: el valor de la etiqueta, ya sea en formato decimal (por ejemplo, 12345) o hexadecimal con prefijo 0x (por ejemplo, 0x12ab). Las etiquetas pueden ir entre 0 y 65535.
* Formato: formato utilizado para el valor. Los valores binarios son todos valores binarios con signo big endian. Para los campos de texto, elija la codificación utilizada por el proveedor SMPP.

### Respuesta automática enviada al MO

Esta función permite responder texto rápidamente a MO y controlar listas negras de código corto.

Las columnas *Keyword* y *Short code* definen condiciones para almacenar en déclencheur la respuesta automática: si ambos campos coinciden, se envía el MO y se activa la acción adicional. Para especificar un comodín, deje el campo vacío. La palabra clave coincide con la primera palabra alfanumérica del texto MO, omitiendo la puntuación y los espacios iniciales. Significa que el campo Palabra clave no puede contener espacios y debe ser una sola palabra.

Además, la configuración de *Palabra clave* es un prefijo. Por ejemplo, si especifica &quot;AD&quot;, coincidirá con &quot;AD&quot;, &quot;ADAPT&quot; y &quot;ADOBE&quot;. Si tiene varias palabras clave con un prefijo común, preste atención al orden, las palabras clave se procesan de arriba a abajo.

La columna *Respuesta* es el texto que se va a responder. No hay personalización disponible en este campo, el texto de respuesta siempre es el mismo. Si deja este campo vacío, no se responderá ningún mensaje, pero la acción adicional se activará de todos modos.

La columna de acción *Additional* proporciona una acción adicional que hacer cuando coinciden palabra clave y código corto (el código corto vacío coincide con todos los códigos cortos). Actualmente, puede enviar a cuarentena o eliminar de la cuarentena. Si especifica una acción adicional y deja vacío el campo de respuesta, la acción se ejecutará pero no se enviará ninguna respuesta. La cuarentena solo se aplica al código corto especificado o a todos los códigos cortos si el campo se deja vacío.

Todas las entradas de la tabla se procesan en el orden especificado, hasta que una regla coincida. Si varias reglas coinciden con un MO, solo se aplicará la regla superior.

>[!NOTE]
>
>La configuración **enviar número de teléfono completo** afecta el comportamiento del mecanismo de cuarentena de respuesta automática: si enviar número de teléfono completo no está marcado, el número de teléfono puesto en cuarentena estará marcado con un signo más (&quot;+&quot;) para que sea compatible con el formato de número de teléfono internacional.

>[!NOTE]
>
>En una arquitectura intermediaria, la aplicación de la respuesta automática para el conector del SMPP ampliado requiere añadir acceso de escritura para el operador medio en la carpeta de cuenta externa.

>[!IMPORTANT]
>
>Tenga cuidado con las codificaciones en las respuestas automáticas, especialmente al copiar y pegar. El software de procesamiento de textos tiende a agregar un formato adicional, como agregar espacios de no separación o cambiar comillas a los apóstrofos.
