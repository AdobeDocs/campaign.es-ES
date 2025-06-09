---
product: campaign
title: Definición del contenido interactivo en Adobe Campaign
description: Aprenda a definir contenido de correo electrónico dinámico e interactivo con AMP en Adobe Campaign
feature: Email Design
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 2a8b900b-ce0a-41b1-b4e4-b024ca93052e
source-git-commit: 3d562aab2f19b84aad8b484768bf19648145feb3
workflow-type: tm+mt
source-wordcount: '1356'
ht-degree: 99%

---

# Definición del contenido interactivo{#defining-interactive-content}

Adobe Campaign le permite usar el formato [AMP interactivo del correo electrónico](https://amp.dev/es/about/email/), que permite enviar correos electrónicos dinámicos en ciertas condiciones.

Con AMP para correo electrónico, puede:
* Probar el envío de correos electrónicos AMP a direcciones específicas correctamente configuradas.
* Enviar correos electrónicos AMP a las direcciones de Gmail o Mail.ru después de registrarse con los proveedores correspondientes.

Para obtener más información acerca de la prueba y el envío de correos electrónicos AMP, consulte [esta sección](#targeting-amp-email).

Esta función está disponible a través de un paquete dedicado en Adobe Campaign. Según los permisos y el modelo de implementación, puede instalar este paquete o ponerse en contacto con Adobe para que se lo instalen.

## Acerca de AMP para correo electrónico {#about-amp-for-email}

Utilice el nuevo formato de **AMP para correo electrónico** para incluir componentes de AMP en los mensajes y mejorar la experiencia de correo electrónico con un contenido enriquecido y procesable. Con la funcionalidad moderna de la aplicación disponible directamente en los correos electrónicos, los destinatarios pueden interactuar dinámicamente con el contenido del mensaje.

Por ejemplo:
* Los correos electrónicos escritos con AMP pueden contener elementos interactivos como carruseles de imágenes.
* El contenido permanece actualizado en el mensaje.
* Los destinatarios pueden responder a un formulario sin salir de su bandeja de entrada.

AMP para correo electrónico es compatible con los correos electrónicos existentes. La versión AMP del mensaje está incrustada en el correo electrónico como una nueva parte MIME, además del HTML y/o el texto sin formato, lo que garantiza la compatibilidad entre todos los clientes de correo electrónico.

Para obtener más información sobre la AMP para los requisitos y especificaciones de formato de correo electrónico, consulte la [documentación para desarrolladores de AMP](https://amp.dev/documentation/guides-and-tutorials/learn/email-spec/amp-email-format/?format=email).

![](assets/do-not-localize/how-to-video.png) [Descubra esta función en vídeo](#amp-email-video)

## Pasos clave para utilizar AMP para correo electrónico con Adobe Campaign {#key-steps-to-use-amp}

Para probar y enviar correctamente un correo electrónico de AMP con Adobe Campaign, siga los pasos a continuación:
1. Cree un correo electrónico y su contenido de AMP en Adobe Campaign. Consulte [Creación de contenido de correo electrónico de AMP con Adobe Campaign](#build-amp-email-content).
1. Asegúrese de seguir todos los requisitos de envío de los proveedores de correo electrónico que admiten el formato AMP. Consulte [Requisitos de AMP para envío por correo electrónico](#amp-for-email-delivery-requirements).
1. Al definir el objetivo, asegúrese de seleccionar los destinatarios que podrán visualizar el formato AMP. Consulte [Objetivización de un correo electrónico AMP](#targeting-amp-email).

   >[!NOTE]
   >
   >Actualmente, solo puede enviar correos electrónicos AMP a [direcciones de correo electrónico específicas](#testing-amp-delivery-for-selected-addresses) (para fines de prueba) o después de [registrarse](#delivering-amp-emails-by-registering) en los clientes de correo electrónico admitidos.

1. Envíe el correo electrónico como lo haría normalmente. Consulte [Envío de un correo electrónico de AMP](#sending-amp-email).

## Creación de contenido de correo electrónico AMP en Adobe Campaign {#build-amp-email-content}

Para generar un correo electrónico con el formato AMP, siga los pasos a continuación.

>[!IMPORTANT]
>
>Asegúrese de seguir las especificaciones y los requisitos de AMP para correo electrónico detallados en la [documentación para desarrolladores de AMP](https://amp.dev/documentation/guides-and-tutorials/learn/email_fundamentals/?format=email). También puede consultar las [prácticas recomendadas de AMP para correo electrónico](https://amp.dev/documentation/guides-and-tutorials/develop/amp_email_best_practices/?format=email).

1. Al crear el envío por correo electrónico, seleccione cualquier plantilla.

   >[!NOTE]
   >
   >Una plantilla de AMP específica contiene un ejemplo de las capacidades principales que puede utilizar: lista de productos, carrusel, doble inclusión, encuesta y solicitud de servidor avanzada.

1. Seleccione la pestaña **[!UICONTROL AMP content]**.

   ![](assets/amp_tab.png)

1. Edite el contenido de AMP para adaptarlo a sus necesidades.

   >[!NOTE]
   >
   >Para obtener más información sobre la creación del primer correo electrónico de AMP, consulte la [documentación para desarrolladores de AMP](https://amp.dev/documentation/guides-and-tutorials/start/create_email/?format=email).

   Por ejemplo, puede utilizar el componente de lista de productos de la plantilla de AMP y mantener una lista de productos de un sistema de terceros, o incluso dentro de Adobe Campaign. Siempre que se ajusta un precio u otro elemento, se refleja automáticamente cuando los destinatarios abren el correo electrónico desde su buzón.

1. Personalice el contenido de AMP según sea necesario, como lo haría normalmente con el formato HTML en Adobe Campaign, con campos y bloques de personalización.

   ![](assets/amp_tab_perso.png)

1. Una vez finalizado el proceso de edición, seleccione todo el contenido de AMP, cópielo y péguelo en el [validador basado en web de AMP](https://validator.ampproject.org) o en un sitio web similar.

   >[!NOTE]
   >
   >Asegúrese de seleccionar **AMP4 EMAIL** en la lista desplegable de la parte superior de la pantalla.

   ![](assets/amp_validator.png)

   Los errores se marcan en la línea.

   >[!NOTE]
   >
   >El editor AMP de Adobe Campaign no está diseñado para validar contenidos. Utilice un sitio web externo como el [validador basado en web de AMP](https://validator.ampproject.org) para comprobar si el contenido es correcto.

1. Realice las modificaciones necesarias hasta que el contenido de AMP pase la validación.

   ![](assets/amp_validator_pass.png)

1. Para previsualizar el contenido, copie y pegue el contenido validado en [AMP Playground](https://playground.amp.dev) o un sitio web similar.

   >[!NOTE]
   >
   >Asegúrese de seleccionar **AMP for Email** en la lista desplegable de la parte superior de la pantalla.

   ![](assets/amp_playground.png)

   >[!NOTE]
   >
   >No puede previsualizar el contenido de AMP directamente en Adobe Campaign. Utilice un sitio web externo como, por ejemplo, [AMP Playground](https://playground.amp.dev).

1. Vuelva a Adobe Campaign y copie y pegue el contenido validado en la pestaña **[!UICONTROL AMP content]**.

1. Cambie a la pestaña **[!UICONTROL HTML content]** o **[!UICONTROL Text content]** y defina el contenido para al menos uno de estos dos formatos.

   >[!IMPORTANT]
   >
   >Si el correo electrónico no contiene una versión HTML o de texto sin formato además del contenido de AMP, no se puede enviar.

## Requisitos de AMP para envío por correo electrónico {#amp-for-email-delivery-requirements}

Al crear el contenido de AMP en Adobe Campaign, debe cumplir las condiciones para enviar un correo electrónico dinámico, que son específicas de los proveedores de correo electrónico de los destinatarios.

Actualmente dos proveedores de correo electrónico admiten la prueba de este formato: Gmail y Mail.ru.

Todos los pasos y especificaciones requeridos para probar el envío con formato AMP en cuentas de Gmail se detallan en la documentación para desarrolladores de [Gmail](https://developers.google.com/gmail/ampemail?) y [Mail.ru.](https://postmaster.mail.ru/amp)

En particular, deben cumplirse los siguientes requisitos:
* Siga los requisitos de seguridad de AMP específicos de [Gmail](https://developers.google.com/gmail/ampemail/security-requirements) y [Mail.ru](https://postmaster.mail.ru/amp/#howto).
* La parte MIME de AMP debe contener un [documento AMP válido](https://amp.dev/documentation/guides-and-tutorials/learn/validation-workflow/validate_emails/?format=email).
* La parte MIME de AMP debe ser inferior a 100 KB.

También puede consultar la documentación de [Sugerencias y limitaciones conocidas de Gmail](https://developers.google.com/gmail/ampemail/tips).

## Objetivización de un correo electrónico de AMP {#targeting-amp-email}

Actualmente puede experimentar enviando un correo electrónico de AMP en dos pasos:

1. Adobe Campaign permite probar la entrega de un correo electrónico dinámico con tecnología AMP a las direcciones de correo electrónico seleccionadas correctamente configuradas, a fin de verificar su contenido y comportamiento. Consulte [Prueba de envío de correo electrónico AMP para direcciones seleccionadas](#testing-amp-delivery-for-selected-addresses).

1. Una vez probada, puede realizar un envío o una campaña como parte del programa de AMP de correo electrónico registrándose con los proveedores de correo electrónico correspondientes para que su dominio de remitente se incluya en la lista de permitidos. Consulte [Envío de correos electrónicos AMP mediante registro en un proveedor de correo electrónico](#delivering-amp-emails-by-registering).

### Prueba del envío de correo electrónico AMP para direcciones seleccionadas {#testing-amp-delivery-for-selected-addresses}

Puede probar la entrega de mensajes dinámicos desde Adobe Campaign a las direcciones de correo electrónico seleccionadas.

>[!NOTE]
>
>Solo Gmail y Mail.ru admiten la prueba del formato AMP.

Para Gmail, primero debe añadir las direcciones de los remitentes que está utilizando a la lista de permitidos para enviar desde Adobe Campaign las cuentas de direccionamiento de Gmail.

Para ello:
1. Asegúrese de que la opción que habilita el correo electrónico dinámico esté marcada para los proveedores de correo electrónico correspondientes.
1. Copie la dirección del remitente que se muestra en el campo **[!UICONTROL From]** del envío y péguela en la sección correspondiente de la configuración de la cuenta del proveedor de correo electrónico.

Para obtener más información, consulte la documentación para desarrolladores de [Gmail](https://developers.google.com/gmail/ampemail/testing-dynamic-email).

![](assets/amp_from_field.png)

Para probar el envío de un correo electrónico AMP a una dirección Mail.ru, siga los pasos de la [documentación del desarrollador de Mail.ru](https://postmaster.mail.ru/amp/#howto) (sección **Si es un usuario**).

### Envío de correos electrónicos AMP mediante el registro con un proveedor de correo electrónico {#delivering-amp-emails-by-registering}

Puede experimentar enviar correos electrónicos dinámicos registrándose con los proveedores de correo electrónico admitidos para que su dominio de remitente se añada a la lista de permitidos.

>[!NOTE]
>
>Solo Gmail y Mail.ru admiten el formato AMP.

Una vez probadas con algunas direcciones, puede enviar correos electrónicos AMP a cualquier dirección de Gmail. Para hacerlo, debe registrarse con Google y esperar su respuesta. Siga los pasos presentados en la documentación para desarrolladores de [Gmail](https://developers.google.com/gmail/ampemail/register). Después de registrarse correctamente, se convierte en un remitente autorizado.

Para enviar correos electrónicos AMP a direcciones de Mail.ru, siga los requisitos y pasos que se enumeran en la [documentación de desarrolladores de Mail.ru](https://postmaster.mail.ru/amp/#howto) (sección **Si es un remitente de correo electrónico**).

## Envío de un correo electrónico de AMP {#sending-amp-email}

Una vez que el contenido de AMP y la reserva están listos, y una vez definido un destinatario compatible, puede enviar el correo electrónico como lo haría normalmente.

Actualmente, solo Gmail y Mail.ru admiten el formato AMP en ciertas condiciones. Puede dirigirse a direcciones de otros proveedores de correo electrónico, pero recibirán la versión HTML o de texto sin formato de su correo electrónico.

>[!IMPORTANT]
>
>Si el correo electrónico no contiene una versión HTML o de texto sin formato además del contenido de AMP, no se puede enviar.

Los destinatarios coincidentes obtienen la versión AMP del correo electrónico en su buzón.

Por ejemplo, si ha incluido una lista de productos en el correo electrónico, al editar los precios en un sistema de terceros, los precios se ajustan automáticamente cada vez que los destinatarios vuelvan a abrir el correo electrónico en su buzón.

>[!NOTE]
>
>De forma predeterminada, la opción **[!UICONTROL AMP inclusion]** está configurada en **[!UICONTROL No]**.

## Tutorial en vídeo {#amp-email-video}

El siguiente vídeo explica cómo activar AMP en Adobe Campaign y cómo usarlo.

>[!VIDEO](https://video.tv.adobe.com/v/29940?quality=12&learn=on)
