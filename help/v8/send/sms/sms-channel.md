---
title: Características del canal SMS
description: Conozca las características del canal SMS
feature: SMS
role: User
level: Intermediate
exl-id: abab6f15-43ea-42fc-817b-8dbd88df82f7
source-git-commit: 5c5d19c9b9b413bb630a4e5738c6697d2341665a
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 22%

---

# Características del canal SMS {#sms-channel}

>[!AVAILABILITY]
>
>Esta capacidad está disponible para todos los entornos de FDA de Campaign. Está **no** disponible para implementaciones de FDAC de Campaign. Esta documentación se aplica a Adobe Campaign 8.7.2 y versiones posteriores. Para cambiar del conector SMS heredado al nuevo, consulte esta [nota técnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>Para las versiones anteriores, lea la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## Tipos de SMS {#sms-types}

Al enviar SMS a través de un proveedor de SMS, se encontrará con 3 tipos diferentes de SMS:

* **SMS MT (móvil finalizado)**: Se trata de un SMS emitido por Adobe Campaign hacia los teléfonos móviles a través del proveedor de SMPP.
* **SMS MO (móvil original)**: Es un SMS que un móvil envía a Adobe Campaign a través del proveedor de SMPP.
* **SMS SR (informe de estado) o DR o DLR (recibo de envío)**: es un recibo de devolución enviado por el móvil a Adobe Campaign a través del proveedor de SMPP que indica que el SMS se ha recibido correctamente. Adobe Campaign también puede recibir SR indicando que el mensaje no se pudo entregar, a menudo con una descripción del error.

Debe distinguir entre reconocimientos (RESP PDU, parte del protocolo SMPP) y SR. Un SR es un tipo de SMS que se envía a través de la red de extremo a extremo, mientras que un reconocimiento es solo una confirmación de que una transferencia se ha realizado correctamente.

Tanto los reconocimientos como SR pueden almacenar en déclencheur los errores. Si se distingue entre los dos, se ayudará a solucionar problemas.

### Información transmitida por un SMS  {#sms-info}

Un SMS lleva más información que texto. Aquí hay una lista de lo que puede encontrar en un SMS:

* El texto está limitado a 140 bytes, lo que significa entre 70 y 160 caracteres en función de la codificación. Consulte [Codificación de texto SMS](#sms-text-encoding) a continuación para obtener detalles y limitaciones.
* Una dirección de destinatario, a veces denominada ADC o MSISDN (el nombre técnico para &quot;número de teléfono&quot;). Ese es el número del móvil que recibirá el SMS.
* Una dirección de remitente, que puede llamarse oADC o, a veces, id de remitente. Puede ser un número de teléfono (para uso diario), un código corto (cuando se envía a través de un proveedor) o un nombre (esta es una función opcional, en ese caso no puede responder al SMS).
* Un indicador que indica si el mensaje es un mensaje flash (un mensaje flash es una ventana emergente que no se almacena en la memoria)
* Un indicador que señala si se espera o no un SR.
* Una fecha de validez, después de la cual no se permite reintentar ningún equipo de red (no siempre presente o respetado).
* Campo data_coding, que indica la codificación del texto.

## Codificación de texto SMS {#sms-text-encoding}

>[!IMPORTANT]
>
>La codificación de SMS es un tema vasto y complejo con muchas trampas e implementaciones no conformes.

La primera regla es **póngase siempre en contacto con el proveedor SMPP en caso de problemas de codificación**. Solo ellos, tienen un conocimiento preciso de la codificación que admiten y reglas especiales que pueden aplicarse debido a las limitaciones en su plataforma técnica. Haga que comprueben lo que le envía y lo que le devuelve. Es el único camino para una interconexión exitosa y estable.

Los mensajes SMS utilizan una codificación especial de 7 bits, a menudo denominada codificación GSM7.  Wikipedia tiene [un buen artículo al respecto (GSM 03.38 en inglés)](https://en.wikipedia.org/wiki/GSM_03.38).

En el protocolo SMPP, el texto de GSM7 se expandirá a 8 bits por carácter para facilitar la resolución de problemas. El SMSC lo empaquetará en 7 bits por carácter antes de enviarlo al dispositivo móvil. Esto significa que el campo short_message del SMS puede tener hasta 160 bytes de longitud en el marco SMPP, mientras que está limitado a 140 bytes cuando se envía en la red móvil (el bit más significativo simplemente se descarta).

En caso de problemas de codificación, hay que comprobar algunos aspectos importantes:
* En primer lugar, asegúrese de saber qué caracteres pertenecen a cada codificación. El GSM7 es tristemente célebre por su compatibilidad parcial con los signos diacríticos (acentos). Especialmente en francés, donde é y è son parte de GSM7, pero ê, â o ï no lo son. Lo mismo se aplica al español.
* La C con cedilla (ç) solo está presente en mayúsculas en el alfabeto GSM7, pero algunos teléfonos la representan en minúsculas o en mayúsculas &quot;inteligentes&quot;: la recomendación general es evitarla por completo y eliminar la cedilla (sigue siendo muy legible en francés) o cambiar a UCS-2.
* **¡No use ASCII en los SMS!** a menos que el proveedor SMPP lo solicite explícitamente: Esta codificación desperdicia espacio porque tiene caracteres de 8 bits y menos cobertura que GSM7. Esta codificación puede ser necesaria para las redes CDMA (utilizadas en Norteamérica).
* Latin-1 no siempre es compatible. Compruebe la compatibilidad con su proveedor SMPP antes de intentar usar Latin-1.
* El conector Adobe Campaign no admite tablas de cambio de idioma nacional. Debe utilizar UCS-2 u otro data_coding en su lugar.
* UCS-2 y UTF-16 suelen mezclarse por teléfono. Esto es un problema para las personas que envían emojis y otros caracteres poco utilizados que no están presentes en UCS-2.
* Los teléfonos antiguos únicos no tienen glifos de fuentes para todos los caracteres UCS-2. Los teléfonos inteligentes más recientes tienden a ser capaces de mostrar caracteres raros con bastante facilidad, los teléfonos inteligentes más antiguos a menudo carecen de muchos emojis, y los teléfonos de funciones muy antiguos generalmente tienen soporte limitado a lo que es útil en la lengua nativa del país en el que se compraron. Si desea utilizar emoji o ASCII-art de algún tipo, pruébelo en una amplia variedad de teléfonos antes de enviarlo. La vista previa de Campaign no simula los glifos que faltan y muestra los símbolos que estén disponibles en el explorador web que muestra la vista previa.

El campo *data_coding* indica qué codificación se usa. Un problema importante es que el valor 0 significa *codificación SMSC predeterminada* en la especificación; en general, significa GSM7, pero no siempre es así. Compruebe con el proveedor SMPP qué codificación está asociada con data_coding = 0. Otros valores data_coding tienden a seguir la especificación, pero la única manera de estar seguros es consultar con el proveedor SMPP.

El tamaño máximo de un mensaje depende de su codificación. Esta tabla resume toda la información relevante:

| Codificación | Data_coding habitual | Tamaño del mensaje (caracteres) | Tamaño de la parte para SMS de varias partes | Caracteres disponibles |
|:-:|:-:|:-:|:-:|:-:|  
| GSM7 | 0 | 160 | 152 | Conjunto de caracteres básico GSM7 + extensión (los caracteres extendidos tienen 2 caracteres) |
| Latin-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode (varía de un teléfono a otro) |

## SMS de varias partes (SMS largos) {#multipart-sms}

Los SMS de varias partes (a menudo llamados SMS largos) son SMS que se envían en varias partes. Debido a limitaciones técnicas en el protocolo de red móvil, un SMS no puede superar los 140 bytes (consulte la sección Codificación de texto SMS a continuación para ver el número de caracteres que pueden caber en un SMS), por lo que los mensajes más largos deben dividirse.

Cada parte de un mensaje largo es un SMS individual. Estas partes viajan independientemente en la red y son montadas por el teléfono móvil receptor. Para gestionar correctamente los reintentos y los problemas de conectividad, Campaign envía las piezas en orden inverso y solicita un SR solo en la primera parte del mensaje (la que se envía la última); como el teléfono móvil solo muestra un mensaje cuando recibió la primera parte, los reintentos de partes adicionales no producirán duplicados en el teléfono móvil.

Se puede establecer el número máximo de SMS por mensaje por envío mediante la configuración Número máximo de SMS por mensaje en la plantilla de envíos. Los mensajes que superen este límite fallarán al enviar un mensaje de error con el motivo SMS demasiado largo.

Hay dos maneras de enviar SMS largos:

* UDH
* message_payload

UDH es la forma predeterminada y recomendada de enviar mensajes largos. En este modo, el conector divide el mensaje en varias PDU SUBMIT_SM con información UDH en ellas. Este protocolo es el que utilizan los propios teléfonos móviles, lo que significa que Campaign tiene el mayor control sobre la generación de mensajes, lo que le permite calcular exactamente cuántas partes se enviaron y cómo se dividieron.

*message_payload* es una forma de enviar el mensaje largo completo en una sola PDU SUBMIT_SM. El proveedor tendrá que dividirlo, lo que significa que es imposible para Campaign saber exactamente cuántas partes se han enviado. Algunos proveedores requieren este modo, utilícelo únicamente si no admiten UDH.

Consulte la descripción de los campos esm_class, short_message y message_payload de la PDU SUBMIT_SM anterior para obtener más detalles acerca del protocolo y los formatos.

>[!NOTE]
>
>Aunque Adobe Campaign admite UDH y message_payload para el envío, solo se admite message_payload para los SMS entrantes (MO).
