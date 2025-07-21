---
title: Configuración del envío de SMS
description: Obtenga información sobre cómo configurar un envío de SMS
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: c4d500ef-2339-491f-9ae2-9bfaf72088a9
source-git-commit: ea51863bdbc22489af35b2b3c81259b327380be4
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 15%

---

# Configuración del envío de SMS {#sms-settings}

>[!AVAILABILITY]
>
>Esta capacidad está disponible para todos los entornos de FDA de Campaign. Está **no** disponible para implementaciones de FDAC de Campaign. Esta documentación se aplica a Adobe Campaign 8.7.2 y versiones posteriores. Para cambiar del conector SMS heredado al nuevo, consulte esta [nota técnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>Para las versiones anteriores, lea la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

La configuración técnica necesaria para un envío SMS es:

* La cuenta externa SMPP para el enrutamiento de mensajes. [Más información](smpp-external-account.md#smpp-connection-settings)
* Configure la pestaña SMS. [Descubra cómo](#sms-tab)

Puede configurar todos estos elementos en una plantilla de envíos para evitar tener que realizar la configuración para cada creación de envíos SMS.

## Configuración de la pestaña SMS {#sms-tab}

![](assets/send_settings.png){zoomable="yes"}

Aquí está la información que necesita para rellenar este formulario. Cada campo se explica a continuación:

* **[!UICONTROL Sender address]**

  Este campo es opcional. Permite anular la dirección del remitente (oADC). El contenido de este campo se coloca en el campo *source_addr* de la PDU SUBMIT_SM.

  El campo está limitado a 21 caracteres por la especificación del SMPP, pero algunos proveedores pueden permitir valores más largos. Tenga en cuenta también que en algunos países se pueden aplicar restricciones muy estrictas (longitud, contenido, caracteres permitidos, etc.), por lo que es posible que tenga que volver a comprobar que el contenido que coloca aquí es legal. Tenga especial cuidado al utilizar campos personalizados.

  Si este campo se deja vacío, se utilizará el valor del campo Source number definido en la cuenta externa. Si ambos valores están vacíos, el campo *source_addr* se dejará vacío.

* **[!UICONTROL Service or program ID]**

  >[!NOTE]
  >
  >No se recomienda utilizar esta función. Los parámetros opcionales del SMPP proporcionan una implementación mucho más flexible.
  >
  >Ambas funciones no se pueden utilizar al mismo tiempo.

  En combinación con la configuración de cuenta externa correspondiente, permite enviar un parámetro opcional con cada MT. Este campo define la parte de valor del TLV.

* **[!UICONTROL Transmission mode]**

  Este campo indica el tipo de SMS que desea transferir: mensajes normales o flash, almacenados en el móvil o en la tarjeta SIM. Esta configuración se transmite en el campo opcional dest_addr_subunit de la PDU SUBMIT_SM.

   * **Flash** establece el valor en 1. Envía un mensaje flash que aparece en el dispositivo móvil y no se almacena en la memoria.
   * **Normal** establece el valor en 0. Envía un mensaje normal.
   * **Guardar en un móvil** establece el valor en 2. Le dice al teléfono que almacene el SMS en la memoria interna.
   * **Guardar en un terminal** establece el valor en 3. Le dice al teléfono que almacene el SMS en la tarjeta SIM.

* **[!UICONTROL Priority, Communication type]**

  El conector SMPP extendido ignora estos campos.

* **[!UICONTROL Maximum number of SMS per message]**

  Esta configuración solo funciona si la configuración Carga útil del mensaje está deshabilitada (consulte en la configuración de la cuenta externa para obtener más información). Si el mensaje requiere más SMS que este valor, se activará un error.

  El protocolo SMS limita los SMS a 255 partes, pero algunos teléfonos móviles tienen problemas para reunir mensajes largos con más de 10 partes, aproximadamente (el límite depende del modelo exacto). Si quieres estar a salvo, no pases de 5 partes por mensaje.

  Debido a cómo funcionan los mensajes personalizados en Adobe Campaign, el tamaño de los mensajes puede variar, por lo que tener muchos mensajes muy largos podría aumentar considerablemente el coste de envío: establecer un valor razonable ayuda a controlar estos costes.

  Si se especifica 0, se desactiva el límite.

* **[!UICONTROL Optional SMPP parameters (TLV)]**
Puede especificar campos adicionales para enviarlos como parámetros SMPP opcionales (TLV). Estos campos adicionales se envían con cada MT y los campos personalizados permiten tener valores diferentes para cada MT.
En la tabla se enumeran los parámetros opcionales que se envían con cada mensaje. Las columnas contienen la siguiente información:
   * **Etiqueta**: se trata de una etiqueta opcional de forma libre. No se transmite al proveedor. Puede proporcionar una descripción textual del parámetro.
   * **Tag**: el valor de la etiqueta, ya sea en formato decimal (p. ej., 12345) o hexadecimal con prefijo 0x (p. ej., 0x12ab). Las etiquetas pueden ir entre 0 y 65535. Solicite al proveedor de servicios SMPP las etiquetas compatibles.
   * **Value**: valor que se enviará en el parámetro opcional. Este es un campo personalizado.
   * **Formato**: codificación utilizada para el parámetro. Puede seleccionar cualquier codificación de texto compatible o los formatos binarios más comunes. Solicite al proveedor de servicios SMPP el formato requerido.
   * **Longitud máxima**: Número máximo de bytes para este parámetro. Esto se ignora para los campos binarios, ya que estos tienen un tamaño fijo.

* **[!UICONTROL Using binary formats for TLV]**

  Campaign admite el envío de TLV en formato binario. El binario se limita a enviar números.

  Dado que los campos personalizados siempre muestran texto, el campo personalizado debe contener una representación decimal del número (cualquier cadena es correcta, siempre que solo contenga dígitos). Los valores pueden estar firmados o no, el motor de personalización solo los convierte en la representación binaria correcta.

  Cuando se utilizan formatos binarios, los valores especiales &#39;&#39; (cadena vacía), &#39;null&#39; y &#39;undefined&#39; desactivan el campo completamente sin generar un error. En estos 3 casos especiales, la etiqueta no se pasa en absoluto. Esto permite pasar un TLV específico solo para algunos mensajes cuando se utiliza JavaScript cuidadosamente diseñado en el campo de personalización.

  >[!NOTE]
  >
  >Los formatos binarios siempre se codifican en forma de big endian.

