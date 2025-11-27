---
title: Preguntas más frecuentes sobre la versión 8 de Campaign
description: Obtenga respuestas a preguntas comunes de la versión 8 de Adobe Campaign sobre configuración, mensajería, flujos de trabajo y mucho más
feature: Overview
role: User
level: Beginner
keywords: Preguntas más frecuentes, Campaign v8, preguntas, respuestas, ayuda, asistencia, solución de problemas
hide: true
hidefromtoc: true
source-git-commit: 09911f7112a89b2cc5235b71bbcaa963ae739aed
workflow-type: tm+mt
source-wordcount: '9652'
ht-degree: 29%

---

# Preguntas frecuentes {#faq}

Obtenga respuestas rápidas a las preguntas más comunes sobre Adobe Campaign v8. Tanto si acaba de empezar como si busca ayuda para la configuración avanzada, encontrará respuestas organizadas por temas a continuación.

**¿Es nuevo en Campaign?** comienza con [Preguntas generales](#general) y [Conceptos clave](#key-concepts).\
**¿Necesita ayuda técnica?**: comprobar [desarrolladores](#developers) y [configuración de la campaña](#settings).\
**¿No encuentra la respuesta?** Visite nuestros [Foros de la comunidad](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=es){target="_blank"} o [comuníquese con la atención al cliente](#get-help).

>[!TIP]
>
>Utilice Ctrl+F (Cmd+F en Mac) para buscar palabras clave específicas en esta página. Haga clic en cualquier pregunta para ampliar la respuesta.


## Preguntas generales {#general}

Obtenga respuestas a las preguntas más comunes sobre Adobe Campaign v8, como cómo conectarse, actualizar y obtener asistencia.

+++ ¿Cómo puedo conectarme a Campaign v8?

Debe descargar e instalar la consola del cliente de Campaign para conectarse a Adobe Campaign.

[Haga clic aquí para obtener más información](connect.md).

A partir de la versión 8.6 de Campaign, tiene acceso a la **interfaz de usuario web de Campaign**, disponible a través del entorno central de Adobe Experience Cloud. Experience Cloud es la familia integrada de aplicaciones, productos y servicios de marketing digital de Adobe.

Obtenga información sobre cómo conectarse a Adobe Experience Cloud y acceder a la interfaz web de Adobe Campaign [en esta página](campaign-ui.md#ac-web-ui).

Obtenga más información en la [documentación de la interfaz de usuario web de Adobe Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

>[!TIP]
>
>**Solución de problemas de conexión:**
>
>* Compruebe que sus credenciales de Adobe ID son correctas
>* Asegúrese de que la versión de la consola del cliente coincida con la versión del servidor
>* Compruebe la conectividad de red y la configuración del cortafuegos
>* Borrar la caché de la consola de cliente si tiene problemas
>* Póngase en contacto con el administrador para comprobar los permisos de usuario

**Temas relacionados:**

* [Instalación de la consola de cliente](connect.md)
* [Interfaz de usuario de Campaign](campaign-ui.md)
* [Permisos de usuario](gs-permissions.md)

+++

+++ ¿Se puede instalar Campaign v8 en un entorno local o híbrido?

Por ahora, Campaign v8 solo está disponible en Managed Cloud Services, totalmente alojados por Adobe.

+++

+++ ¿Cómo puedo actualizar Campaign a la versión más reciente?

Adobe Campaign se actualiza periódicamente. Cada año se publican versiones menores con nuevas funciones, mejoras y correcciones. Además, lanzamos versiones periódicamente solamente con correcciones acumulativas.

Esta frecuencia regular de actualizaciones tiene como objetivo ofrecerle lo más novedoso y lo mejor, mantener el entorno seguro y mejorar su experiencia con nuestro producto. Esta es la razón por la que creemos que es esencial que ejecute la versión más reciente de Adobe Campaign.

>[!NOTE]
>
>Como usuario de Cloud Services administrados, la instancia se actualiza en Adobe con nuevas versiones.

+++

+++ ¿Cómo configurar el envío del correo electrónico?

La capacidad de envío de correo electrónico, un componente esencial para el éxito del programa de marketing de cada remitente, se caracteriza por criterios y reglas que cambian constantemente. La navegación eficaz en este mundo digital requiere un ajuste regular de su estrategia de correo electrónico, teniendo en cuenta las tendencias clave de envío, para llegar mejor a su público.

Consulte esta guía para obtener más información [Prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es){target="_blank"}

Aprenda a implementar la entregabilidad en Campaign [con esta guía](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=es){target="_blank"}

>[!TIP]
>
>**Sugerencias clave para la entrega:**
>
>* Mantenga una lista de correo electrónico limpia y elimine los suscriptores inactivos con regularidad
>* Utilice la doble inclusión para garantizar la participación de los destinatarios
>* Monitorice la reputación de su remitente y la reputación de su IP
>* Autentique sus correos electrónicos con SPF, DKIM y DMARC
>* Respetar las solicitudes de cancelación de suscripción inmediatamente
>* Pruebe los correos electrónicos antes de enviarlos a audiencias grandes

**Temas relacionados:**

* [Acerca de la capacidad de entrega](../send/about-deliverability.md)
* [Contenido de mensajes de control](../send/control-message-content.md)
* [Monitorización de la capacidad de entrega](../send/monitoring-deliverability.md)
* [SpamAssassin](../send/spamassassin.md)

+++

+++ ¿Cómo puedo asegurarme de que mi entrega se envíe sin errores?

Adobe Campaign incluye un conjunto de paneles de control y herramientas para monitorizar las entregas de correo electrónico.

[Lea la documentación de Campaign Classic v7 para aprender](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es){target="_blank"} a corroborar que sus mensajes se envían, a monitorizar la ejecución y a actuar en consecuencia si se produce un error.

+++

+++ ¿Se puede monitorizar la ejecución del flujo de trabajo?

Descubra cómo monitorizar la ejecución de flujos de trabajo de Campaign [en esta página](https://experienceleague.adobe.com/es/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}

+++

+++ ¿Con qué sistemas y componentes es compatible Campaign v8?

Puede obtener la lista de todos los sistemas y componentes compatibles con la última versión de Campaign en [la matriz de compatibilidad de Adobe Campaign](compatibility-matrix.md).

+++

+++ ¿Cómo puedo descargar Campaign?

Puede obtener el programa de instalación y la consola del cliente desde el Centro de descargas de Adobe.

Como usuario administrador, acceda a Adobe [Distribución de software](https://experience.adobe.com/#/downloads/content/software-distribution/es/campaign.html){target="_blank"} para descargar Adobe Campaign.

Obtenga más información acerca del Centro de distribución [en esta página](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=es){target="_blank"}.

+++

+++ ¿Cómo puedo registrar un problema?

La creación de un caso le permite ponerse en contacto con el equipo de Asistencia al cliente de Adobe en relación con cualquier problema que tenga con sus productos de Adobe. Para ayudarle a resolver sus problemas, Adobe Admin Console le permitirá hablar con Asistencia al cliente de Adobe.

Para registrar un problema o iniciar una sesión de chat en el nuevo sistema, conéctese a [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}.

Este nuevo sistema requiere nuevas cuentas individuales para cada usuario, con los permisos correctos. Si no puede iniciar sesión con su Adobe ID, solicite acceso a través de Experience League y el equipo de Servicio de atención al cliente le ayudará lo antes posible. [Más información](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Únase a la comunidad de Campaign: busque respuestas en preguntas existentes o pregunte a los expertos. [Únase a la conversación](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=es){target="_blank"}

+++


## Conceptos clave {#key-concepts}

Obtenga información sobre los conceptos fundamentales de Campaign, incluida la autenticación, la interfaz de usuario, los flujos de trabajo y las funcionalidades principales para empezar de forma eficaz.

+++ ¿Puedo conectarme a Campaign v8 con un Adobe ID?

¡Sí! Gracias a la integración con el IMS (Adobe Identity Management System), los usuarios se conectan a la consola de Adobe Campaign con su Adobe ID. La integración proporciona las siguientes ventajas:

* Se puede utilizar la misma ID para todas las soluciones de Experience Cloud.
* Cada conexión se memoriza cuando se utiliza Adobe Campaign con diferentes integraciones.
* Política de gestión segura de contraseñas.
* Uso de cuentas de ID federadas (proveedor de ID externo).

[Más información](connect.md) sobre el acceso a Campaign v8 con un Adobe ID.

+++

+++ ¿Cuál es mi versión de Campaign?

Compruebe su [versión y su número integrado](connect.md#ac-version) en el menú **Ayuda > Acerca de...** de la consola del cliente de Campaign.

+++

+++ ¿Cuáles son las diferencias entre la versión 7 de Campaign Classic y la versión 8 de Campaign?

Campaign v8 es la versión de próxima generación de Campaign, diseñada para Cloud Services administrados. Aporta mejoras significativas en infraestructura, seguridad, capacidad de envío y monitorización.

La versión 8 de Adobe Campaign está disponible exclusivamente como **Cloud Service administrado**, y no se puede implementar en un entorno local o híbrido.

[Más información acerca de la transición de Campaign Classic v7 a v8](v7-to-v8.md).

+++

+++ ¿Cómo puedo configurar los permisos de usuario?

Como administrador de Campaign, puede configurar permisos para usuarios de su organización.

Se trata de un conjunto de derechos y restricciones que autorizan o deniegan:

* Acceso a determinadas funcionalidades
* Acceder a determinados datos
* Creación, modificación o eliminación de datos

[Más información](../start/gs-permissions.md) acerca de los permisos de usuario en la versión 8 de Campaign.

**Temas relacionados:**

* [Introducción a los permisos](gs-permissions.md)
* [Administrar permisos de usuario](manage-permissions.md)
* [Agregar permisos en carpetas](folder-permissions.md)

+++

+++ ¿Cómo se puede garantizar el cumplimiento de la privacidad con Campaign?

Adobe Campaign ofrece un conjunto de herramientas para ayudarle con el cumplimiento de la privacidad de RGPD, CCPA y otras normas de privacidad.

[Más información](../start/privacy.md) acerca de la administración de privacidad y las herramientas y funcionalidades que proporciona Adobe Campaign para ayudarle a cumplir con la privacidad.

+++

+++ ¿Cuáles son los conceptos de la interfaz de usuario de Campaign que debería conocer?

Consulte [esta sección](campaign-ui.md) para obtener más información sobre los conceptos básicos de la interfaz de usuario de Adobe Campaign.

A partir de la versión 8.6 de Campaign, también tiene acceso a la nueva **interfaz de usuario web de Campaign**, disponible a través del entorno central de Adobe Experience Cloud.

[Obtenga más información en la documentación de la interfaz de usuario web de Adobe Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ ¿Cómo puedo seleccionar el público de mis mensajes?

Con Adobe Campaign, puede utilizar diferentes estrategias para crear públicos y seleccionar destinatarios objetivo.

[Más información](../audiences/gs-audiences.md) acerca de cómo definir audiencias en la versión 8 de Campaign.

+++

+++ ¿Qué es un flujo de trabajo?

Adobe Campaign incluye flujos de trabajo para organizar la gama completa de procesos y tareas en los distintos módulos del servidor de aplicaciones. Este entorno gráfico completo permite diseñar procesos, incluso la segmentación, la ejecución de campañas, el procesamiento de archivos, la participación humana, etc. El motor de flujo de trabajo se ejecuta y rastrea estos procesos.

Se puede utilizar un flujo de trabajo, por ejemplo, para descargar un archivo de un servidor, descomprimirlo y, a continuación, importar registros de la base de datos de Adobe Campaign.

Un flujo de trabajo también puede incluir uno o varios operadores por notificar o que pueden realizar acciones y aprobar procesos. De este modo, es posible crear una acción de envío, asignar una tarea a uno o varios operadores para trabajar en el contenido, especificar objetivos y verificar pruebas antes de iniciar la entrega.

[Más información](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=es){target="_blank"} sobre los flujos de trabajo. También puede leer las [prácticas recomendadas de flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=es){target="_blank"}.

**Temas relacionados:**

* [Introducción a los flujos de trabajo](../config/workflows.md)
* [Cree su primer flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=es){target="_blank"}
* [Casos de uso del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}
* [Monitorización de la ejecución del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=es){target="_blank"}

+++

+++ ¿Cómo se crea y se envía un primer correo electrónico?

La creación del primer correo electrónico en Campaign v8 implica varios pasos clave:

1. **Crear la entrega** - Comience creando un nuevo envío de correo electrónico desde una plantilla o desde cero
1. **Definir la audiencia**: seleccione los destinatarios objetivo mediante consultas, listas o flujos de trabajo
1. **Diseñar el contenido**: use el diseñador de correo electrónico para crear el mensaje con personalización
1. **Probar con pruebas** - Enviar correos electrónicos de prueba para validar contenido y personalización
1. **Analizar y enviar**: ejecuta el análisis de envío para comprobar si hay errores y, a continuación, envía el correo electrónico

La versión 8 de Campaign ofrece dos interfaces para la creación de correo electrónico:

* **Consola de cliente**: aplicación de escritorio con todas las funciones y funciones avanzadas
* **IU web de Campaign**: interfaz web moderna e intuitiva para una creación de correo electrónico más rápida

[Obtenga más información acerca del diseño y la validación de correos electrónicos](../send/email.md) en la versión 8 de Campaign.

**Temas relacionados:**

* [Cree su primer envío](create-message.md) - Guía paso a paso
* [Trabajar con plantillas de envío](../send/create-templates.md) - Ahorrar tiempo con plantillas
* [Prácticas recomendadas de entrega](delivery-best-practices.md) - Recomendaciones para el éxito
* [Definir el contenido del correo electrónico](../send/defining-the-email-content.md): opciones de creación de contenido
* [Vista previa y pruebas](../send/preview-and-proof.md) - Prueba antes de enviar
* [Configurar y enviar](../send/configure-and-send.md): pasos finales para enviar
* [Personalizar contenido](../send/personalize.md) - Agregar personalización dinámica

+++

+++ ¿Cómo se envían mensajes SMS?

El envío de mensajes SMS con Campaign v8 requiere una configuración inicial y, a continuación, sigue un proceso de envío directo:

**Configuración inicial (configuración única):**

1. **Configurar canal de SMS**: configure la configuración de envío de SMS y la cuenta externa
1. **Configurar conexión SMPP** - Conectarse a su proveedor de servicios SMS a través del protocolo SMPP
1. **Probar la conexión**: valide la conectividad con su proveedor de SMS
1. **Configurar enrutamiento**: define cómo se enrutan los mensajes SMS a través de tu proveedor

**Creando y enviando SMS:**

1. **Crear envío de SMS** - Iniciar un nuevo envío de SMS desde una plantilla
1. **Definir destinatarios**: seleccione la audiencia móvil mediante los campos de número de teléfono
1. **Escribir contenido de SMS**: crea tu mensaje (estándar de 160 caracteres o más con concatenación)
1. **Agregar personalización** - Incluir campos dinámicos específicos de cada destinatario
1. **Enviar pruebas** - Probar la entrega de SMS para validar el contenido y la entrega
1. **Analizar y enviar**: ejecute el análisis y envíelo a su audiencia

**Funcionalidades clave de SMS:**

* **Múltiples conectores SMPP**: compatibilidad con varios proveedores y protocolos SMS
* **Informes de envío**: haga un seguimiento de los mensajes enviados, entregados y con errores
* **Codificación de caracteres**: compatibilidad con GSM7, Unicode y caracteres especiales
* **Compatibilidad con SMS largos**: concatenación automática de mensajes para mensajes de texto más largos
* **SMS bidireccional**: administre las respuestas de SMS entrantes con flujos de trabajo

[Obtenga más información acerca de la configuración y el envío de SMS](../send/sms/sms.md) en la versión 8 de Campaign.

**Temas relacionados:**

* [Introducción a SMS](../send/sms/sms.md) - Guía completa de SMS
* [Configuración de envío de SMS](../send/sms/sms-delivery-settings.md) - Opciones de configuración
* [Configuración de cuenta externa de SMPP](../send/sms/smpp-external-account.md) - Configuración del proveedor
* [Crear un envío de SMS](../send/sms/create-sms.md): creación paso a paso
* [Contenido de SMS](../send/sms/sms-content.md): directrices de diseño de contenido
* [Envío de pruebas de SMS](../send/sms/sms-proofs.md) - Prueba de SMS
* [Monitorizar SMS](../send/sms/sms-monitor.md): haga un seguimiento y analice las entregas

+++

+++ ¿Cómo se envían notificaciones push?

El envío de notificaciones push con Campaign v8 implica configurar la integración de la aplicación móvil y crear notificaciones atractivas:

**Configuración inicial (configuración única):**

1. **Configurar canal push**: configure el canal de notificaciones push en Campaign
1. **Integrar Campaign SDK** - Agregar Adobe Campaign SDK a su aplicación móvil (o usar Recopilación de datos)
1. **Configurar aplicación móvil**: Registre sus aplicaciones de iOS y Android en Campaign
1. **Configurar certificados**: configure el certificado de APN (iOS) y la clave FCM (Android)
1. **Registro de pruebas**: compruebe que los dispositivos pueden registrarse y recibir tokens

**Creación y envío de notificaciones push:**

1. **Crear envío push** - Iniciar una nueva notificación push desde una plantilla
1. **Seleccionar plataforma**: elige iOS, Android o ambas plataformas
1. **Definir audiencia**: suscriptores de aplicaciones de destino que usan datos de suscripción de aplicaciones móviles
1. **Notificación de diseño** - Crear título, mensaje y contenido multimedia enriquecido
1. **Configurar el comportamiento** - Establecer acciones de clic, vínculos profundos y datos personalizados
1. **Enviar notificaciones de prueba** - Validar en dispositivos reales antes de enviar
1. **Analizar y enviar**: revise la segmentación y envíela a su audiencia móvil

**Funciones de notificación push:**

* **Notificaciones push enriquecidas**: incluye imágenes, vídeos y botones interactivos (iOS y Android)
* **Personalization**: contenido dinámico basado en el perfil y el comportamiento del usuario
* **Vinculación profunda**: Dirija a los usuarios a pantallas o contenido específicos de la aplicación
* **Programación** - Enviar a horas óptimas según la zona horaria del usuario
* **Pruebas A/B**: Pruebe mensajes diferentes y optimice la participación
* **Seguimiento**: supervise aperturas, clics y conversiones

**Características específicas de la plataforma:**

* **iOS**: notificaciones silenciosas, categorías de notificación, personalización de sonido
* **Android**: plantillas push enriquecidas, canales de notificación y diseños personalizados

[Obtenga más información acerca de la configuración de notificaciones push](../send/push-settings.md) en la versión 8 de Campaign.

**Temas relacionados:**

* [Crear y enviar notificaciones push](../send/push.md) - Guía completa de notificaciones push
* [Configurar el canal de notificaciones push](../send/push-settings.md) - Configuración del canal
* [Diseñar una notificación rich push de Android](../send/rich-push-android.md) - Notificaciones rich de Android
* [Diseñar una notificación rich push de iOS](../send/rich-push-ios.md) - Notificaciones rich de iOS
* [Configurar con recopilación de datos](../send/push-data-collection.md) - Método de integración moderno revisado
* [Seguimiento y monitorización](tracking.md) - Analizar el rendimiento de las notificaciones push

+++

+++ ¿Cómo se crea la página de destino?

Puede utilizar el editor de contenido digital de Adobe Campaign para diseñar páginas de aterrizaje y definir la asignación con campos de base de datos.

[Obtenga más información](../dev/landing-pages.md) en la documentación de Campaign v8.

También puede usar la interfaz de usuario de Campaign Web para crear y publicar páginas de aterrizaje: [Más información](https://experienceleague.adobe.com/es/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ ¿Cómo puedo hacer un seguimiento de las entregas?

Puede hacer un seguimiento de las entregas realizadas con Campaign v8 a través de [informes de entregas](../reporting/delivery-reports.md) dedicados y luego monitorizarlos.

Obtenga más información acerca de la administración de seguimiento en Campaign [en esta página](../start/tracking.md).

**Temas relacionados:**

* [Seguimiento y monitorización de mensajes](tracking.md)
* [Informes de envío](../reporting/delivery-reports.md)
* [Comprender los errores de envío](../send/delivery-failures.md)
* [Configurar vínculos rastreados](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"} (documentación de Campaign Classic v7)

+++

+++ ¿Cómo se puede traducir un mensaje de error?

¿Aparece un mensaje de error en un idioma extranjero? En [esta página](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=es){target="_blank"} se muestran todos los mensajes de error y su traducción.

+++

+++ ¿Puedo crear un formulario web y recopilar respuestas en Campaign?

Sí. Cree formularios web mediante **Campaign Web Applications &amp; Forms** (consola de cliente) para tener un control total sobre la lógica y validación de los formularios, o use **Campaign Landing Pages** (interfaz de usuario web) con una moderna interfaz de arrastrar y soltar para las suscripciones y la generación de posibles clientes. Ambos recopilan datos directamente en Campaign e integran flujos de trabajo para acciones automatizadas.

[Más información sobre las aplicaciones web y los formularios](../dev/webapps.md) | [Páginas de aterrizaje de la interfaz web de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8 frente a versiones anteriores {#v7-differences}

Comprenda las diferencias clave entre Campaign v8 y las versiones anteriores (Classic v7 y Standard), incluida la arquitectura, la implementación, las rutas de migración y los cambios de funciones.

+++ ¿Cuáles son las principales diferencias entre la versión 8 de Campaign y las versiones anteriores?

La versión 8 de Campaign es una completa reinvención de Adobe Campaign, diseñada para una arquitectura moderna nativa de la nube y que ofrece mejoras significativas con respecto a la versión 7 de Campaign Classic y a la Campaign Standard:

**Modelo de implementación:**

* **v8:** solo servicios administrados en la nube: totalmente hospedado y administrado por Adobe
* **v7/Standard:** Hay disponibles opciones locales, híbridas o hospedadas
* **Beneficio:** Cero administración de infraestructura, escalado automático, seguridad de nivel empresarial

**Arquitectura y rendimiento:**

* **v8:** arquitectura de FDA completo (FDAC) mejorada con base de datos PostgreSQL
* **v8:** optimizado para administrar millones de perfiles y envíos de gran volumen
* **v8:** Rendimiento de consultas y velocidad de procesamiento de datos mejorados de manera significativa
* **Beneficio:** Mejor rendimiento para operaciones a gran escala y campañas complejas

**Interfaz de usuario:**

* **v8:** Nueva interfaz de usuario web de Campaign junto con la consola de cliente
* **v8:** Diseño moderno y adaptable con experiencia de usuario mejorada
* **v8:** Flujos de trabajo simplificados de administración y creación de campañas
* **Beneficio:** Incorporación más rápida, ejecución más fácil de la campaña, mejor accesibilidad

**Actualizaciones y mantenimiento:**

* **v8:** actualizaciones automáticas administradas por Adobe: siempre en la última versión estable
* **v7:** Se requiere la planificación y ejecución manual de la actualización
* **Beneficio:** Menor carga de mantenimiento, acceso inmediato a nuevas funciones, sin tiempo de inactividad

**API e integración:**

* **v8:** API de REST modernas con rendimiento y confiabilidad mejorados
* **v8:** integración perfecta con las soluciones de Adobe Experience Cloud
* **Ventaja:** integraciones más sencillas, mejor interoperabilidad y prácticas de desarrollo modernas

[Obtenga más información acerca de las funcionalidades clave de Campaign v8](whats-new.md)

**Temas relacionados:**

* [De Campaign Classic v7 a v8](v7-to-v8.md)
* [De Campaign Standard a v8](acs-to-v8.md)
* [Arquitectura de la versión 8 de Campaign](../architecture/architecture.md)
* [Mecanismos de protección y limitaciones](ac-guardrails.md)

+++

+++ ¿Debería migrar de Campaign Classic v7 o Campaign Standard a v8?

**Campaign v8 es ideal para las organizaciones que necesitan:**

* **Campañas de gran volumen**: envía millones de mensajes con rendimiento y fiabilidad mejorados
* **Escalabilidad empresarial**: amplíe su base de datos y sus campañas sin problemas de rendimiento
* **Interfaz de usuario web moderna**: IU web de Campaign intuitiva y adaptable para una creación de campañas más rápida y una experiencia de usuario mejorada
* **Ventajas nativas de la nube**: aproveche las actualizaciones automáticas, la infraestructura administrada y la escala elástica
* **Soporte a largo plazo**: Campaign v8 es la plataforma estratégica de Adobe con soporte ampliado, mientras que las versiones anteriores llegarán al fin del soporte en los próximos años
* **Reducción de la sobrecarga de TI**: elimine la administración de la infraestructura y la planificación de la actualización

**Cuándo considerar la migración:**

* La instancia actual de Campaign administra grandes volúmenes de datos (millones de perfiles)
* Está experimentando problemas de rendimiento con flujos de trabajo o direccionamiento complejos
* Desea reducir los costes de mantenimiento y gestión de la infraestructura
* Necesita una integración perfecta con otras soluciones de Adobe Experience Cloud
* De todos modos, está planeando una actualización importante o una actualización de la infraestructura
* **Desea tecnología preparada para el futuro**: Campaign Classic v7 y Campaign Standard llegarán al fin de la asistencia técnica, por lo que v8 será la solución estratégica a largo plazo
* **Su equipo necesita una interfaz moderna**. La nueva interfaz de usuario de Campaign Web ofrece una experiencia más intuitiva y accesible para los especialistas en marketing

**Consideraciones de migración:**

* La migración automatizada aún no está disponible: Adobe proporciona asistencia y orientación para la migración
* v8 solo es Cloud Service administrado (sin implementación local o híbrida)
* Algunas implementaciones técnicas pueden diferir de la versión 7: revise la [matriz de compatibilidad](compatibility-matrix.md)
* La migración y las pruebas de datos requieren planificación y recursos

**Pasos siguientes:**
Póngase en contacto con su representante de Adobe para:

* Evalúe la preparación y el calendario de la migración
* Comprenda las ventajas específicas de su caso de uso
* Planificar la estrategia de migración y la asignación de recursos
* Acceso a herramientas de migración y asistencia

**Temas relacionados:**

* [De Campaign Classic v7 a v8](v7-to-v8.md): guía detallada de comparación y migración para usuarios de v7
* [De Campaign Standard a la versión 8](acs-to-v8.md): ruta de migración para usuarios estándar
* [Matriz de capacidades de Campaign v8](../start/compatibility-matrix.md)

+++

+++ ¿Qué funciones de Campaign Classic v7 son diferentes o no están disponibles en v8?

La versión 8 de Campaign incorpora la mayoría de las funciones de Campaign Classic v7 con mejoras, pero algunas tienen cambios debido a la arquitectura nativa de la nube de:

**No disponible en la versión 8:**

* **Implementaciones locales e híbridas**: La versión 8 de solo es Managed Cloud Services
* **Acceso directo a la base de datos**: en su lugar, use las API y herramientas proporcionadas
* **Infraestructura administrada por el cliente**: Adobe administra toda la infraestructura

**Diferentes implementaciones en la versión 8:**

* **Flujos de trabajo técnicos**: algunos optimizados para la arquitectura en la nube pueden funcionar de forma diferente
* **Estructura de la base de datos** - La arquitectura de FDAC mejorada puede requerir adaptaciones de esquema
* **Integraciones personalizadas**: es posible que necesite actualizaciones para la arquitectura basada en la nube
* **Personalizaciones de bajo nivel**: algunas requieren enfoques diferentes en un entorno administrado

**Mejorado o reemplazado en la versión 8:**

* **Actualizaciones de la compilación**: ahora automáticas (administradas por Adobe) en lugar de manuales
* **Ajuste del rendimiento** - Administrado por la optimización de la infraestructura de Adobe
* **Parches de seguridad**: aplicados automáticamente por Adobe
* **Copia de seguridad y recuperación** - Administrado por Adobe como parte del servicio


**Importante:** La mayoría de las características operativas y de marketing están disponibles y mejoradas en la versión 8. Adobe administra las funciones técnicas y de nivel de infraestructura en el entorno de la nube.

[Revise la matriz de compatibilidad completa](compatibility-matrix.md) para obtener información detallada.

**Temas relacionados:**

* [Mecanismos de protección](ac-guardrails.md)
* [Guía de transición de v7 a v8](v7-to-v8.md)

+++

## Perfiles y públicos {#audiences}

Encuentre respuestas a preguntas sobre la administración de perfiles, la creación de audiencias, la importación de datos y la segmentación de destinatarios para sus campañas.

+++ ¿Cómo se crean los destinatarios? 

Cree destinatarios manualmente en la consola del cliente para perfiles individuales, importe desde archivos (CSV/TXT) para adiciones masivas, utilice formularios web para el registro automático o integre a través de API desde sistemas externos. Utilice flujos de trabajo de importación para cargas de datos recurrentes.

[Crear perfiles manualmente](../audiences/create-profiles.md) | [Importar perfiles de un archivo](../audiences/import-profiles.md) | [Recopilar perfiles con formularios web](../audiences/collect-profiles.md)

+++

+++ Forma de importar los perfiles

Campaign ofrece varios métodos de importación: importación de archivos sencilla mediante el asistente de importación, importación basada en flujos de trabajo para transformaciones complejas, importación recurrente con flujos de trabajo programados desde SFTP e importación de API para la integración mediante programación.

Para las importaciones de archivos, prepare el archivo de datos (codificación CSV/TXT, UTF-8), utilice el asistente de importación o el flujo de trabajo, asigne columnas a campos de Campaign, defina reglas de actualización/inserción y realice la prueba primero con un pequeño ejemplo. Utilice flujos de trabajo para importaciones recurrentes y aplique reglas de anulación de duplicación.

[Guía de importación de datos](../start/import.md) | [Flujo de trabajo de importación recurrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=es){target="_blank"} | [Actividad de carga de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=es){target="_blank"}

+++

+++ ¿Cómo puedo definir la población destinataria de una campaña de marketing? 

Campaign ofrece varios métodos de segmentación: crear consultas con criterios visuales, segmentar listas o segmentos existentes, importar destinatarios de archivos externos (CSV, TXT) o aplicar filtros predefinidos. Puede combinar criterios con la lógica AND/OR, excluir poblaciones específicas, utilizar grupos de control y dividir para las pruebas A/B. Obtenga siempre una vista previa del tamaño de la población objetivo antes de enviar.

[Definir objetivos de campaña](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=es){target="_blank"} | [Actividad de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=es){target="_blank"} | [Crear audiencias](../audiences/create-audiences.md)

+++

+++ ¿Cómo puedo crear una lista de perfiles? 

Una lista es un conjunto estático de destinatarios que se puede dirigir en envíos y reutilizar en campañas.

**Tres métodos de creación:**

* **Creación manual:** Vaya a **[!UICONTROL Profiles and Targets > Lists]** y haga clic en **[!UICONTROL Create]**. Añadir destinatarios de una consulta, por selección individual o desde una carpeta.

* **Automatización del flujo de trabajo:** Utilice la actividad **[!UICONTROL List update]** para crear y mantener listas automáticamente a partir de resultados de consultas o datos importados.

* **Durante la importación:** Cree una lista al importar perfiles para guardarlos como un grupo reutilizable.

>[!TIP]
>
>Utilice flujos de trabajo para listas que requieran actualizaciones regulares y creación manual para la segmentación única.

[Crear audiencias](../audiences/create-audiences.md) | [Actividad de actualización de lista](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html?lang=es){target="_blank"}

+++

+++ ¿Cómo duplicar una población antes de enviar un mensaje? 

Utilice la actividad **[!UICONTROL Deduplication]** en un flujo de trabajo para eliminar los destinatarios duplicados antes de la entrega. Colóquela entre sus actividades **[!UICONTROL Query]** y **[!UICONTROL Delivery]** y, a continuación, elija los criterios de anulación de duplicación (generalmente la dirección de correo electrónico o el ID de destinatario) y qué registro desea mantener.

>[!TIP]
>
>Anule siempre la duplicación antes de enviar para asegurarse de que cada persona reciba el mensaje solo una vez.

[Actividad de deduplicación](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=es){target="_blank"}

+++

+++ ¿Cómo se identifican y se segmentan los suscriptores a un newsletter? 

Campaign realiza automáticamente un seguimiento de las suscripciones a boletines informativos a través de servicios informativos. Para dirigirse a suscriptores:

* Use una actividad **[!UICONTROL Query]** y filtre en **[!UICONTROL Subscriptions]** > seleccione el servicio del boletín informativo
* Seleccione a los suscriptores directamente de su envío eligiendo **[!UICONTROL To > Subscribers of an information service]**
* Generar listas de suscriptores con la actividad de flujo de trabajo **[!UICONTROL Subscription Services]**

Campaign realiza un seguimiento del historial de suscripciones/bajas y administra automáticamente la inclusión/exclusión.

[Administrar suscripciones](../start/subscriptions.md) | [Actividad de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=es){target="_blank"}

+++

+++ ¿Cuál es la práctica recomendada para excluir perfiles de una población objetivo? 

Utilice la actividad **[!UICONTROL Exclusion]** en un flujo de trabajo para eliminar perfiles no deseados del destinatario. Colóquelo después de las actividades de segmentación y defina qué población excluir.

[Actividad de exclusión](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html?lang=es){target="_blank"}

+++

+++ ¿Puedo utilizar perfiles externos sin importarlos en Campaign?

Sí, la versión 8 de Campaign le permite trabajar con perfiles externos almacenados en una base de datos externa sin cargarlos en Adobe Campaign. [Más información](../audiences/external-profiles.md).

+++

+++ ¿Cómo creo perfiles de prueba para mis envíos?

Los perfiles de prueba son destinatarios especiales que se utilizan para enviar pruebas y validar envíos sin afectar a la base de datos de producción. Créelos en **[!UICONTROL Profiles and Targets > Test profiles]** o use la característica **[!UICONTROL Seed addresses]** para agregar automáticamente destinatarios de prueba a sus envíos para garantizar la calidad y supervisar la bandeja de entrada.

[Perfiles de prueba](../audiences/test-profiles.md)

+++

## Diseño de mensaje {#design}

Aprenda a diseñar mensajes de marketing eficaces en Campaign v8, incluidas plantillas de correo electrónico, técnicas de personalización y contenido multilingüe. Diseñe sus mensajes en la consola del cliente o use el moderno **Designer de correo electrónico** de la interfaz de usuario web de Campaign para disfrutar de una experiencia de edición visual mejorada.

+++ ¿Cuáles son las prácticas recomendadas para diseñar correos electrónicos en Campaign?

Directrices clave: Garantice un diseño adaptable a dispositivos móviles, utilice un código compatible con HTML 4.0/XHTML con CSS en línea, optimice las imágenes (menos de 100 KB) con texto alternativo, utilice campos de combinación de personalización, realice pruebas en clientes de correo electrónico antes de enviarlo e incluya una versión de texto sin formato. Consiga un tamaño total de correo electrónico inferior a 500 KB para conseguir una entrega óptima.

[Guía de diseño de correo electrónico](../send/email.md) | [Prácticas recomendadas de envío](delivery-best-practices.md)

+++

+++ ¿Qué es una plantilla de envíos?

Una plantilla de envíos es un envío preconfigurado que guarda todos los ajustes y parámetros para reutilizarlos en varias campañas. Las plantillas incluyen reglas de destino, diseño de contenido, personalización, configuración técnica (remitente, respuesta) y reglas de tipología. Cree una vez y reutilice para mantener la coherencia y acelerar la creación de campañas.

[Creación de plantillas de entrega](../send/create-templates.md)

+++

+++ ¿Puedo importar fácilmente un HTML existente para crear un correo electrónico en Campaign?

Sí. Importe contenido de HTML mediante copiar/pegar directamente en el editor de contenido, cargar archivos desde el equipo o cargar desde una dirección URL. Asegúrese de que HTML utiliza código compatible con el correo electrónico (HTML 4.0/XHTML) con CSS en línea y aloje imágenes en un servidor público. Campaign añade automáticamente la personalización y el seguimiento a HTML importado.

>[!TIP]
>
>Para obtener la mejor experiencia de diseño de correo electrónico, usa **Email Designer** en la interfaz de usuario de Campaign Web, que ofrece funciones modernas de arrastrar y soltar y plantillas adaptables integradas, en lugar de importar HTML sin procesar.

[Importar contenido de HTML](../send/defining-the-email-content.md)

+++

+++ ¿Cómo puedo crear una newsletter basada en suscripción en Campaign?

Sí. Utilice los servicios informativos de Campaign para administrar las suscripciones al boletín informativo. Las funciones clave incluyen la administración automática de la inclusión/exclusión, el seguimiento de la suscripción, la administración del cumplimiento (RGPD, CAN-SPAM), la compatibilidad con varios boletines informativos, la integración web para formularios de registro y la entrega segmentada a los suscriptores.

[Administración de suscripciones](../start/subscriptions.md)

+++

+++ ¿Cómo puedo personalizar los mensajes?

Campaign ofrece funcionalidades de personalización para crear mensajes relevantes y dirigidos en función de los datos del destinatario, el comportamiento y las preferencias.

**Opciones de Personalization:**

* **Campos de personalización** - Insertar datos de destinatario (por ejemplo, `"Hello {{firstName}}")`
* **Bloques de personalización**: utilice bloques de contenido predefinidos o personalizados
* **Contenido condicional**: muestra contenido diferente según los criterios del destinatario
* **Datos de comportamiento**: aprovecha el historial de navegación, los patrones de compra o las métricas de participación

Pruebe la personalización antes de enviar para verificar que los campos de combinación y la lógica condicional funcionan correctamente.

[Guía de Personalization](../send/personalize.md) | [Campos de personalización](../send/personalization-fields.md) | [Contenido condicional](../send/conditions.md)

+++

+++ ¿Puedo enviar mensajes multilingües?

Sí. La versión 8 de Campaign ofrece funcionalidades multilingües, con la **IU web de Campaign** que proporciona el enfoque más sencillo. La interfaz de usuario web ofrece un envío multilingüe nativo con variantes de idioma: agregue variantes de idioma al envío y Campaign enviará automáticamente la versión adecuada en función del idioma preferido del destinatario. Disponible para correo electrónico, notificaciones push, SMS y mensajes transaccionales.

Funciones clave: duplicación automática de contenido, envío automático basado en idiomas, reserva de idioma predeterminada y administración sencilla de variantes.

La consola del cliente también admite contenido multilingüe mediante contenido condicional y flujos de trabajo, pero requiere una configuración más manual.

[Envíos multilingües (interfaz de usuario web)](https://experienceleague.adobe.com/es/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Contenido condicional (consola de cliente)](../send/conditions.md)

+++

+++ ¿Puedo localizar un formulario web?

Sí. Las aplicaciones web de Campaign admiten la localización en varios idiomas. Defina traducciones para todos los elementos del formulario (etiquetas, botones, mensajes, texto de error), con detección automática de idioma basada en la configuración del perfil de destinatario o del explorador. Se admiten versiones en varios idiomas dentro de una sola aplicación web, con reserva a un idioma predeterminado cuando sea necesario.

[Localización de aplicaciones web](../dev/webapps.md)

+++

+++ ¿Puedo utilizar contenido con tecnología de IA en mis correos electrónicos?

Sí, pero **solo a través de la IU web de Campaign**. El asistente de IA, con tecnología de Microsoft Azure OpenAI y Adobe Firefly, ayuda a crear contenido profesional y coherente con la marca en correos electrónicos, SMS y notificaciones push.

**Funcionalidades clave:**

* Generar texto (copia de correo electrónico, líneas de asunto, contenido SMS/push) e imágenes alineadas con la marca
* Crear variaciones de contenido optimizadas para diferentes audiencias
* Refinamiento del contenido (elaborar, resumir, reformular, simplificar)
* Cargar recursos de marca y obtener puntuación de alineación de marca
* Usar contenido existente como referencia y cargar imágenes de referencia de estilo

>[!NOTE]
>
>El asistente de IA está disponible exclusivamente en la interfaz de usuario web de Campaign y, actualmente, solo admite inglés. Los usuarios necesitan los permisos adecuados y deben aceptar un acuerdo de usuario.

[Descripción general del Asistente de IA](https://experienceleague.adobe.com/es/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Casos de uso del Asistente de IA](https://experienceleague.adobe.com/es/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Alineación de marca](https://experienceleague.adobe.com/es/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Prueba y envío de mensajes {#send}

Conozca las prácticas recomendadas para probar, validar, enviar y rastrear sus mensajes de marketing para garantizar el éxito de la entrega de campañas.

+++ ¿Qué es el análisis de entrega?

El análisis de envío es una fase de validación en la que Campaign se ejecuta antes de enviar. Calcula la población objetivo, valida el contenido, comprueba si hay errores, aplica reglas de tipología y calcula el volumen de entrega.

Campaign genera registros que muestran advertencias y errores. Los errores bloquean la entrega y deben corregirse; las advertencias son aconsejables. Revise siempre los registros de análisis antes de enviar.

[Guía de análisis de envíos](../send/delivery-analysis.md)

+++

+++ ¿Por qué debería generar pruebas?

Las pruebas son mensajes de prueba que validan la entrega antes de enviarlo a la audiencia principal. Utilice pruebas para verificar la personalización, probar el procesamiento de contenido en clientes de correo electrónico, confirmar vínculos y realizar un seguimiento del trabajo, comprobar imágenes y archivos adjuntos y validar la capacidad de respuesta móvil.

Las pruebas ayudan a detectar errores antes de que lleguen a miles de destinatarios, habilitan la aprobación de las partes interesadas y prueban la ubicación en la bandeja de entrada. Envíe pruebas a varios clientes de correo electrónico y dispositivos, y obtenga siempre la aprobación antes de que se envíe el flujo de trabajo de producción.

[Guía de pruebas y previsualización](../send/preview-and-proof.md)

+++

+++ ¿Cómo se utilizan las direcciones semilla en Adobe Campaign?

Las direcciones semilla son destinatarios especiales que se añaden automáticamente a cada entrega para realizar pruebas, garantizar la calidad y supervisar el contenido, sin coincidir con los criterios de destino. Útil para la monitorización continua, las pruebas de ubicación de bandeja de entrada, la validación de correo directo y la visibilidad de las partes interesadas.

**Diferencias clave de las pruebas:**

* **Direcciones semilla**: agregadas automáticamente a los envíos de producción, cuente para enviar el volumen
* **Pruebas**: la prueba se envía antes de la producción, no se cuenta en el volumen, se usa para la validación

Administrar direcciones semilla en **[!UICONTROL Resources > Campaign management > Seed addresses]**. Mantenga las listas pequeñas para evitar afectar a las métricas de envío.

[Guía de direcciones semilla](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html?lang=es){target="_blank"}

+++

+++ ¿Cómo puedo configurar un proceso de aprobación antes de enviar mensajes?

Campaign proporciona flujos de trabajo de aprobación para garantizar que los mensajes cumplan los estándares de calidad antes de enviarlos. Configure aprobaciones para el contenido, el destinatario, la extracción (correo postal) y el presupuesto en el nivel de campaña o entrega.

**Configuración:**

Cree grupos de operadores en **[!UICONTROL Administration > Access management > Operator groups]** y luego asigne grupos de aprobación en las propiedades de campaña o entrega. Campaign envía correos electrónicos de notificación a los revisores que pueden aprobar, rechazar o solicitar cambios.

**Para envíos independientes (no en una campaña):**

Use **pruebas como proceso de aprobación**. Envíe pruebas al grupo de aprobación para su validación y envíe siempre una nueva prueba después de realizar cambios para garantizar que las partes interesadas revisen la versión más reciente.

[Validación de envío](../send/preview-and-proof.md) | [Aprobaciones de campaña](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=es){target="_blank"}

+++

+++ ¿Qué es una regla de tipología?

Las reglas de tipología son lógicas empresariales automatizadas aplicadas durante el análisis de envío para validar y optimizar el envío de mensajes. Garantizan el cumplimiento de las políticas de marketing, protegen la capacidad de entrega y evitan la fatiga de los clientes.

**Tipos de reglas principales:**

* **Reglas de filtrado** - Excluir destinatarios (incluidos en la lista de bloqueados, sin suscribir, en cuarentena)
* **Reglas de presión**: controla la frecuencia de los mensajes para evitar que los destinatarios se vean abrumados
* **Reglas de capacidad**: limitar el volumen de mensajes para la capacidad de procesamiento o los límites del ISP
* **Reglas de control** - Comprobar la validez del mensaje (línea de asunto, vínculo de cancelación de suscripción, formato de remitente)

Las reglas se agrupan en tipologías y se aplican durante el análisis de envío. Campaign puede excluir destinatarios, bloquear la entrega o generar advertencias basadas en las reglas.

[Guía de reglas de tipología](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=es){target="_blank"}

+++

+++ ¿Cómo puedo enviar correos electrónicos en cadena? 

Sí. El envío de ondas divide su envío en varios lotes enviados a intervalos programados. Esto es esencial para campañas de gran volumen a fin de equilibrar la carga del servidor, evitar la restricción de ISP, crear una reputación de remitente con nuevas IP y administrar las exclusiones/devoluciones entre olas.

**Configuración:**

En las propiedades de la entrega, habilite el envío de ondas y defina el número de olas (o el tamaño del lote), el intervalo entre olas y la distribución de ondas (porcentajes lineales o personalizados). Campaign divide automáticamente la población objetivo y envía cada ola según lo programado.

Utilice olas para campañas grandes, monitorice el rendimiento de la primera ola antes de continuar y permita tiempo suficiente entre olas para procesar devoluciones y exclusiones.

[Configurar el envío de olas](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ ¿Cuáles son los pasos clave para crear un correo electrónico en Campaign?

La creación de un correo electrónico en Campaign v8 implica estos pasos clave: crear la entrega, definir la audiencia de destino, diseñar el contenido, añadir personalización, configurar opciones (remitente, asunto, respuesta), ejecutar el análisis de entrega, enviar pruebas para realizar pruebas y, finalmente, enviar o programar.

**Pasos clave:**

1. **Crear la entrega** - Elija el correo electrónico como canal y, opcionalmente, seleccione una plantilla de entrega
1. **Definir el destinatario**: seleccione la audiencia de destinatario mediante consultas, listas o archivos importados
1. **Diseño del contenido** - Cree su mensaje con el editor de correo electrónico (interfaz de usuario web, Designer de correo electrónico o editor de consola de cliente)
1. **Agregar personalización**: inserte campos dinámicos, bloques de personalización y contenido condicional
1. **Configurar opciones** - Establecer parámetros de dirección de remitente, línea de asunto, respuesta y entrega
1. **Ejecutar análisis de envío**: Campaign valida el contenido, calcula el objetivo y comprueba los errores
1. **Enviar pruebas**: pruebe el correo electrónico con grupos de aprobación para validar el procesamiento y el contenido
1. **Enviar o programar** - Enviar inmediatamente al objetivo principal o programar para una fecha posterior

**Dos opciones de interfaz:**

* **Interfaz de usuario web de Campaign**: interfaz moderna con correo electrónico Designer mejorado, asistente de IA y funciones multilingües
* **Consola de cliente**: interfaz tradicional con funciones avanzadas de flujo de trabajo y direccionamiento


>[!TIP]
>
>Utilice la interfaz de usuario web de Campaign para una creación de correo electrónico más rápida e intuitiva con herramientas de diseño modernas. Utilice la consola del cliente para segmentar campañas complejas o avanzadas basadas en flujos de trabajo.

[Cree su primer correo electrónico](create-message.md) | [Guía de diseño de correo electrónico](../send/email.md)

+++

+++ ¿Cómo se puede programar una entrega?

Campaign le permite programar envíos para envíos futuros a fin de optimizar los tiempos de envío y coordinar las campañas.

**Opciones de programación:**

* **Propiedades de envío** - Enviar inmediatamente, programar para una fecha/hora específica o diferir por horas/días
* **Nivel de campaña**: coordine todas las entregas dentro de una campaña
* **Actividad del Planificador de flujo de trabajo**: para envíos recurrentes, patrones complejos y campañas activadas por eventos

Campaign también admite la optimización de la fecha de contacto (mejor hora de envío por destinatario) y la adaptación de la zona horaria (misma hora local para todos los destinatarios).

[Programar envío de envíos](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ ¿Se puede añadir un archivo adjunto a los correos electrónicos?

Sí. Campaign admite archivos adjuntos estáticos (el mismo archivo para todos los destinatarios) y personalizados (diferentes archivos por destinatario según los datos del perfil). Agregue archivos adjuntos en la sección **[!UICONTROL Attachments]** de sus propiedades de entrega.

**Consideraciones importantes:**

* Mantener los archivos adjuntos en 1 MB para una entrega óptima
* Los archivos adjuntos pueden almacenar en déclencheur los filtros de correo no deseado; pruébelos a fondo antes de enviarlos
* Evite los tipos de archivo que suelen bloquear los clientes de correo electrónico (.exe, .zip, .js)
* Para archivos grandes, considere la posibilidad de utilizar vínculos de descarga rastreados en su lugar

Utilice formatos de archivo seguros (PDF, JPEG, PNG, DOCX) y pruébelos con direcciones semilla antes de que se envíe el proceso de producción.

[Guía de archivos adjuntos de correo electrónico](../send/email.md#attachments)

+++

+++ ¿Cómo puedo configurar los vínculos rastreados en una entrega de correo electrónico?

Campaign convierte automáticamente todas las direcciones URL del correo electrónico en vínculos rastreados para supervisar la participación de los destinatarios. Acceda a la sección **[!UICONTROL Tracking]** de su envío para configurar las opciones de seguimiento de cada vínculo.

**Opciones de configuración:**

* **Habilitar/deshabilitar seguimiento** - Control de seguimiento por vínculo
* **Etiquetas de vínculos** - Agregue nombres descriptivos para los informes (por ejemplo, &quot;Comprar ahora en CTA&quot;)
* **Categorías de vínculos**: agrupe vínculos por tipo para el análisis agregado
* **Tipo de seguimiento** - Rastrear clics, aperturas o ambos

Campaign realiza un seguimiento de los vínculos de contenido, de las páginas espejo y de los vínculos de cancelación de suscripción, y puede incluir un píxel de seguimiento opcional para las aperturas de correo electrónico. Utilice etiquetas y categorías significativas para simplificar la creación de informes e identificar rápidamente contenido de alto rendimiento.

[Guía de seguimiento de vínculos](../start/tracking.md) | [Prácticas recomendadas de seguimiento](../send/send.md)

+++

+++ ¿Dónde puedo acceder a los registros de entrega y seguimiento?

Acceda a los registros de envío y seguimiento directamente desde cada panel de envío. En la consola del cliente, haga clic en la ficha **[!UICONTROL Delivery]** en la parte inferior. En la interfaz de usuario web de Campaign, vaya a la sección **[!UICONTROL Logs]**.

**Registros disponibles:**

* **Registros de envío** - Mensajes enviados con detalles y estado de destinatario (enviados, pendientes, con error)
* **Registros de seguimiento**: interacciones del destinatario (aperturas, clics) con marcas de tiempo
* **Registros de exclusión** - Destinatarios excluidos con motivos (cuarentena, reglas de tipología, duplicados)
* **Registros de difusión** - Historial de envío completo, incluidos reintentos y errores

Utilice estos registros para solucionar problemas de entrega, analizar la participación y mantener la higiene de la lista.

[Supervisión de entrega](../send/send.md) | [Guía de seguimiento](../start/tracking.md)

+++

+++ ¿Dónde puedo obtener los informes de envío?

Campaign proporciona informes integrados completos para analizar el rendimiento de la entrega, la participación de los destinatarios y la eficacia de la campaña. Acceda a informes desde la ficha **[!UICONTROL Reports]** en cualquier entrega, desde el panel de campañas o desde el menú global **[!UICONTROL Reports]** para el análisis entre campañas.

**Los informes clave incluyen:**

* **Resumen de envío**: envía estadísticas, aperturas, clics, devoluciones y cancelaciones de suscripción
* **Clics activos**: mapa de calor visual del rendimiento del vínculo
* **Indicadores de seguimiento** - Tasas de clics y métricas de participación
* **No entregables**: análisis de rechazo con motivos de error

Los informes están disponibles tanto en la consola del cliente como en la interfaz de usuario web de Campaign con visualizaciones modernas.

[Informes de envío integrados](../reporting/delivery-reports.md) | [Informes de campaña](../reporting/gs-reporting.md)

+++

+++ ¿Cómo califica y administra las direcciones en cuarentena Adobe Campaign?

Campaign administra automáticamente una lista de cuarentena para proteger la reputación del remitente y mejorar la capacidad de entrega. Las direcciones en cuarentena se excluyen automáticamente de futuros envíos hasta que se validan o eliminan de la cuarentena.

**Por qué las direcciones se ponen en cuarentena:**

* **Rechazos graves** - Errores de entrega permanentes (dirección de correo electrónico no válida, dominio no existente, buzón eliminado)
* **Umbral de rebote suave**: errores temporales repetidos (buzón lleno, servidor no disponible temporalmente) que superan el umbral de error
* **Quejas por correo no deseado** - Destinatarios que marcan sus correos electrónicos como correo no deseado
* **Direcciones no válidas** - Direcciones con errores de sintaxis o que no superan la validación
* **Incluidos en la lista de bloqueados**: destinatarios que se excluyeron o que solicitaron ser excluidos

**Funcionamiento de la cuarentena:**

Campaign realiza un seguimiento de los errores de envío de cada dirección. Cuando una dirección alcanza el umbral de error configurado, se pone en cuarentena automáticamente y se excluye de todos los envíos futuros durante el análisis. Las devoluciones duras (errores permanentes) se ponen en cuarentena inmediatamente, mientras que las devoluciones suaves requieren varios errores antes de la cuarentena.

**Administración de direcciones en cuarentena:**

Acceder a la administración de cuarentena en **[!UICONTROL Administration > Campaign Management > Non deliverables Management]**. Puede ver las direcciones en cuarentena, eliminar manualmente las direcciones validadas de la cuarentena o configurar reglas de limpieza automáticas.

>[!TIP]
>
>Monitorice la lista de cuarentena regularmente. El aumento de las tasas de cuarentena suele indicar problemas de calidad de datos que requieren atención antes de que afecten a la reputación del remitente.

[Guía de administración de cuarentena](../send/quarantines.md) | [Administración de devoluciones](../send/delivery-failures.md)

+++

## Flujos de trabajo {#workflows}

Explore cómo utilizar flujos de trabajo para automatizar procesos, administrar datos y organizar campañas de marketing complejas en Adobe Campaign.

+++ ¿Cuáles son los pasos clave para crear un flujo de trabajo?

Cree flujos de trabajo para automatizar los procesos de marketing en Campaign:

1. **Crear un nuevo flujo de trabajo** - Vaya a **[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]** o **[!UICONTROL Administration > Production > Technical workflows]** y haga clic en **[!UICONTROL Create]**
1. **Agregar actividades** - Arrastrar y soltar actividades de la paleta (segmentación, control de flujo, actividades de acción)
1. **Configurar actividades**: haga doble clic en cada actividad para establecer parámetros y definir lógica
1. **Conectar actividades** - Vincular actividades con transiciones para definir el flujo de ejecución
1. **Probar y validar**: use el diagrama de flujo de trabajo para comprobar la lógica y, a continuación, pruébelo con un pequeño conjunto de datos
1. **Ejecutar**: Inicie el flujo de trabajo manualmente o programe su ejecución automática

Patrones de flujo de trabajo comunes: importación de datos, segmentación de audiencia, envío de envíos, enriquecimiento de datos y orquestación entre canales.

**Temas relacionados:**

* [Creación de un flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=es){target="_blank"}
* [Actividades de flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"}
* [Prácticas recomendadas de flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=es){target="_blank"}
* [Casos de uso del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ ¿Cómo se pueden importar datos en Campaign?

Importe datos en Campaign utilizando varios métodos según sus necesidades:

**Importación simple de archivos:**

* Utilice el asistente de importación para importaciones CSV/TXT únicas con una interfaz guiada
* Ideal para cargas manuales y cargas de datos rápidas

**Importación basada en flujo de trabajo:**

* Crear flujos de trabajo con actividad **[!UICONTROL Data loading (file)]** para importaciones complejas
* Añadir transformaciones, enriquecimiento y deduplicación de datos
* Programar importaciones recurrentes desde SFTP, directorios locales o almacenamiento en la nube

**Integración de API:**

* Utilice las API de REST para importar datos mediante programación desde sistemas externos
* Ideal para la sincronización en tiempo real con CRM, comercio electrónico u otras plataformas

**Prácticas recomendadas:** Realice siempre pruebas con muestras pequeñas, utilice la codificación UTF-8, asigne los campos correctamente, aplique reglas de deduplicación y programe importaciones grandes durante las horas de menor actividad.

**Temas relacionados:**

* [Prácticas recomendadas de importación](../start/import.md)
* [Actividad de carga de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=es){target="_blank"}
* [Flujo de trabajo de importación recurrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=es){target="_blank"}

+++

+++ ¿Se puede monitorizar la ejecución del flujo de trabajo?

Sí. Campaign proporciona funciones completas de monitorización del flujo de trabajo para realizar un seguimiento de la ejecución, identificar problemas y optimizar el rendimiento.

**Opciones de supervisión:**

* **Panel de flujo de trabajo**: vea el estado de ejecución en tiempo real, el progreso y los estados de actividad
* **Registros de ejecución** - Acceder a los registros detallados de cada actividad y transición
* **Pista de auditoría**: haga un seguimiento de las modificaciones del flujo de trabajo y del historial de ejecución
* **Alertas y notificaciones** - Configurar alertas por correo electrónico para errores o condiciones específicas

**Características de supervisión clave:**

* Indicadores de estado visuales (pendiente, en curso, completado, fallido)
* Seguimiento del tiempo de ejecución para la optimización del rendimiento
* Mensajes de error de nivel de actividad para la resolución de problemas
* Pausar, detener o reiniciar flujos de trabajo según sea necesario

Monitorización de acceso desde **[!UICONTROL Administration > Production > Objects created automatically > Campaign workflows]** o directamente desde el panel de flujo de trabajo.

**Temas relacionados:**

* [Monitorización de la ejecución del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=es){target="_blank"}
* [Prácticas recomendadas de flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=es){target="_blank"}
* [Inicio de un flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/executing-a-workflow/start-a-workflow.html?lang=es){target="_blank"}

+++

+++ ¿Cómo se pueden actualizar los datos de Campaign con un flujo de trabajo?

Utilice la actividad **[!UICONTROL Update data]** en flujos de trabajo para realizar operaciones masivas en la base de datos:

**Operaciones compatibles:**

* **Insertar** - Agregar nuevos registros a la base de datos
* **Actualizar** - Modificar registros existentes basados en criterios coincidentes
* **Insertar o actualizar** - Agregar registros nuevos o actualizar los existentes (actualizar)
* **Eliminar** - Quitar registros que coincidan con criterios específicos

**Casos de uso comunes:**

* Actualización de atributos de perfil después del enriquecimiento de datos
* Sincronización de datos con sistemas externos
* Mantener suscripciones a listas en función del comportamiento
* Limpieza y deduplicación de datos
* Aplicar cambios de estado masivos (por ejemplo, exclusión, cuarentena)

Configure las claves de reconciliación para que coincidan los registros con precisión y elija las opciones de actualización (actualice todos los campos o solo los vacíos).

**Temas relacionados:**

* [Actualizar actividad de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=es){target="_blank"}
* [Actividades de administración de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ ¿Cómo se pueden aprovechar las funcionalidades de administración de datos?

Las actividades de gestión de datos de Campaign permiten operaciones de datos sofisticadas dentro de flujos de trabajo para una segmentación y un objetivo complejos.

**Actividades clave de administración de datos:**

* **Enriquecimiento** - Agregar datos de tablas relacionadas o orígenes externos a la población activa
* **Split**: Segmenta poblaciones según criterios o distribuye aleatoriamente
* **Anulación de duplicación**: quite registros duplicados basados en claves especificadas
* **Actualizar datos** - Realizar operaciones de inserción, actualización o eliminación en lotes
* **Cambiar dimensión** - Cambiar dimensiones de segmentación (por ejemplo, de destinatarios a suscripciones)
* **Intersección/Unión/Exclusión**: combinar o filtrar varias poblaciones

**Casos de uso comunes:**

* Enriquecimiento de perfiles con historial de compras o datos de comportamiento
* Segmentar audiencias en varios grupos para diferentes mensajes
* Eliminación de duplicados antes del envío
* Integración de datos de bases de datos externas (FDA - Acceso de datos federado)
* Crear consultas y uniones complejas de varias tablas

Estas actividades permiten trabajar con datos que no están directamente en la tabla de destinatarios principal y realizar operaciones avanzadas en la base de datos.

**Temas relacionados:**

* [Actividades de administración de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"}
* [Flujos de trabajo de segmentación](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=es){target="_blank"}
* [Actividad de enriquecimiento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=es){target="_blank"}

+++

+++ ¿Se puede automatizar la entrega de mensajes personalizados?

Sí. Los flujos de trabajo permiten campañas de mensajes personalizadas completamente automatizadas basadas en los datos de los destinatarios, el comportamiento y los criterios personalizados.

**Estructura del flujo de trabajo de automatización:**

1. **Consulta**: seleccione su audiencia de destino según ciertos criterios
1. **Enriquecimiento** - Agregar datos de personalización de tablas relacionadas
1. **Split**: Segmente en grupos para diferentes variantes de mensaje (opcional)
1. **Envío** - Envío de mensajes personalizados con campos combinados
1. **Programador**: configure la ejecución recurrente para campañas automatizadas

**Opciones de Personalization:**

* Usar datos de perfil de destinatario (nombre, ubicación, preferencias)
* Incluir datos de comportamiento (historial de compras, puntuaciones de participación)
* Aplicar contenido condicional basado en segmentos o atributos
* Calcular valores dinámicos (puntos de lealtad, fechas de caducidad)

Escenarios comunes: campañas de cumpleaños, abandono del carro de compras, programas de fidelidad, campañas de recuperación y mensajes activados por eventos.

**Temas relacionados:**

* [Guía de Personalization](../send/personalize.md)
* [Casos de uso del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=es){target="_blank"}
* [Actividad de enriquecimiento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=es){target="_blank"}

+++

+++ ¿Cómo se puede dividir un público en subconjuntos con un flujo de trabajo?

Utilice la actividad **[!UICONTROL Split]** para dividir una sola población en varios subconjuntos en función de criterios o reglas de distribución.

**Métodos de división:**

* **Condiciones de filtrado**: cree subconjuntos basados en criterios (por ejemplo, grupos de edad, ubicación, estado de VIP)
* **Distribución porcentual**: dividido aleatoriamente en porcentajes iguales o personalizados para pruebas A/B
* **Limitar registros** - Restringir tamaños de subconjuntos (primeros N registros, X% superior, selección aleatoria)
* **Agrupación de datos**: cree un subconjunto por cada valor distinto (por ejemplo, un subconjunto por país)

**Casos de uso comunes:**

* Pruebas A/B con grupos de control
* Enrutamiento de preferencias de canal (correo electrónico frente a SMS)
* Despliegue progresivo (enviar al 10 % y después al 90 %)
* Mensajería específica de segmentos (VIP, clientes habituales, nuevos clientes)
* Equilibrio de carga en varios servidores de entrega

Cada subconjunto dividido fluye a una transición independiente, lo que permite un procesamiento o envío diferentes para cada grupo.

**Temas relacionados:**

* [Dividir actividad](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=es){target="_blank"}
* [Guía de pruebas A/B](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ ¿Cómo se pueden actualizar los datos de destinatario de un archivo externo?

Sí. Utilice flujos de trabajo para actualizar los datos de Campaign con valores de archivos externos (CSV, TXT).

**Estructura del flujo de trabajo:**

1. **Carga de datos (archivo)**: cargue el archivo externo y asigne columnas
1. **Enriquecimiento** (opcional): agregar datos o transformaciones adicionales
1. **Reconciliación**: defina las claves para que coincidan los registros de archivos con los registros de la base de datos (por ejemplo, la dirección de correo electrónico o el ID de destinatario)
1. **Actualizar datos** - Elegir opciones de actualización:
   * Actualizar solo los registros coincidentes
   * Actualizar campos existentes o solo campos vacíos
   * Insertar registros nuevos si no se encuentran coincidencias

**Escenarios comunes:**

* Actualización de atributos de perfil desde exportaciones CRM
* Actualización de los estados de suscripción de sistemas externos
* Sincronizar puntos de lealtad o puntuaciones de clientes
* Actualización de las preferencias de inclusión/exclusión
* Enriquecimiento de perfiles con datos de comportamiento

**Prácticas recomendadas:** Use identificadores únicos para la reconciliación, valide los datos antes de la actualización, realice pruebas con muestras pequeñas y programe actualizaciones regulares para la sincronización en curso.

**Temas relacionados:**

* [Guía de importación de datos](../start/import.md)
* [Actividad de carga de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=es){target="_blank"}
* [Actualizar actividad de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=es){target="_blank"}

+++

+++ ¿Cómo se pueden identificar y segmentar nuevos destinatarios?

Utilice flujos de trabajo con actividades de consulta para identificar destinatarios añadidos recientemente y déclencheur campañas de bienvenida automatizadas.

**Enfoque de consulta:**

Cree un filtro de consulta en el campo **[!UICONTROL Created date]** para seleccionar los destinatarios agregados dentro de un intervalo de tiempo específico (por ejemplo, las últimas 24 horas, la semana pasada).

**Estructura del flujo de trabajo de bienvenida automatizada:**

1. **Programador** - Ejecutar a diario o a intervalos específicos
1. **Consulta** - Seleccionar destinatarios creados desde la última ejecución
1. **Anulación de duplicación** (opcional): asegúrese de que no haya duplicados
1. **Envío** - Enviar mensaje de bienvenida
1. **Actualizar datos** (opcional): marcar los destinatarios como &quot;bienvenidos&quot;

**Técnica avanzada con agregados:**

Utilice funciones de agregado para identificar dinámicamente las adiciones más recientes y compararlas con destinatarios procesados anteriormente para detectar nuevos destinatarios sofisticados.

**Temas relacionados:**

* [Actividad de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=es){target="_blank"}
* [Uso de agregados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=es){target="_blank"}
* [Programas de bienvenida](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=es){target="_blank"}

+++

+++ ¿Cómo utilizo las actividades de flujo de trabajo?

Los flujos de trabajo de la campaña se crean utilizando cuatro categorías principales de actividades, cada una con fines específicos:

**Actividades de segmentación**: defina y perfeccione la audiencia

* Consulta, División, Deduplicación, Enriquecimiento, Intersección, Unión, Exclusión
* Úselos para seleccionar destinatarios, segmentar poblaciones y combinar fuentes de datos

**Actividades de control de flujo** - Administrar la lógica y el tiempo del flujo de trabajo

* Planificador, Espera, Prueba, Bifurcación, AND-join, OR-join, Salto
* Control del flujo de ejecución, adición de condiciones y administración de rutas paralelas

**Actividades de acción** - Realizar operaciones y enviar mensajes

* Envío, Actualización de datos, Carga de datos (archivo), Extracción de datos (archivo), Código JavaScript
* Ejecutar operaciones de base de datos, transferencias de archivos y envío de mensajes

**Actividades de eventos** - Reaccionar ante déclencheur externos

* Señal externa, Recolector de archivos, Transferencia HTTP, SMS, Correo electrónico
* Gestión de datos entrantes e interacciones con sistemas externos

Para utilizar actividades, arrástrelas desde la paleta al lienzo del flujo de trabajo, haga doble clic para configurar parámetros y conéctelos con transiciones.

**Temas relacionados:**

* [Referencia de actividades de segmentación](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=es){target="_blank"}
* [Referencia de actividades de control de flujo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=es){target="_blank"}
* [Referencia de actividades de acción](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=es){target="_blank"}
* [Referencia de actividades de eventos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=es){target="_blank"}

+++

+++ ¿Cuáles son las prácticas recomendadas de flujo de trabajo?

Siga estas prácticas recomendadas para crear flujos de trabajo eficientes, mantenibles y fiables:

**Diseño y organización:**

* Utilice nombres claros y descriptivos para los flujos de trabajo y las actividades
* Agregar etiquetas y descripciones a la lógica del documento
* Agrupar visualmente actividades relacionadas para facilitar la lectura
* Divida procesos complejos en varios flujos de trabajo más pequeños

**Optimización del rendimiento:**

* Limitar los tamaños de los resultados de consulta con los filtros adecuados
* Usar tablas temporales para el almacenamiento de datos intermedio
* Programar flujos de trabajo con uso intensivo de recursos durante las horas de menor actividad
* Evite bucles innecesarios e iteraciones excesivas

**Control y supervisión de errores:**

* Agregar rutas de control de errores con supervisores
* Configuración de alertas para flujos de trabajo con errores
* Realizar pruebas con muestras de datos pequeñas antes de la ejecución completa
* Revise los registros de ejecución regularmente para ver problemas de rendimiento

**Mantenimiento y administración:**

* Archivar o eliminar flujos de trabajo obsoletos
* Cambios en el flujo de trabajo de control de versiones y modificaciones de documentos
* Limitar la complejidad del flujo de trabajo (objetivo para &lt; 20 actividades)
* Uso de plantillas de flujo de trabajo para patrones recurrentes

**Administración de datos y seguridad:**

* Aplicar los permisos de operador adecuados
* Limpieza de datos temporales con limpieza del flujo de trabajo
* Evite codificar valores: utilice variables y opciones
* Revisar y optimizar regularmente flujos de trabajo con mal rendimiento

**Temas relacionados:**

* [Guía de prácticas recomendadas de flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=es){target="_blank"}
* [Creación de un flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=es){target="_blank"}
* [Monitorización de flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=es){target="_blank"}

+++

## Configuración de campaña {#settings}

Configure la instancia de Campaign con las configuraciones, integraciones y ajustes adecuados para optimizar las operaciones de marketing.

+++ ¿Puedo cambiar el idioma de la interfaz de Campaign? 

El idioma de Campaign se selecciona al crear la instancia. No puede cambiarlo posteriormente. Para obtener más información, consulte [esta sección](../start/connect.md).

La interfaz de usuario de Adobe Campaign está disponible en varios idiomas: inglés, francés, alemán, japonés y más. Tenga en cuenta que la consola del cliente y el servidor deben estar configurados en el mismo idioma. Cada instancia de Campaign solo puede ejecutarse en un idioma.

Para inglés, al instalar Campaign, puede seleccionar inglés de EE. UU. o inglés de Reino Unido: difieren en los formatos de fecha y hora.

+++

+++ ¿Puedo utilizar la versión 8 de Campaign con otras soluciones de Adobe?

Puede combinar las funcionalidades de entrega y las funcionalidades avanzadas de gestión de campañas de Adobe Campaign con un conjunto de soluciones creadas para ayudarle a personalizar su experiencia de usuario.

[Aprenda a trabajar con otras soluciones de Adobe](../connect/integration.md) y [a configurar IMS en Campaign](../start/connect.md).

+++

+++ ¿Cómo puedo configurar las funcionalidades de seguimiento en mi instancia de Campaign? 

Como usuario experimentado, puede configurar las funcionalidades de seguimiento en la instancia de Campaign.

[Más información](../start/tracking.md).

+++

+++ ¿Cómo configurar la entrega del correo electrónico? 

Además de la [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es){target="_blank"}, revise las recomendaciones técnicas de la capacidad de entrega para comprender cómo configurar la instancia a fin de maximizar las capacidades de entrega de Campaign.

[Más información](../send/about-deliverability.md).

+++

+++ ¿Cómo puedo implementar la aprobación de contenido? 

Campaign permite configurar los procesos de aprobación para las etapas principales de la campaña de marketing en modo de colaboración. Para cada campaña, puede aprobar el objetivo de envío, los contenidos y los costes. Los operadores de Adobe Campaign responsables de la aprobación pueden recibir notificaciones por correo electrónico y aceptar o rechazar la aprobación a través de la consola o de una conexión web.

[Obtenga más información](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=es){target="_blank"} y descubra los pasos para implementar la aprobación de su contenido de envío en Campaign.

+++

+++ ¿Cómo puedo acceder a los datos almacenados en una base de datos externa? 

Adobe Campaign proporciona la opción Acceso de datos federados (FDA) para procesar la información almacenada en una o más bases de datos externas: puede acceder a datos externos sin cambiar la estructura de los datos de Adobe Campaign.

[Más información](../connect/fda.md).

+++

+++ ¿A qué bases de datos externas puedo conectar Campaign? 

Las bases de datos externas compatibles con Campaign mediante el Acceso de datos federados (FDA) se muestra en la [matriz de compatibilidad](compatibility-matrix.md).

+++

+++ ¿Se puede integrar Adobe Campaign con sistemas CRM?

Adobe Campaign ofrece varios conectores CRM para vincular la plataforma de Adobe Campaign a los sistemas de terceros. Estos conectores de CRM le permiten sincronizar contactos, cuentas, compras, etc., para facilitar la integración de la aplicación con diversas aplicaciones de terceros y de negocios.

Estos conectores permiten una integración de datos rápida y sencilla: Adobe Campaign proporciona un asistente dedicado para recopilar y seleccionar información de las tablas disponibles en CRM. De este modo, se garantiza la sincronización bidireccional para asegurar que los datos estén actualizados en todo momento en todos los sistemas.

[Más información](../connect/crm.md) acerca de cómo sincronizar su herramienta CRM con Adobe Campaign.

+++

+++ ¿Cómo borro la caché de la consola del cliente?

Si tiene problemas como que los nuevos logotipos no se reflejen correctamente o problemas con la exportación de datos, es posible que tenga que borrar la caché de la consola del cliente.

Cierre la sesión y la consola de cliente. Navegue hasta la siguiente ubicación en función de su sistema operativo:

* Windows: `C:\Users\<Username>\AppData\Roaming\Neolane\NL_5\`
* Mac: `~/Library/Application Support/Neolane/NL_5/`

Elimine los archivos de configuración XML (conservando `nlclient_cnx.xml`) y vuelva a iniciar sesión en la consola de cliente.

+++

+++ ¿Puedo configurar los ajustes de la interfaz de usuario?

Sí, como administrador, puede personalizar la configuración de la interfaz de usuario de Campaign para los usuarios. [Más información](../config/ui-settings.md).

+++

+++ ¿Puedo crear campos y tablas personalizados?

Sí, la versión 8 de Campaign le permite ampliar el modelo de datos con campos y tablas personalizados. Aprenda a [ampliar esquemas](../dev/extend-schema.md).

+++

## Creación de informes {#reporting}

Obtenga información sobre las funcionalidades de creación de informes de Campaign, incluidos informes integrados, informes personalizados y herramientas de análisis de datos como cubos.

+++ ¿Cómo se pueden crear nuevos informes?

Además de los informes integrados, Adobe Campaign permite generar informes en distintos contextos y satisfacer diferentes necesidades.

Adobe Campaign no es una herramienta de informes especializada: los informes creados en Adobe Campaign principalmente le permiten ver los datos añadidos.

[Más información](../reporting/gs-reporting.md) acerca de las funcionalidades de informes de Campaign.

+++

+++ ¿Cómo se puede diseñar y compartir informes estadísticos sobre la población?

Los [informes de análisis descriptivos](../reporting/built-in-reports.md) de Adobe Campaign le permiten diseñar y compartir informes estadísticos sobre su población.

[Más información](../reporting/built-in-reports.md).

+++

+++ ¿Cómo se puede diseñar informes avanzados con mis datos?

Con Campaign v8, puede [crear informes avanzados](../reporting/custom-reports.md). Como usuario experto, podrá crear, actualizar y distribuir informes personalizados con sus datos.

También puede utilizar la interfaz de usuario de Campaign Web para crear informes y paneles. [Más información](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}.

+++

+++ ¿Qué es un cubo y cómo crear ese tipo de informe?

Puede ampliar las capacidades de análisis y exploración de base de datos al mismo tiempo que facilita a los usuarios finales la configuración de informes y tablas: estos últimos solo necesitan seleccionar un cubo existente (completamente configurado) al crear su informe o tabla para procesar cálculos, medidas y estadísticas.

Una vez que se han creado y configurado, los cubos se utilizan en las casillas de consulta de los informes y en las aplicaciones web. Se pueden utilizar y manipular dentro de las tablas dinámicas.

Descubra cómo [explorar sus datos](../reporting/gs-cubes.md) con cubos.

+++

+++ ¿Se puede crear un informe a partir de respuestas a una encuesta en línea?

La versión 8 de Campaign no tiene una función de encuesta integrada. Puede utilizar Adobe Experience Manager u otras soluciones web para crear encuestas.

Sin embargo, puede utilizar las funcionalidades de creación de informes para analizar los datos recopilados y crear informes personalizados.

+++

+++ ¿Cómo se puede compartir el acceso a mi informe en la interfaz de Campaign?

Puede definir en qué contexto se mostrará el informe en la interfaz de usuario de Adobe Campaign. Para obtener más información sobre el acceso a informes, consulte [esta sección](../reporting/custom-reports.md).

+++

+++ ¿Se pueden exportar informes en diferentes formatos?

Sí, los informes de Campaign se pueden exportar en distintos formatos, como Excel, PDF o CSV. [Más información](../reporting/custom-reports.md).

+++

## Desarrolladores {#developers}

Acceda a información técnica para desarrolladores, incluidos detalles del modelo de datos, esquemas, API y funcionalidades de personalización.

+++ ¿Qué es el modelo de datos de Campaign?

El modelo de datos conceptuales de la base de datos de Adobe Campaign consta de un conjunto de tablas integradas y su interacción. La estructura física y lógica de los datos que se llevan en la aplicación se describe en XML. Obedece a una gramática específica de Adobe Campaign, denominada esquema.

[Más información sobre el modelo de datos de Campaign](../dev/datamodel.md).

[Esta página enumera las prácticas recomendadas](../dev/datamodel-best-practices.md).

+++

+++ ¿Cómo se trabaja con los esquemas de Campaign?

En Adobe Campaign, los esquemas de datos se utilizan para:

* Definir el modo en que los objetos de datos de la aplicación están vinculados a las tablas de bases de datos subyacentes.
* Definir vínculos entre los diferentes objetos de datos dentro de la aplicación de Campaign.
* Definir y describir los campos individuales incluidos en cada objeto.

[Empiece a usar las tablas y los esquemas](../dev/schemas.md) para comprender cómo trabajar con el esquema de datos, ampliar y personalizar Campaign para satisfacer sus necesidades.

+++

+++ ¿Cómo se utiliza una tabla de destinatarios personalizada?

Puede crear e implementar una tabla de destinatarios no integrada en Campaign para enviar los mensajes.

[Más información](../dev/custom-recipient.md)

+++

+++ ¿Cuáles son las mejores prácticas para definir las consultas en Campaign? 

El editor de consultas de Adobe Campaign es una herramienta poderosa para explorar datos y crear segmentos.

La herramienta de consulta de Adobe Campaign se encuentra en varios niveles del software: para crear una población objetivo, segmentar clientes, extraer y filtrar logs de seguimiento, crear filtros, etc.

Puede consultar la base de datos de Campaign utilizando el editor de consultas genérico. Se accede a través del menú **Tools > Generic query editor...** Permite extraer información almacenada en una base de datos y organizar, agrupar, ordenar, etc. Por ejemplo, el usuario puede recuperar los destinatarios que han hecho clic un determinado número de veces en el vínculo de un boletín durante un periodo determinado. Esta herramienta le permite recopilar, ordenar y mostrar los resultados según sus necesidades.

[Más información](../start/query-editor.md). También puede consultar la [guía de automatización de Campaign](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=es){target="_blank"}.

+++

+++ ¿Cómo puedo importar un paquete de datos? 

Adobe Campaign permite exportar o importar la configuración y los datos de la plataforma a través de un sistema de paquetes. Los paquetes de datos permiten que las entidades de la base de datos de Adobe Campaign se muestren mediante archivos en formato XML. Cada entidad contenida en un paquete se representa con todos sus datos.

El principio de los paquetes de datos es exportar una configuración de datos e integrarla en otro sistema de Adobe Campaign.

[Más información](../dev/packages.md) sobre cómo trabajar con paquetes de datos para importar y exportar configuraciones de Campaign.

+++

+++ ¿Dónde puedo encontrar la lista de las API de Campaign v8?

Todas las API de Campaign, con su descripción completa, están disponibles en esta [documentación dedicada](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=es){target="_blank"}.

+++

+++ ¿Qué es la API de REST de Campaign?

La versión 8 de Campaign expone un conjunto de API de REST que le permiten crear integraciones para Adobe Campaign y construir su propio ecosistema al interconectar Adobe Campaign con el panel de tecnologías que utiliza.

[Más información](../dev/api/get-started-apis.md).

+++

+++ ¿Cómo superviso los flujos de trabajo desde la API?

Aprenda a monitorizar los flujos de trabajo mediante las API de Campaign en [esta página dedicada](../dev/api/controlling-a-workflow.md).

+++

+++ ¿Cómo se puede actualizar la estructura de la base de datos?

Si modifica los esquemas de datos de Campaign, debe actualizar la estructura de la base de datos. Aprenda en [esta sección](../dev/update-database-structure.md).

+++

+++ ¿Cuáles son las limitaciones de Campaign v8?

La versión 8 de Campaign tiene algunas limitaciones en comparación con la versión 7 de Campaign Classic, que se detallan en [esta página](../start/v7-to-v8.md#limitations).

+++

## Privacidad {#privacy}

Comprenda cómo Adobe Campaign le ayuda a cumplir con las regulaciones de privacidad, como el RGPD y la CCPA, y a administrar las solicitudes de los interesados.

+++ ¿Cuáles son los términos clave sobre la privacidad?

Los elementos que se enumeran a continuación vinculan los términos y conceptos clave relacionados con la privacidad y el consentimiento en Adobe Campaign:

* [Regulaciones sobre administración de la privacidad](../start/privacy.md#privacy-regulations)
* [Datos personales y personas](../start/privacy.md#personal-data)
* [Derecho de acceso y Derecho a ser olvidado](../start/privacy.md#right-access-forgotten)
* [Consentimiento, retención y funciones](../start/privacy.md#consent-retention-roles)

+++

+++ ¿Cuál es la sugerencia de Adobe Campaign para cumplir con las regulaciones de privacidad más recientes?

Adobe no proporciona asesoramiento legal. Debe trabajar con su propio asesor legal para asegurarse de que está tomando todas las medidas necesarias para cumplir con las normas de privacidad RGPD, CCPA, PDPA, LGPD o cualquier otra norma legal aplicable.

**Preparación para las solicitudes de acceso a datos y eliminación**

* Identifique el proceso para recibir/responder a las solicitudes del sujeto de datos, incluido el nombramiento de un punto de contacto de privacidad.

* Revise los distintos datos de cliente almacenados en Adobe Campaign y determine identificadores únicos (probablemente habrá más de uno).

* Determine la directiva de validación/autenticación y el proceso para la confirmación de identidad del sujeto de datos.

* Asegúrese de que la respuesta del sujeto de datos sea fácil de entender.

**Consideración del consentimiento**

* Enumere y actualice según sea necesario, todos los puntos de contacto para la captura de datos del RGPD (es decir, considere el idioma, el mecanismo para el consentimiento y los registros de consentimientos).

* Asegúrese de que todos los correos electrónicos de marketing incluyan los vínculos de cancelación de suscripción.

* Evalúe la estrategia global de marketing por correo electrónico para determinar las implementaciones específicas de cada ubicación geográfica.

**Comprensión de los datos**

* Revise todos los orígenes de captura e importación de datos en las que los datos fluyen a Adobe Campaign y documente los campos que se utilizan para las actividades de marketing.

* Quite los atributos de datos que no se utilicen de la base de datos de Adobe Campaign.

* Utilice los datos disponibles en Adobe Campaign para comprobar la calidad de la captura y ofrecer a sus destinatarios experiencias más personalizadas.

* Revise y actualice los permisos de acceso a los datos para garantizar que los usuarios de Adobe Campaign puedan aprovechar por completo solo los datos necesarios para ejecutar sus campañas, pero no acceder a ningún dato aparte de esto.

* Asegúrese de que cada usuario de Adobe Campaign tenga los derechos de acceso adecuados para realizar las tareas necesarias, pero no tenga ningún otro derecho para realizar tareas adicionales.

+++

+++ ¿Cómo pueden obtener consentimiento los controladores de datos con un impacto mínimo en la participación del usuario?

En los casos en que se necesite el consentimiento para determinadas actividades de marketing, el consentimiento del consumidor deberá estar activo (es decir, no habrá silencio como casillas de verificación o de aprobación), no agrupado y puede no estar condicionado a la oferta de los servicios.

Puede incluso haber casos en los que sea necesario actualizar ciertos consentimientos para poder seguir utilizando datos a partir de ahora.

Los especialistas en marketing deben adoptar estos requisitos de consentimiento mejorados como un verdadero indicador de la implicación y lealtad con la marca, así como de la satisfacción y la confianza de los clientes.

+++

+++ ¿Cómo pueden los controladores de datos administrar el consentimiento en Adobe Campaign?

Adobe Campaign ya ofrece capacidades para administrar el consentimiento en más niveles que la mayoría de los expertos en marketing mediante campos de datos personalizados o a través de uno o más servicios.

Los expertos en marketing deben consultar con el asesor legal para obtener instrucciones sobre cómo proceder y luego aprovechar las capacidades ya integradas en Adobe Campaign.

Por ejemplo: ampliar el modelo de datos en Adobe Campaign para rastrear no solo si las personas han elegido participar, sino también la marca de tiempo de la inclusión y algún tipo de indicador que capture el ámbito preciso del consentimiento.

+++

+++ ¿Qué datos pueden eliminar los controladores de datos en Adobe Campaign en respuesta a una solicitud del cliente de un sujeto de datos?

Se eliminarán todos los datos asociados al sujeto de datos, incluidas las tablas predeterminadas y las personalizadas.

Técnicamente, se eliminarán todos los datos vinculados al sujeto de datos con `integrity="own"` .

Como controlador de datos, tiene la opción de personalizarlos cambiando la integridad de los vínculos definidos en los esquemas de datos (por ejemplo, si tiene una justificación comercial para no eliminar determinados datos).

+++

+++ ¿En qué afecta a los informes cuando se eliminan entregas y registros de seguimiento?

Los informes de Adobe Campaign se basan en indicadores calculados a partir de los datos agregados de entregas y registros de seguimiento. Como resultado, la eliminación de los registros individuales no debería afectar a las métricas de los informes.

+++

+++ ¿Debo tener en cuenta la posibilidad de volver a importar los datos más adelante?

En Adobe Campaign, los registros suelen cargarse desde una fuente de datos externa.

Como controlador de datos, deberá asegurarse de que, cuando reciba una solicitud de eliminación, elimine todos los datos necesarios sobre el sujeto de datos de todos los sistemas.

+++

+++ ¿Puede un sujeto de datos, cuyos datos se han borrado de Adobe Campaign, adherirse nuevamente más adelante?

Es posible que un sujeto de datos vuelva a incluirse o se añada como un nuevo destinatario después de que sus datos se hayan borrado de Adobe Campaign.

Puede utilizar la pista de auditoría que detalla cuándo se realizó la eliminación anterior y cuándo se creó el nuevo destinatario.

+++

## ¿Todavía necesitas ayuda? {#get-help}

¿No encuentras lo que estás buscando? Estos son recursos adicionales para ayudarle a tener éxito con Adobe Campaign v8.

### Compatibilidad con la comunidad

Conéctese con otros usuarios de Campaign y con expertos en Adobe para compartir conocimientos y obtener respuestas.

* **[Comunidad de Adobe Campaign](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=es){target="_blank"}**: haga preguntas, comparta soluciones y conecte con la comunidad de Campaign
* **[Foros de Experience League](https://experienceleaguecommunities.adobe.com/?profile.language=es){target="_blank"}**: Examine los debates en todos los productos de Adobe
* **[Horario de oficina de la comunidad de Campaign](https://experienceleague.adobe.com/es){target="_blank"}**: únase a las sesiones en directo con los expertos de Adobe

### Documentación y aprendizaje

Acceda a guías completas, tutoriales y materiales de formación.

* **[Página de inicio de documentación de Campaign v8](../campaign-home.md)**: documentación completa del producto
* **[Tutoriales de Campaign](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=es){target="_blank"}**: guías de vídeo paso a paso y tutoriales prácticos
* **[Novedades](whats-new.md)**: características y funciones más recientes
* **[Notas de la versión](release-notes.md)** - Información de la versión actual y anterior
* **[Prácticas recomendadas](delivery-best-practices.md)** - Enfoques recomendados para tareas comunes

### Recursos técnicos

Encuentre documentación técnica detallada y recursos para desarrolladores.

* **[API de Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=es){target="_blank"}**: documentación de referencia de API completa
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.es-ES)**: Contribuya a la documentación
* **[Notas técnicas](https://experienceleague.adobe.com/es/docs/campaign/technotes-ac/technotes-home){target="_blank"}**: artículos técnicos detallados
* **[Matriz de compatibilidad](compatibility-matrix.md)** - Sistemas y versiones compatibles

### Asistencia y servicios

Obtenga ayuda del equipo de asistencia de Adobe y administre su instancia.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Registrar casos de soporte y administrar usuarios
* **[Servicio de atención al cliente de Adobe](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Comuníquese con el equipo de atención al cliente
* **[Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es){target="_blank"}** - Administrar la configuración de la instancia de Campaign
* **[Estado del sistema](https://status.adobe.com/){target="_blank"}** - Comprobar el estado de los servicios de Adobe

### Formación y certificación

Mejore sus aptitudes con los programas oficiales de formación y certificación de Adobe.

* **[Servicios de aprendizaje digital de Adobe](https://learning.adobe.com/){target="_blank"}** - Cursos oficiales guiados por instructores y con ritmo personalizado
* **[Certificación Adobe Campaign](https://experienceleague.adobe.com/docs/certification/program/overview.html?lang=es){target="_blank"}** - Valide su experiencia con certificación profesional
* **[Rutas de aprendizaje de Experience League](https://experienceleague.adobe.com/?lang=es#dashboard/learning){target="_blank"}** - recorridos de aprendizaje guiados

### Otros recursos útiles

* **[Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=es){target="_blank"}** - Referencia para usuarios de Classic v7
* **[Documentación de la interfaz de usuario web de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Nueva guía de la interfaz web
* **[Prácticas recomendadas de envío](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es){target="_blank"}** - Optimizar envío de correo electrónico
* **[Actualizaciones de productos](https://experienceleague.adobe.com/es/docs/release-notes/experience-cloud/current){target="_blank"}**: últimas actualizaciones de Adobe Experience Cloud

**Última actualización:** noviembre de 2025 | **Se aplica a:** Campaign v8.6 y versiones posteriores

*¿Encontró un error o desea sugerir una mejora? [Editar esta página en GitHub](https://github.com/AdobeDocs/campaign.es-ES/edit/main/help/v8/start/campaign-faq-comprehensive.md)*

