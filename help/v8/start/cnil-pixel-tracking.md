---
title: Píxeles de seguimiento de correo electrónico y guía de CNIL
description: Comprender las directrices actualizadas de CNIL sobre los píxeles de seguimiento de correo electrónico y las funciones de Adobe Campaign que pueden apoyar los esfuerzos de cumplimiento.
feature: Overview
role: User
level: Beginner
hide: true
source-git-commit: c56ec544361983d75851660e739d02aadeb65dcd
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 2%

---

# Explicación de las directrices actualizadas de CNIL sobre los píxeles de seguimiento de correo electrónico

Esta publicación es solo con fines informativos. No es asesoramiento legal y no garantiza el cumplimiento de la ley aplicable. Las funcionalidades del producto de Adobe Campaign que se describen a continuación son componentes básicos que, configurados y operados correctamente, pueden admitir una implementación compatible. Cada cliente es responsable de determinar y cumplir con sus obligaciones según la ley aplicable.

## Información general

El 14 de abril de 2026, la _Comisión Nacional de Informática y Libertades_ (CNIL), la autoridad de protección de datos de Francia, publicó una [recomendación sobre el uso de píxeles de seguimiento en correos electrónicos](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf). La guía aclara cuándo se requiere el consentimiento y resalta la importancia de las prácticas de consentimiento adecuadas para el seguimiento de píxeles del correo electrónico. Esta política podría afectar a las prácticas de envío de cualquier entidad que envíe correos electrónicos a suscriptores con sede en Francia.

CNIL proporcionó a las empresas un periodo de tres meses a partir de la fecha de la recomendación para informar a sus destinatarios de correo electrónico (&quot;usuarios&quot;) de la presencia de los píxeles de seguimiento, su propósito y el derecho de los usuarios a la exclusión. Durante este período de transición, se espera que los clientes notifiquen a los usuarios el seguimiento de píxeles y proporcionen una exclusión si es necesario. Se espera que CNIL inicie sus actividades de aplicación después del 14 de julio de 2026.

A medida que la CNIL y otros reguladores aclaren las directrices sobre el seguimiento de píxeles y problemas relacionados, Adobe seguirá supervisando las actualizaciones e informando a los clientes de las funciones técnicas de los productos de Adobe que admiten el marketing por correo electrónico, incluido Adobe Campaign.

Las aplicaciones de ejecución de marketing por correo electrónico de Adobe, incluidas Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign y Marketo Engage, proporcionan controles que pueden ayudar a los clientes a administrar el seguimiento abierto en el nivel de envío o de correo electrónico. Los clientes son responsables de determinar sus propias obligaciones de cumplimiento según las directrices de CNIL aplicables y otras leyes, pero estas capacidades pueden apoyar los esfuerzos de cumplimiento de los clientes.

## Qué es un píxel de seguimiento de correo electrónico

Un píxel de seguimiento de correo electrónico es una imagen transparente 1x1 incrustada en el HTML de un correo electrónico. Cuando el cliente de correo electrónico del destinatario carga esa imagen, el píxel hace ping a un servidor que registra datos como una marca de tiempo, un tipo de dispositivo, un cliente de correo electrónico y, a veces, una dirección IP para obtener una ubicación aproximada. A continuación, ese registro se vincula al registro de un destinatario, lo que permite a los especialistas en marketing ver si se abre un correo electrónico.

## Atención al cliente

Los clientes que busquen ayuda para implementar los cambios descritos anteriormente pueden interactuar con el ecosistema de Adobe existente. Para preguntas técnicas sobre las funcionalidades de Adobe a las que se hace referencia, póngase en contacto con el administrador de éxito del cliente o con el administrador técnico de cuentas.

## Funcionalidad de Adobe Campaign relacionada con el seguimiento de correo electrónico

Los clientes pueden utilizar los mecanismos nativos de seguimiento, esquema y personalización de Adobe Campaign para abordar ciertos elementos al configurar la arquitectura para abordar las directrices CNIL:

* **Clasificación del envío.** Amplíe `nms:delivery` con un atributo `emailType` (autenticación, solo capacidad de entrega, transaccional, marketing, servicio público, prospección B2B). La clasificación determina qué píxeles se permiten sin consentimiento.
* **Captura de consentimiento.** Amplíe `nms:recipient` con una estructura de consentimiento por propósito que incluya la versión del texto, la marca de tiempo, el origen de captura y la caducidad. Amplíe los formularios de registro y los centros de preferencias para recopilar el consentimiento en píxeles de forma independiente de la inclusión por correo electrónico.
* **Emisión de píxeles.** Defina un `NmsTracking_OpenFormula` por propósito de píxel (autenticación, capacidad de entrega, rendimiento, generación de perfiles, detección de fraude). Una regla de tipología de entrega selecciona qué fórmulas emitir en función de emailType y el consentimiento del destinatario para cada propósito. Los bloques personalizados encapsulan la lógica para que no viva en elementos creativos individuales.
* **Retiro.** Agregue un vínculo **Administrar preferencias de rastreador** a cada pie de página del correo electrónico, distinto del vínculo de cancelación de suscripción. El vínculo apunta a una página de aterrizaje `nms:webApp` autenticada mediante `idTracking`; el destinatario retira el consentimiento con un solo clic, sin volver a escribir su dirección de correo electrónico. Un paso de filtro agregado al flujo de trabajo estándar **Tracking** evita que las reaperturas de correos electrónicos enviados anteriormente se aprovechen después de la retirada.
* **Prueba de consentimiento.** Capturar cada evento de consentimiento en un registro de solo anexar (un área de nombres de extensión `pix:consentLog`, por ejemplo), con la versión de la redacción almacenada por separado para su recuperación después de cambios de redacción. El registro aparece a través del explorador de Adobe Campaign y como una exportación periódica.
* **Gobernanza de solicitud de nuevo.** Un campo `lastPixelRefusalDate` y una regla de tipología de filtrado impiden que se vuelva a solicitar durante al menos seis meses después de una denegación. Un flujo de trabajo periódico puede ayudar a administrar la caducidad del consentimiento.
* **Informes.** Los informes de Adobe Campaign existentes siguen operando con los nuevos campos (urlCategory, emailType, los indicadores de consentimiento) sin cambios de código.

Para obtener más información sobre el seguimiento de correo electrónico en las aplicaciones de ejecución de marketing por correo electrónico de Adobe, consulte la siguiente documentación:

| Producto | Referencia de documentación |
|---|---|
| Campaign v8 | [Seguimiento de mensajes](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/analytics/tracking/url-tracking){target="_blank"} |
| Campaign Classic | [Introducción al seguimiento de mensajes](https://experienceleague.adobe.com/es/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-message-tracking){target="_blank"} |
| Campaign Standard | [Configuración del canal de correo electrónico](https://experienceleague.adobe.com/es/docs/campaign-standard/using/administrating/configuring-channels/configuring-email-channel){target="_blank"} |
| Journey Optimizer | [Documentación de seguimiento de mensajes](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/channels/email/design-email/add-content/message-tracking){target="_blank"} |
| Marketo Engage | [Deshabilitar el seguimiento de un vínculo de correo electrónico](https://experienceleague.adobe.com/es/docs/marketo/using/product-docs/email-marketing/general/functions-in-the-editor/disable-tracking-for-an-email-link){target="_blank"} |
| Journey Optimizer B2B | [Documentación de configuración de correo electrónico](https://experienceleague.adobe.com/es/docs/journey-optimizer-b2b/user/journey-content/email-channel/add-email){target="_blank"} |
