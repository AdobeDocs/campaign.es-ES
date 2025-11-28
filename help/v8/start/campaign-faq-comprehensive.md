---
title: Preguntas más frecuentes sobre la versión 8 de Campaign
description: Obtenga respuestas a preguntas comunes de la versión 8 de Adobe Campaign sobre configuración, mensajería, flujos de trabajo y mucho más
feature: Overview
role: User
level: Beginner
keywords: Preguntas más frecuentes, Campaign v8, preguntas, respuestas, ayuda, asistencia, solución de problemas
hide: true
hidefromtoc: true
source-git-commit: 4f9b580ed4aeec0666fcb3343861b955a6787f01
workflow-type: tm+mt
source-wordcount: '12425'
ht-degree: 10%

---

# Preguntas frecuentes {#faq}

Obtenga respuestas rápidas a las preguntas más comunes sobre Adobe Campaign v8. Tanto si acaba de empezar como si busca ayuda para la configuración avanzada, encontrará respuestas organizadas por temas a continuación.

**¿Es nuevo en Campaign?** comienza con [Preguntas generales](#general) y [Conceptos clave](#key-concepts).\
**¿Necesita ayuda técnica?**: comprobar [desarrolladores](#developers) y [configuración de la campaña](#settings).\
**¿No encuentra la respuesta?** Visite nuestros [Foros de la comunidad](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=es){target="_blank"} o [comuníquese con la atención al cliente](#get-help).

**Sugerencia:** Utilice Ctrl+F (Cmd+F en Mac) para buscar palabras clave específicas en esta página. Haga clic en cualquier pregunta para ampliar la respuesta.


## Preguntas generales {#general}

Obtenga respuestas a las preguntas más comunes sobre Adobe Campaign v8, como cómo conectarse, actualizar y obtener asistencia.

+++ ¿Cómo puedo conectarme a Campaign v8?

Debe descargar e instalar la consola del cliente de Campaign para conectarse a Adobe Campaign.

[Haga clic aquí para obtener más información](connect.md).

A partir de la versión 8.6 de Campaign, tiene acceso a la **interfaz de usuario web de Campaign**, disponible a través del entorno central de Adobe Experience Cloud. Experience Cloud es la familia integrada de aplicaciones, productos y servicios de marketing digital de Adobe.

Obtenga información sobre cómo conectarse a Adobe Experience Cloud y obtener acceso a la interfaz web de Adobe Campaign [en esta página](campaign-ui.md#ac-web-ui). Obtenga más información en la [documentación de la interfaz de usuario web de Adobe Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Temas relacionados:**

* [Instalación de la consola de cliente](connect.md)
* [Interfaz de usuario de Campaign](campaign-ui.md)
* [Permisos de usuario](gs-permissions.md)

+++

+++ ¿Se puede instalar Campaign v8 en un entorno local o híbrido?

No. La versión 8 de Campaign está disponible exclusivamente como **Cloud Service administrado**, totalmente alojado por Adobe.

**Ventajas clave de Managed Cloud Services:**

* Rendimiento y capacidad de ampliación superiores
* Actualizaciones automáticas: siempre en la versión más reciente
* Seguridad mejorada con supervisión continua
* Sin administración de infraestructura ni sobrecarga de TI
* Alta disponibilidad integrada y recuperación ante desastres

Obtenga más información acerca de la [arquitectura de Campaign v8](../architecture/architecture.md) y las [diferencias entre Campaign v8 y Classic v7](../start/v7-to-v8.md).

+++

+++ ¿Cómo puedo actualizar Campaign a la versión más reciente?

Adobe Campaign se actualiza periódicamente. Cada año se publican versiones menores con nuevas funciones, mejoras y correcciones. Además, lanzamos versiones periódicamente solamente con correcciones acumulativas.

Esta frecuencia regular de actualizaciones tiene como objetivo ofrecerle lo más novedoso y lo mejor, mantener el entorno seguro y mejorar su experiencia con nuestro producto. Esta es la razón por la que creemos que es esencial que ejecute la versión más reciente de Adobe Campaign.

**Nota:** Como usuario de Cloud Services administrados, Adobe actualiza su instancia con nuevas versiones.

Más información sobre [versiones y actualizaciones de Campaign](upgrades.md).

+++

+++ ¿Cómo configurar el envío del correo electrónico?

La capacidad de envío de correo electrónico, un componente esencial para el éxito del programa de marketing de cada remitente, se caracteriza por criterios y reglas que cambian constantemente. La navegación eficaz en este mundo digital requiere un ajuste regular de su estrategia de correo electrónico, teniendo en cuenta las tendencias clave de envío, para llegar mejor a su público.

Consulte esta guía para obtener más información [Prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es){target="_blank"}

Aprenda a implementar la entregabilidad en Campaign [con esta guía](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=es){target="_blank"}

**Temas relacionados:**

[Acerca de la capacidad de entrega](../send/about-deliverability.md) | [Control del contenido del mensaje](../send/control-message-content.md) | [Supervisar la capacidad de entrega](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ ¿Cómo puedo asegurarme de que mi entrega se envíe sin errores?

Siga estos pasos para garantizar una entrega correcta:

**Antes de enviar:**

* Ejecutar el análisis de envío para detectar errores (falta personalización, destinatarios no válidos, problemas de contenido)
* Envíe pruebas de prueba para verificar el procesamiento y la personalización
* Revisar advertencias durante la preparación
* Verificar recuento de población objetivo

**Durante y después de enviar:**

* Monitorización del panel de envío para estadísticas en tiempo real (envíos, envíos, devoluciones, errores)
* Comprobar registros de envío para el estado de nivel de mensaje
* Seguimiento de la tasa de éxito, la tasa de devolución y los mensajes de error
* Revisar direcciones en cuarentena

**Prácticas recomendadas:**

* Configuración de alertas para umbrales de error
* Utilizar olas (envío por lotes) para grandes volúmenes
* Pruebe primero con volúmenes pequeños
* Limpieza periódica de la base de datos de destinatarios
* Monitorización de la reputación del remitente

Obtenga más información acerca de [supervisar entregas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es){target="_blank"} y [prácticas recomendadas de entrega](delivery-best-practices.md).

+++

+++ ¿Se puede monitorizar la ejecución del flujo de trabajo?

Sí. Campaign proporciona varias herramientas para monitorizar la ejecución del flujo de trabajo:

* **Panel de flujo de trabajo**: vea el estado en tiempo real, el progreso y los errores de cada actividad de flujo de trabajo
* **[Registros de flujo de trabajo](https://experienceleague.adobe.com/es/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#displaying-logs){target="_blank"}**: acceda a los registros de ejecución detallados para solucionar problemas
* **[Mapa de calor](https://experienceleague.adobe.com/es/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}**: visualice la actividad del flujo de trabajo e identifique cuellos de botella de rendimiento
* **[Pista de auditoría](../reporting/audit-trail.md)**: efectúe el seguimiento de todas las modificaciones realizadas en los flujos de trabajo
* **[Alertas](https://experienceleague.adobe.com/es/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators){target="_blank"}**: configure notificaciones para errores o retrasos del flujo de trabajo

Para supervisar un flujo de trabajo, ábralo y haga clic en la ficha **Registros**. Las actividades fallidas se resaltan en rojo y puede ver los detalles del error haciendo clic en ellas.

Obtenga más información acerca de [supervisar la ejecución del flujo de trabajo](https://experienceleague.adobe.com/es/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} y [prácticas recomendadas del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=es){target="_blank"}.

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

Compruebe su [versión y su número integrado](upgrades.md#version) en el menú **Ayuda > Acerca de...** de la consola del cliente de Campaign.

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

Comprenda las diferencias clave entre Campaign v8 y las versiones anteriores (Classic v7 y Standard), incluida la arquitectura, la implementación, las rutas de migración y los cambios de funciones. Tanto si viene de Campaign Classic v7 como de Campaign Standard, aprenda las novedades y cómo realizar la transición sin problemas.

+++ ¿Cuáles son las principales diferencias entre la versión 8 de Campaign y las versiones anteriores?

La versión 8 de Campaign es una completa reinvención de Adobe Campaign, diseñada para una arquitectura moderna nativa de la nube y que ofrece mejoras significativas con respecto a la versión 7 de Campaign Classic y a la Campaign Standard:

**Modelo de implementación:**

* **v8:** solo servicios administrados en la nube: totalmente hospedado y administrado por Adobe
* **v7/Standard:** Hay disponibles opciones locales, híbridas o hospedadas
* **Beneficio:** administración de infraestructura cero, escalado automático, seguridad de nivel empresarial, supervisión proactiva

**Arquitectura y rendimiento:**

* **v8:** arquitectura de FDA completo (FDAC) mejorada con base de datos PostgreSQL
* **v8:** Rendimiento de procesamiento por lotes que alcanza hasta **20 millones de operaciones por hora**
* **v8:** Rendimiento de mensajes transaccionales de **1 millón por hora**
* **v8:** Exploración de datos en tiempo real y creación rápida de audiencias (minutos vs. horas)
* **Beneficio:** Mejor rendimiento para operaciones a gran escala y campañas complejas

**Interfaz de usuario:**

* **v8:** Nueva **interfaz de usuario web de Campaign** junto con la consola del cliente: intuitiva, accesible e ideal para los especialistas en marketing
* **v8:** Diseño moderno y adaptable con capacidades de arrastrar y soltar
* **v8:** Flujos de trabajo simplificados de administración y creación de campañas
* **v8:** comparte muchas similitudes con la interfaz de Campaign Standard
* **Beneficio:** Incorporación más rápida, ejecución de campañas más sencilla, mejor accesibilidad, curva de aprendizaje mínima

**Nuevas características clave:**

* **Notificaciones push enriquecidas** con imágenes, vídeos, botones interactivos, carruseles y temporizadores
* **Asistente de IA** para la generación de contenido (correo electrónico, SMS, push) con puntuación de alineación de marca
* **Infraestructura de SMS actualizada (SMS v2.0)** con confiabilidad y compatibilidad mejoradas
* **Integración de Adobe Experience Manager as a Cloud Service** para una administración de contenido perfecta
* **Informes mejorados** que incluyen informes dinámicos para usuarios de Campaign Standard

**Actualizaciones y mantenimiento:**

* **v8:** actualizaciones automáticas administradas por Adobe: siempre en la última versión estable con modelo de entrega continua
* **v7/Standard:** Se requiere la planificación y ejecución manual de la actualización
* **Beneficio:** Menor carga de mantenimiento, acceso inmediato a nuevas funciones, sin tiempo de inactividad

**API e integración:**

* **v8:** API de REST modernas con rendimiento y confiabilidad mejorados
* **v8:** integración perfecta con Adobe Experience Cloud y Adobe Experience Platform
* **Ventaja:** integraciones más sencillas, mejor interoperabilidad y prácticas de desarrollo modernas

[Obtenga más información acerca de las funcionalidades clave de Campaign v8](whats-new.md)

**Temas relacionados:**

* [De Campaign Classic v7 a v8](v7-to-v8.md) | [Guía de transición de v7 a v8](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}
* [De Campaign Standard a la versión 8](acs-to-v8.md) | [Transición de Campaign Standard](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}
* [Guía de adopción de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign-web/acs-to-ac/home){target="_blank"}
* [Matriz de capacidades de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Arquitectura de la versión 8 de Campaign](../architecture/architecture.md)
* [Mecanismos de protección y limitaciones](ac-guardrails.md)

+++

+++ ¿Debería migrar de Campaign Classic v7 o Campaign Standard a v8?

**Campaign v8 es ideal para las organizaciones que necesitan:**

* **Campañas de gran volumen**: envía millones de mensajes con rendimiento y fiabilidad mejorados (20 millones de operaciones por hora)
* **Escalabilidad empresarial**: amplíe su base de datos y sus campañas sin problemas de rendimiento
* **Interfaz de usuario web moderna**: IU web de Campaign intuitiva y adaptable para una creación de campañas más rápida y una experiencia de usuario mejorada
* **Ventajas nativas de la nube**: aproveche las actualizaciones automáticas, la infraestructura administrada, la escala elástica y la supervisión proactiva
* **Soporte a largo plazo**: Campaign v8 es la plataforma estratégica de Adobe con soporte ampliado, mientras que las versiones anteriores llegarán al fin del soporte en los próximos años
* **Reducción de la sobrecarga de TI**: elimine la administración de la infraestructura y la planificación de la actualización
* **Funciones avanzadas**: asistente de IA, push enriquecida, SMS mejorado, integración con Adobe Experience Platform

**Para usuarios de Campaign Standard:**

Los usuarios de Campaign Standard ahora pueden realizar la transición a Cloud Services administrados de Campaign v8. Las ventajas principales incluyen:

* **Interfaz familiar**: La interfaz de usuario web de Campaign comparte muchas similitudes con Campaign Standard, lo que minimiza la curva de aprendizaje
* **Paridad de características**: Se han agregado las funciones clave de Campaign Standard a la versión 8 (Informes dinámicos, promoción centralizada de marca, API de REST, páginas de aterrizaje, fragmentos visuales)
* **Soporte mejorado**: asistencia de primer nivel con transición sin problemas y supervisión continua de la plataforma
* **Migración de datos**: Todos los datos de Campaign Standard se importan con una interrupción mínima
* **Experiencia de usuario coherente**: siga trabajando con flujos de trabajo e interfaz familiares

**Para usuarios de Campaign Classic v7:**

Campaign v8 ofrece mejoras sustanciales al tiempo que mantiene las funcionalidades principales de Campaign:

* **Interfaz doble**: acceda a la potente consola del cliente y a la moderna interfaz de usuario de Campaign web
* **Mejor rendimiento**: rendimiento de consultas y procesamiento de datos significativamente mejorados
* **Ventajas de la nube**: Actualizaciones automáticas, parches de seguridad, copia de seguridad o recuperación administrados por Adobe
* **Arquitectura moderna**: arquitectura de FDAC mejorada con PostgreSQL para una mejor escalabilidad

**Cuándo considerar la migración:**

* La instancia actual de Campaign administra grandes volúmenes de datos (millones de perfiles)
* Está experimentando problemas de rendimiento con flujos de trabajo o direccionamiento complejos
* Desea reducir los costes de mantenimiento y gestión de la infraestructura
* Necesita una integración perfecta con Adobe Experience Cloud o Adobe Experience Platform
* De todos modos, está planeando una actualización importante o una actualización de la infraestructura
* **Desea tecnología preparada para el futuro**. Las versiones anteriores llegarán al fin del soporte técnico
* **Su equipo necesita una interfaz moderna**. La interfaz de usuario web de Campaign ofrece una mejor accesibilidad para los especialistas en marketing

**Consideraciones de migración:**

* Adobe proporciona soporte, orientación y herramientas para la migración
* v8 solo es Cloud Service administrado (sin implementación local o híbrida)
* Algunas implementaciones técnicas pueden diferir; revise la [matriz de capacidades](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* La migración y las pruebas de datos requieren planificación y recursos
* **Para usuarios de Campaign Standard**: la transición está diseñada para ser fluida con una interrupción mínima del flujo de trabajo

**Pasos siguientes:**

Póngase en contacto con su representante de Adobe para:

* Evalúe la preparación y el calendario de la migración
* Comprenda las ventajas específicas de su caso de uso
* Planificar la estrategia de migración y la asignación de recursos
* Acceso a herramientas de migración y asistencia

**Temas relacionados:**

**Para usuarios de Campaign Classic v7:**

* [De Campaign Classic v7 a v8](v7-to-v8.md)
* [Guía detallada de las versiones 7 a 8](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**Para usuarios de Campaign Standard:**

* [Transición de Campaign Standard a la versión 8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}
* [Guía de adopción de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign-web/acs-to-ac/home){target="_blank"}
* [Información general de Campaign Standard a la versión 8](https://experienceleague.adobe.com/es/docs/campaign-web/acs-to-ac/overview){target="_blank"}
* [Introducción para especialistas en marketing](https://experienceleague.adobe.com/es/docs/campaign-web/acs-to-ac/marketers){target="_blank"}
* [Introducción para administradores/desarrolladores](https://experienceleague.adobe.com/es/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**Recursos generales:**

* [Matriz de capacidades de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Matriz de compatibilidad](compatibility-matrix.md)

+++

+++ ¿Cuáles son las diferencias clave de terminología y características en la versión 8 de Campaign?

La versión 8 de Campaign incorpora mejoras en la mayoría de las funciones de Campaign Classic v7 y Campaign Standard, pero algunas funciones han sufrido cambios debido a la arquitectura nativa de la nube de, y parte de la terminología difiere entre las versiones.

**Diferencias terminológicas (de Campaign Standard a v8):**

* **Los recursos personalizados** ahora son **Esquemas**
* **Los mensajes** se denominan **envíos**
* **Los usuarios de productos** ahora son **Operadores**
* **Los roles** se han configurado con **Derechos asignados**
* **Los grupos de seguridad** ahora son **grupos de operadores**
* Las **unidades organizativas** se administran mediante **permisos de carpeta**

**Actualizaciones terminológicas de la interfaz de usuario web de Campaign:**

Los siguientes términos se han actualizado en la interfaz de usuario web de Campaign (la consola del cliente utiliza términos tradicionales):

* **Los destinatarios** ahora son **Perfiles**
* **Las direcciones semilla** ahora son **perfiles de prueba**
* **Análisis de envío** es ahora **Preparación de envío** (haga clic en el botón **Preparar**)
* **Vista previa del correo electrónico** está disponible a través del botón **Simular contenido**
* **Listas** son ahora **Audiencias**

**No disponible en la versión 8:**

* **Implementaciones locales e híbridas**: La versión 8 de solo es Managed Cloud Services
* **Acceso directo a la base de datos**: en su lugar, use las API y herramientas proporcionadas
* **Infraestructura administrada por el cliente**: Adobe administra toda la infraestructura
* **Actualizaciones manuales de la compilación**: ahora automáticas (administradas por Adobe)

**Diferentes implementaciones en la versión 8:**

* **Flujos de trabajo técnicos**: algunos optimizados para la arquitectura en la nube pueden funcionar de forma diferente
* **Estructura de la base de datos** - La arquitectura de FDAC mejorada puede requerir adaptaciones de esquema
* **Integraciones personalizadas**: es posible que necesite actualizaciones para la arquitectura basada en la nube
* **Personalizaciones de bajo nivel**: algunas requieren enfoques diferentes en un entorno administrado

**Mejorado o reemplazado en la versión 8:**

* **Actualizaciones de compilación**: automática con modelo de entrega continua en lugar de manual
* **Ajuste del rendimiento** - Administrado por la optimización de la infraestructura de Adobe
* **Parches de seguridad**: aplicados automáticamente por Adobe
* **Copia de seguridad y recuperación** - Administrado por Adobe como parte del servicio
* **Interfaz de usuario**: nueva interfaz de usuario web de Campaign junto con la consola del cliente

**Funciones agregadas para los usuarios de Campaign Standard que realizan la transición a la versión 8:**

* **Informes dinámicos**: informes personalizables en tiempo real con análisis demográfico
* **Marca centralizada**: defina las directrices técnicas y visuales de la marca
* **API de REST**: cree integraciones y construya su ecosistema
* **Mejoras en las páginas de aterrizaje**: paridad de características mejorada con Campaign Standard
* **Fragmentos visuales**: componentes visuales reutilizables para correos electrónicos y plantillas de contenido

**Importante:** La mayoría de las características operativas y de marketing están disponibles y mejoradas en la versión 8. Adobe administra las funciones técnicas y de nivel de infraestructura en el entorno de la nube.

**Temas relacionados:**

* [Matriz de capacidades](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/capability-matrix){target="_blank"} - Comparar características entre interfaces
* [Matriz de compatibilidad](compatibility-matrix.md) - Sistemas y componentes compatibles
* [Mecanismos de protección y limitaciones](ac-guardrails.md)
* [Guía de transición de v7 a v8](v7-to-v8.md)
* [Transición de Campaign Standard a la versión 8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}

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

**Sugerencia:** utilice flujos de trabajo para listas que requieran actualizaciones regulares y creación manual para segmentación única.

[Crear audiencias](../audiences/create-audiences.md) | [Actividad de actualización de lista](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html?lang=es){target="_blank"}

+++

+++ ¿Cómo duplicar una población antes de enviar un mensaje? 

Utilice la actividad **[!UICONTROL Deduplication]** en un flujo de trabajo para eliminar los destinatarios duplicados antes de la entrega. Colóquela entre sus actividades **[!UICONTROL Query]** y **[!UICONTROL Delivery]** y, a continuación, elija los criterios de anulación de duplicación (generalmente la dirección de correo electrónico o el ID de destinatario) y qué registro desea mantener.

**Sugerencia:** Anule siempre la duplicación antes de enviar para asegurarse de que cada persona reciba su mensaje solo una vez.

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

**Sugerencia:** Para obtener la mejor experiencia de diseño de correo electrónico, use **Email Designer** en la interfaz de usuario de Campaign Web, que ofrece funciones modernas de arrastrar y soltar y plantillas adaptables integradas, en lugar de importar HTML sin procesar.

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

**Nota:** El Asistente de IA está disponible exclusivamente en la interfaz de usuario de Campaign Web y actualmente solo admite inglés. Los usuarios necesitan los permisos adecuados y deben aceptar un acuerdo de usuario.

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

**Sugerencia:** Utilice la interfaz de usuario web de Campaign para crear correos electrónicos de forma más rápida e intuitiva con herramientas de diseño modernas. Utilice la consola del cliente para segmentar campañas complejas o avanzadas basadas en flujos de trabajo.

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

**Sugerencia:** Supervise la lista de cuarentena regularmente. El aumento de las tasas de cuarentena suele indicar problemas de calidad de datos que requieren atención antes de que afecten a la reputación del remitente.

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

Depende de la interfaz que esté utilizando. El idioma de la consola de cliente **1&rbrace; es fijo, pero la interfaz de usuario web de** Campaign **permite que los usuarios individuales cambien sus preferencias de idioma.**

**Consola de cliente (aplicación de escritorio):**

* El idioma se establece cuando se crea la instancia y no se puede cambiar
* La consola de cliente y el servidor deben utilizar el mismo idioma
* Cada instancia de Campaign funciona en un solo idioma
* Para las instalaciones en inglés, puede elegir entre inglés de EE. UU. o inglés de Reino Unido (difieren en los formatos de fecha y hora)

**IU web de Campaign:**

* Los usuarios pueden cambiar el idioma de la interfaz de forma independiente mediante las preferencias de perfil
* Se admiten varios idiomas con un formato específico de la configuración regional para fechas, horas y números
* La preferencia de idioma de la interfaz de usuario web es independiente del idioma del servidor de Campaign y de la consola del cliente


[Cambiar idioma en la interfaz de usuario web de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Introducción a la consola del cliente de Campaign](connect.md)

+++

+++ ¿Puedo utilizar la versión 8 de Campaign con otras soluciones de Adobe?

Sí. La versión 8 de Campaign se integra perfectamente con las soluciones de Adobe Experience Cloud para crear un ecosistema de marketing potente y unificado. La versión 8 de As a Managed Cloud Service está diseñada para la integración nativa con las aplicaciones empresariales de Adobe.

**Integraciones clave disponibles:**

* **Adobe Experience Platform**: aproveche perfiles unificados de clientes y datos en tiempo real
* **Adobe Analytics**: mida el rendimiento de la campaña y el comportamiento del cliente en todos los canales
* **Adobe Target**: personalice el contenido en función de los segmentos y el comportamiento de los clientes
* **Adobe Experience Manager**: centralice la creación de contenido y la administración de recursos
* **Adobe Audience Manager**: cree y active segmentos de audiencia en todas las plataformas

**Ventajas:** datos de clientes unificados, experiencias de usuario coherentes, flujos de trabajo optimizados y funciones de personalización mejoradas.

**Configuración:** La integración con las soluciones de Adobe requiere la autenticación de Adobe Identity Management System (IMS), configurada automáticamente para Managed Cloud Services de Campaign v8.

[integraciones de Adobe Campaign](../connect/integration.md) | [Conectar con Adobe ID](connect.md)

+++

+++ ¿Cómo puedo configurar las funcionalidades de seguimiento en mi instancia de Campaign? 

La versión 8 de Campaign proporciona un seguimiento completo para supervisar las interacciones de los destinatarios con los mensajes. El seguimiento requiere la configuración adecuada de la instancia y la configuración del mensaje.

**Lo que puede rastrear:**

* **Aperturas del correo electrónico** - A través del píxel de seguimiento (imagen transparente 1x1)
* **Clics en vínculos**: todas las direcciones URL se convierten automáticamente en vínculos rastreados
* **Cancela la suscripción** - Seguimiento de vínculos de no participación
* **Vistas de página espejo**: cuando los destinatarios ven la versión web
* **Parámetros personalizados**: agregue datos de seguimiento a las direcciones URL para realizar análisis avanzados

**Pasos de configuración clave:**

1. Configure la URL del servidor de seguimiento en la configuración de la instancia (administrada por Adobe para la versión 8)
2. Habilitar el seguimiento en las propiedades de envío
3. Configurar automáticamente el seguimiento de vínculos individuales o de todos los vínculos
4. Definir el periodo de validez de seguimiento y la retención de registros

**Práctica recomendada:** Pruebe siempre el seguimiento con pruebas antes de enviarlo a la audiencia principal para asegurarse de que los vínculos funcionan correctamente y de que se capturan los datos.

[Seguimiento y monitorización de entregas](tracking.md) | [Configurar vínculos rastreados](../send/email.md)

+++

+++ ¿Cómo configurar la entrega del correo electrónico? 

La capacidad de envío de correo electrónico depende de la configuración técnica, la calidad del contenido y la reputación del remitente. La versión 8 de Campaign proporciona herramientas y configuraciones para optimizar la ubicación de la bandeja de entrada.

**Pasos esenciales de configuración:**

* **Autenticación de dominio**: configure registros SPF, DKIM y DMARC para comprobar el dominio de envío
* **Calentamiento de IP**: aumente gradualmente el volumen de envío en nuevas IP para crear reputación
* **Configuración del remitente**: utilice nombres y direcciones de remitente coherentes y reconocibles
* **Administración de devoluciones**: configure reglas de cuarentena para administrar devoluciones suaves y duras automáticamente
* **Bucles de comentarios**: configure la administración de quejas para administrar los informes de spam

**Prácticas recomendadas de contenido:**

* Prueba de correos electrónicos con SpamAssassin para comprobar la puntuación de spam
* Mantener una proporción de texto e imagen adecuada
* Incluir versión de texto sin formato junto con HTML
* Proporcionar siempre el vínculo de cancelación de suscripción
* Evite el déclencheur de palabras no deseadas y las mayúsculas excesivas

**Supervisión:** Utilice los informes de envío de Campaign para rastrear las tasas de devolución, las tasas de quejas y la ubicación en la bandeja de entrada. Para la versión 8 de Campaign, Adobe proporciona una optimización de la capacidad de envío a nivel de infraestructura.

[Acerca de la capacidad de entrega en Campaign](../send/about-deliverability.md) | [Guía de prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es){target="_blank"}

+++

+++ ¿A qué bases de datos externas puedo conectar Campaign? 

La versión 8 de Campaign admite conexiones de acceso de datos federado (FDA) a los principales sistemas de bases de datos empresariales, lo que le permite aprovechar la infraestructura de datos existente.

**Bases de datos compatibles:**

* **Bases de datos en la nube:** Amazon Redshift, Google BigQuery, Snowflake, Azure Synapse Analytics
* **Bases de datos empresariales:** Oracle, Microsoft SQL Server, PostgreSQL, MySQL
* **Almacenes de datos:** Teradata, Vertica, SAP HANA
* **Datos grandes:** Hadoop a través de Hive

**Consideraciones específicas de la plataforma:** Las versiones de bases de datos compatibles y los requisitos de conexión varían. Campaign v8 as a Managed Cloud Service puede tener requisitos específicos de red y seguridad para el acceso a bases de datos externas.

**Importante:** Compruebe siempre la matriz de compatibilidad oficial de su versión de Campaign v8 para confirmar la compatibilidad con versiones de bases de datos específicas y garantizar las licencias adecuadas para los conectores de bases de datos externas.

[Matriz de compatibilidad](compatibility-matrix.md) | [Configurar conexiones de FDA](../connect/fda.md)

+++

+++ ¿Se puede integrar Adobe Campaign con sistemas CRM?

Sí. Campaign proporciona conectores CRM nativos para una sincronización bidireccional perfecta entre Campaign y su sistema CRM, lo que garantiza datos de clientes coherentes en todas las plataformas.

**Sistemas CRM compatibles:**

* **Salesforce**: posibles clientes, contactos, cuentas, oportunidades y campañas
* **Microsoft Dynamics 365**: contactos, cuentas, posibles clientes, entidades personalizadas
* Otros CRM mediante integraciones de API personalizadas

**Qué sincroniza:**

* **Desde CRM hasta Campaign:** registros de contacto, información de cuenta, posibles clientes, campos personalizados, datos de segmentación
* **De Campaign a CRM:** Registros de envío, datos de seguimiento, métricas de participación, respuestas de campaña, estado de suscripción

**Modos de sincronización:**

* **Programado**: sincronización automática a intervalos definidos (por hora o por día)
* **Manual**: sincronización a petición desencadenada por operadores
* **Tiempo real**: mediante API para actualizaciones inmediatas (desarrollo personalizado)

**Configuración:** Utilice el asistente de conector CRM integrado de Campaign para asignar campos CRM a atributos de Campaign, seleccionar tablas que sincronizar y programar sincronización. El conector gestiona la resolución de conflictos y mantiene la coherencia de los datos.

**Práctica recomendada:** Comience con la sincronización de solo lectura para probar la asignación y, a continuación, habilite la sincronización bidireccional. Supervise los registros de sincronización en busca de errores y mantenga los datos limpios en ambos sistemas.

[Configuración del conector CRM](../connect/crm.md) | [Actividades de CRM de flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html?lang=es){target="_blank"}

+++

+++ ¿Cómo borro la caché de la consola del cliente?

Borrar la caché de la consola del cliente resuelve muchos problemas comunes de visualización y funcionalidad. La caché almacena archivos de configuración local que a veces pueden dañarse o quedar obsoletos.

**Cuándo borrar la caché:**

* Los nuevos elementos de marca (logotipos, colores) no se muestran correctamente
* Error inesperado en las funciones de exportación/importación
* Los elementos de la interfaz no se actualizan después de cambios de configuración
* Problemas de rendimiento o respuesta lenta de la consola
* Después de actualizar a una nueva versión de la consola del cliente

**Pasos para borrar la caché:**

1. Abra la consola del cliente de Campaign
2. Ir al menú **[!UICONTROL File]**
3. Seleccionar **[!UICONTROL Clear the local cache...]**
4. Confirme la acción cuando se le solicite
5. Reinicie la consola del cliente



[Instalación y configuración de la consola de cliente](connect.md)

+++

+++ ¿Puedo configurar los ajustes de la interfaz de usuario?

Sí. Los administradores de Campaign pueden personalizar la interfaz de usuario para que coincida con la marca de la organización y optimizar la experiencia del usuario. Configure las opciones en el nivel de instancia o de usuario.

**Lo que puede personalizar:**

* **Promoción de marca**: logotipo, colores y elementos de identidad visual
* **Vistas predeterminadas**: diseño de la página principal, visibilidad de la estructura de carpetas
* **Configuraciones de lista**: columnas predeterminadas, orden, filtros en listas de datos
* **Navegación**: elementos de menú y métodos abreviados disponibles
* **Configuración regional**: formatos de fecha y hora, formatos de número y zonas horarias
* **Notificaciones**: alertas de correo electrónico, notificaciones en la aplicación y alertas de flujo de trabajo

**Niveles de configuración:**

* **En toda la instancia** - Aplicar a todos los usuarios (requiere derechos de administrador)
* **Específico del usuario**: preferencias individuales y configuración personal
* **Grupo de operadores** - Configuración heredada por todos los miembros del grupo


[Configurar la configuración de la interfaz de usuario](../config/ui-settings.md) | [Permisos de usuario](gs-permissions.md)

+++

+++ ¿Puedo crear campos y tablas personalizados?

Sí. El modelo de datos flexible de Campaign le permite ampliar esquemas integrados con campos personalizados y crear tablas completamente nuevas para satisfacer sus necesidades comerciales específicas.

**Lo que puede personalizar:**

* **Agregar campos a tablas existentes**: amplíe la tabla de destinatarios con puntos de fidelidad, preferencias personalizadas e ID externos
* **Crear nuevas tablas personalizadas**: productos de tienda, transacciones, niveles de fidelidad y entidades personalizadas
* **Definir relaciones**: vincule tablas personalizadas a tablas de Campaign existentes
* **Extender formularios**: actualice la interfaz de usuario para mostrar y editar campos personalizados

**Casos de uso comunes:**

* Almacenar atributos de perfil adicionales (valor de duración del cliente, tienda preferida, estado de VIP)
* Administración de catálogos de productos con atributos personalizados
* Seguimiento de eventos e interacciones personalizados
* Integración de ID de sistema externos para la sincronización de datos
* Creación de modelos de datos específicos del sector (minorista, financiero, viajes)


[Ampliar modelo de datos](../dev/extend-schema.md) | [Estructura del esquema](../dev/schemas.md) | [Prácticas recomendadas del modelo de datos](../dev/datamodel-best-practices.md)

+++

## Creación de informes {#reporting}

Obtenga información sobre las funcionalidades de creación de informes de Campaign, incluidos informes integrados, informes personalizados y herramientas de análisis de datos como cubos.

+++ ¿Cómo se pueden crear nuevos informes?

Campaign ofrece varias opciones de creación de informes en función de sus necesidades y experiencia técnica. Puede utilizar informes integrados, crear informes personalizados en la consola del cliente o diseñar paneles visuales en la interfaz de usuario web de Campaign.

**Opciones de informes:**

* **Informes integrados**: se puede acceder a los informes de envío, campaña y seguimiento listos para usar desde la pestaña **[!UICONTROL Reports]**
* **Análisis descriptivo**: informes estadísticos rápidos sobre cualquier dato con una interfaz dirigida por un asistente
* **Informes personalizados**: informes avanzados creados por usuarios técnicos con el editor de informes
* **Paneles de interfaz de usuario web**: informes visuales y paneles modernos con interfaz de arrastrar y soltar
* **Cubos**: exploración de datos multidimensional y análisis de tabla dinámica

**Importante:** La campaña está diseñada para generar informes de operaciones de marketing, no como una herramienta de inteligencia empresarial especializada. Para necesidades analíticas complejas, considere la posibilidad de integrar con Adobe Analytics o plataformas de BI dedicadas.

[Introducción a los informes](../reporting/gs-reporting.md) | [Informes de IU web de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

+++ ¿Cómo se puede diseñar y compartir informes estadísticos sobre la población?

Utilice la herramienta de análisis descriptivo de Campaign para generar rápidamente informes estadísticos sobre cualquier dato de población. Esta función, dirigida por un asistente, le ayuda a analizar distribuciones, tendencias y patrones sin conocimientos técnicos.

**Lo que puede analizar:**

* Desgloses demográficos y de segmentación de destinatarios
* Métricas de rendimiento de la campaña y tasas de respuesta
* Distribución de atributos de perfil (edad, ubicación, preferencias)
* Estadísticas de envío y patrones de participación
* Valores de campos personalizados y métricas de calidad de datos

**Cómo crear:** Seleccione cualquier resultado de lista o consulta → Haga clic con el botón secundario en el → **[!UICONTROL Actions > Analyze]** → Elija el tipo de análisis (cualitativo o cuantitativo) → Configure las opciones de visualización → Generar informe.

**Uso compartido:** Exporte informes a Excel/PDF o guárdelos en la carpeta **[!UICONTROL Reports]** para que el equipo tenga acceso a ellos con los permisos adecuados.

[Análisis descriptivo](../reporting/built-in-reports.md)

+++

+++ ¿Cómo se puede diseñar informes avanzados con mis datos?

Campaign ofrece dos métodos para crear informes personalizados avanzados: informes técnicos en la consola del cliente para análisis complejos y paneles visuales para facilitar la creación de informes.

En la consola del cliente, puede:

* Creación de informes complejos con consultas SQL y cálculos personalizados
* Creación de informes de varias páginas con gráficos, tablas y tablas dinámicas
* Diseño de formato condicional y contenido dinámico
* Acceso al modelo de datos completo de Campaign y a las bases de datos externas (FDA)


[Crear informes personalizados (consola de cliente)](../reporting/custom-reports.md)

+++

+++ ¿Qué es un cubo y cómo puedo utilizarlo para la creación de informes?

Los cubos son estructuras de datos multidimensionales que permiten a los usuarios empresariales explorar y analizar datos de Campaign a través de tablas dinámicas sin habilidades técnicas. Considérelos como modelos de datos preconfigurados que simplifican los informes complejos.


* Los usuarios técnicos crean y configuran cubos que definen dimensiones (tiempo, geografía, canales) y medidas (aperturas, clics, ingresos)
* Los usuarios empresariales seleccionan un cubo al crear informes y arrastran y sueltan dimensiones para explorar datos
* Los datos se agregan y calculan automáticamente en función de la configuración del cubo
* Los resultados se pueden mostrar como tablas dinámicas, gráficos o exportarse a Excel


[Exploración de datos con cubos](../reporting/gs-cubes.md)

+++

+++ ¿Se puede crear un informe a partir de respuestas a una encuesta en línea?

¡Sí! Campaign incluye un módulo de Encuesta que le permite crear cuestionarios en línea y generar informes integrados sobre las respuestas a las encuestas.

**Importante:** La administración de encuestas no está disponible en las implementaciones de Campaign v8 Enterprise (FDAC). [Más información](../architecture/enterprise-deployment.md).

**Funciones de encuesta:**

* Creación de cuestionarios en línea con varias páginas y tipos de preguntas
* Recopilar respuestas en la base de datos o en las variables locales
* Visualización del seguimiento en tiempo real de las respuestas a la encuesta
* Generar informes específicos sobre las respuestas a las encuestas (desglose por pregunta, estadísticas generales)
* Exportar respuestas de encuestas a Excel, PDF o CSV para un análisis más detallado
* Uso de datos de encuestas en flujos de trabajo de segmentación para personalizar campañas

**Informes de encuesta integrados:**

* **Informe general**: tendencias de respuesta a lo largo del tiempo, distribución por origen e idioma
* **Desglose de respuestas** - Desglose detallado de respuestas para cada pregunta
* **Informe de documentación**: representación visual de la estructura de la encuesta

**Análisis avanzado:**

* Acceder a las respuestas de encuestas desde la ficha **[!UICONTROL Responses]** y exportar datos
* Utilice la actividad **[!UICONTROL Survey responses]** en flujos de trabajo para segmentar destinatarios según sus respuestas
* Combinación de datos de encuestas con otros datos de Campaign para la segmentación y personalización
* Creación de informes y cubos personalizados para análisis de encuestas multidimensional


[Introducción a las encuestas](https://experienceleague.adobe.com/es/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Informes de encuesta](https://experienceleague.adobe.com/es/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ ¿Cómo se puede compartir el acceso a mis informes?

Campaign ofrece opciones flexibles para compartir informes con diferentes grupos de usuarios y controlar la visibilidad y los permisos de acceso en función de las funciones y responsabilidades.

**Control de acceso de informe:**

* **Permisos de carpeta**: coloque informes en carpetas con acceso de lectura y escritura adecuado para grupos de usuarios
* **Derechos asignados**: asigne derechos específicos para ver, crear o modificar informes
* **Contexto de visualización** - Defina dónde aparecen los informes: en **[!UICONTROL Reports]** carpeta, fichas de campaña o pantallas de envío
* **Uso compartido de la interfaz de usuario web** - Compartir vínculos del panel con integrantes del equipo a través de la interfaz de usuario web de Campaign

**Cómo configurar el acceso:**

1. Guarde el informe en una carpeta específica de la consola del cliente
2. Configuración de permisos de acceso a carpetas para grupos de operadores relevantes
3. Definir las propiedades del informe: tipo de informe, contexto de visualización y disponibilidad
4. Pruebe el acceso con un usuario del grupo destinatario antes de un despliegue más amplio

**Práctica recomendada:** Cree carpetas de informes dedicadas para diferentes equipos (marketing, operaciones y administración) con permisos de acceso personalizados. Documentar el propósito del informe y las programaciones de actualización.

[Informes personalizados](../reporting/custom-reports.md) | [Permisos de usuario](gs-permissions.md)

+++

+++ ¿Se pueden exportar informes en diferentes formatos?

Sí, Campaign admite varios formatos de exportación tanto para la consola del cliente como para los informes de la interfaz de usuario web, lo que permite compartir fácilmente con las partes interesadas e integrar con otras herramientas.

**Formatos de exportación disponibles:**

* **Excel (.xlsx)**: idóneo para la manipulación de datos, análisis adicionales y tablas dinámicas
* **PDF**: idóneo para presentaciones, resúmenes ejecutivos e informes impresos
* **CSV**: perfecto para importar datos en otros sistemas y herramientas de BI
* **OpenDocument (.ods)**: formato de hoja de cálculo de código abierto
* **XML**: para integraciones de sistemas y procesamiento automatizado

**Cómo exportar:**

* **Consola de cliente:** Abrir informe → Haga clic en el botón **[!UICONTROL Export]** → Elegir formato → Guardar archivo
* **Interfaz de usuario web:** Abrir panel → Haga clic en el icono de exportación → Seleccionar formato → Descargar
* **Exportaciones automatizadas:** Programar exportaciones regulares mediante flujos de trabajo con actividades de exportación

**Prácticas recomendadas:**

* Utilice Excel para informes que requieran análisis y anotaciones de las partes interesadas
* Utilice PDF para informes estáticos enviados a ejecutivos o archivados para fines de conformidad
* Utilice CSV para integraciones con almacenes de datos o herramientas de análisis externas
* Prueba de informes exportados para garantizar el formato y la precisión de los datos

[Informes personalizados](../reporting/custom-reports.md) | [Informes de IU web de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Desarrolladores {#developers}

Acceda a información técnica para desarrolladores, incluidos detalles del modelo de datos, esquemas, API y funcionalidades de personalización.

+++ ¿Qué es el modelo de datos de Campaign?

El modelo de datos de Campaign es una estructura de base de datos relacional basada en esquemas que define cómo se organizan y relacionan los datos de marketing. Consta de tablas integradas para objetos de marketing principales (destinatarios, envíos, campañas) y se puede ampliar para satisfacer sus necesidades comerciales específicas.

**Conceptos clave del modelo de datos:**

* **Esquemas**: definiciones XML que describen la estructura de tabla, los campos y las relaciones
* **Tablas integradas**: entidades de marketing principales (destinatarios, envíos, flujos de trabajo, campañas)
* **Vínculos** - Relaciones entre tablas (1-1, 1-N, N-N)
* **Enumeraciones**: listas de valores predefinidas para campos desplegables
* **Extensiones**: campos personalizados y tablas agregadas al modelo estándar

**Esquemas integrados principales:**

* **Destinatario (nms:recipient)** - Perfiles de cliente e información de contacto
* **Envío (nms:delivery)**: correo electrónico, SMS y campañas push
* **Flujo de trabajo (xtk:workflow)** - Procesos de automatización
* **Campaña (nms:operation)** - Organización de la campaña de marketing
* **Registros de seguimiento**: aperturas, clics y datos de participación

**Por qué es importante:** Es esencial comprender el modelo de datos para crear flujos de trabajo, crear consultas, ampliar esquemas y desarrollar integraciones personalizadas. El enfoque basado en esquemas garantiza la coherencia de los datos y habilita potentes capacidades de consulta.

[Modelo de datos de Campaign](../dev/datamodel.md) | [Prácticas recomendadas del modelo de datos](../dev/datamodel-best-practices.md)

+++

+++ ¿Cómo se trabaja con los esquemas de Campaign?

Los esquemas son la base de la estructura de datos de Campaign y definen tablas, campos y relaciones en formato XML. Comprender los esquemas es crucial para la personalización, la integración y el desarrollo avanzado del flujo de trabajo.

**Qué definen los esquemas:**

* **Estructura de tabla**: tablas de base de datos y sus objetos de aplicación correspondientes
* **Propiedades del campo**: tipos de datos, etiquetas, reglas de validación y valores predeterminados
* **Relaciones** - Vínculos entre tablas (uniones) y cardinalidad
* **Índices**: optimización de la base de datos para el rendimiento de consultas
* **Control de acceso**: qué campos pueden ver y modificar los usuarios

**Trabajando con esquemas:**

* **Ver esquemas:** Acceso a través de **[!UICONTROL Administration > Configuration > Data schemas]** en la consola de cliente
* **Ampliar esquemas:** Crear esquemas de extensión (por ejemplo, `cus:recipient` amplía `nms:recipient`) para agregar campos personalizados sin modificar los esquemas principales
* **Crear esquemas personalizados:** Crear tablas completamente nuevas para datos específicos de la empresa
* **Actualizar base de datos:** Aplicar cambios de esquema usando **[!UICONTROL Tools > Advanced > Update database structure]**

**Casos de uso comunes:**

* Adición de campos personalizados a la tabla de destinatarios (ID de empresa, nivel de fidelidad, preferencias)
* Crear tablas personalizadas para productos, tiendas o transacciones
* Definición de relaciones entre tablas personalizadas y tablas integradas
* Implementación de modelos de datos específicos para la empresa

**Importante:** Nunca modifique directamente los esquemas integrados. Utilice siempre esquemas de extensión para conservar la compatibilidad de actualización y Adobe.

[Introducción a los esquemas](../dev/schemas.md) | [Ampliar un esquema](../dev/extend-schema.md)

+++

+++ ¿Cómo se utiliza una tabla de destinatarios personalizada?

Campaign le permite utilizar una tabla personalizada en lugar de la tabla de destinatarios integrada cuando su empresa requiera una estructura de datos diferente para la segmentación (por ejemplo, cuentas B2B, suscriptores, posibles clientes o contactos externos).

**Por qué usar una tabla de destinatarios personalizada:**

* Empresas o unidades organizativas B2B objetivo en lugar de contactos individuales
* Separar datos de suscriptores de la base de datos principal de clientes
* Usar una tabla de cliente existente de otro sistema
* Implementar arquitecturas de varias marcas con tablas de contacto independientes
* Cumplir con los requisitos específicos de gobernanza de datos

**Pasos de implementación:**

1. Cree el esquema personalizado que defina la estructura de la tabla de destinatarios
2. Incluir campos obligatorios (correo electrónico, clave principal, indicadores de exclusión)
3. Configure asignaciones de destino para vincular la tabla con las entregas
4. Actualizar plantillas de envío para utilizar la nueva asignación de destino
5. Adaptar flujos de trabajo y consultas para hacer referencia a la tabla personalizada

**Consideraciones clave:**

* Las tablas de destinatarios personalizadas deben incluir los campos obligatorios para las entregas (correo electrónico, exclusiones, seguimiento)
* Los flujos de trabajo y los formularios deben adaptarse para trabajar con la estructura personalizada
* Algunas funciones integradas pueden requerir personalización
* Las pruebas son esenciales antes de migrar campañas de producción

**Práctica recomendada:** Empiece ampliando la tabla de destinatarios estándar antes de considerar una tabla personalizada. Las tablas de destinatarios personalizadas añaden complejidad y solo deben utilizarse cuando sea verdaderamente necesario.

[Tabla de destinatarios personalizada](../dev/custom-recipient.md) | [Asignaciones de destino](../audiences/target-mappings.md)

+++

+++ ¿Cuáles son las mejores prácticas para definir las consultas en Campaign? 

El editor de consultas de Campaign es una potente herramienta visual para crear consultas de base de datos sin conocimientos de SQL. Dominarlo es esencial para un direccionamiento, una segmentación y un análisis de datos eficaces.

**Donde se usan las consultas:**

* **Actividades de flujo de trabajo**: consultar, dividir, actualizar datos, actividades de enriquecimiento
* **Direccionamiento de entrega**: defina las poblaciones de destinatarios para las campañas
* **Listas** - Crear listas de destinatarios dinámicas o estáticas
* **Informes** - Generar análisis y extracciones de datos personalizados
* **Filtros** - Crear criterios de direccionamiento reutilizables

**Prácticas recomendadas de consulta:**

* **Iniciar simple**: genere consultas de forma incremental y realice pruebas en cada paso
* **Usar dimensiones de filtrado**: aproveche las relaciones entre tablas (destinatarios → envíos → registros de seguimiento)
* **Optimizar el rendimiento**: indexe los campos consultados con frecuencia para evitar campos calculados complejos.
* **Aprovechar filtros predefinidos**: reutilice y combine filtros existentes para mantener la coherencia
* **Prueba con ejemplos pequeños**: valide la lógica de consulta antes de ejecutarla en la base de datos completa
* **Documentar consultas complejas**: agregue descripciones para el mantenimiento y la transferencia de conocimientos

**Patrones de consulta comunes:**

* Destinatarios objetivo que abrieron un envío específico: Filtre por los registros de seguimiento vinculados a los destinatarios
* Buscar contactos inactivos: Consulta de la última fecha de envío o actividad de seguimiento
* Segmentar por comportamiento: combinar entrega, seguimiento y criterios de perfil
* Excluir destinatarios anteriores: utilizar operaciones de conjunto (unión, intersección, exclusión)

**Acceder al editor de consultas genérico:** **[!UICONTROL Tools > Generic query editor]** para la exploración de bases de datos ad hoc y la extracción de datos fuera de los flujos de trabajo.

[Editor de consultas](../start/query-editor.md) | [Actividad de consulta en flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=es){target="_blank"}

+++

+++ ¿Cómo puedo importar un paquete de datos? 

Los paquetes de datos permiten exportar e importar configuraciones de Campaign (esquemas, flujos de trabajo, tipologías, filtros) y datos entre instancias. Esto es esencial para implementar configuraciones desde el desarrollo hasta la producción o compartir componentes entre organizaciones.

**Qué se puede empaquetar:**

* **Objetos de configuración**: esquemas, flujos de trabajo, reglas de tipología, formularios, filtros
* **Componentes de Campaign**: plantillas de envío, plantillas de campaña y bloques de contenido
* **Configuración de la aplicación** - Operadores, grupos de operadores, estructuras de carpetas
* **Datos**: listas de destinatarios, direcciones semilla, fragmentos de contenido
* **Desarrollos personalizados**: código JavaScript, scripts SQL y aplicaciones web


**Tipos de paquetes:**

* **Paquete de usuario**: configuraciones personalizadas que crea y exporta
* **Paquete de plataforma**: características y actualizaciones proporcionadas por Adobe
* **Paquete de datos**: contiene registros de datos reales, no solo una estructura

**Prácticas recomendadas:**

* Exporte siempre paquetes de la misma versión de Campaign o de una anterior
* Probar las importaciones de paquetes en el entorno de desarrollo antes de la producción
* Documentar el contenido y las dependencias del paquete
* Utilizar el control de versiones para los archivos XML del paquete
* Copia de seguridad de la instancia antes de importaciones de paquetes principales

[Trabajo con paquetes de datos](../dev/packages.md)

+++

+++ ¿Dónde puedo encontrar la lista de las API de Campaign v8?

La versión 8 de Campaign proporciona documentación de API completa que cubre tanto las API de SOAP (para interacciones con la consola del cliente) como las API de REST (para integraciones modernas). La referencia de la API incluye todos los métodos, parámetros y formatos de respuesta disponibles.

**Tipos de API de Campaign:**

* **API de SOAP**: API tradicionales para operaciones de la consola del cliente de Campaign, manipulación de esquemas y control de flujo de trabajo
* **API de REST**: API de HTTP modernas para integraciones de sistemas externos, administración de perfiles y activación de eventos
* **API de JavaScript**: API de scripts del lado del servidor para actividades de flujo de trabajo y lógica empresarial personalizada

**Recursos de documentación de API:**

* **Referencia de API completa:** Documentación completa de la API de SOAP con firmas de métodos, parámetros y ejemplos
* **Guía de API de REST:** Extremos REST modernos para perfiles, eventos y unidades organizativas
* **API de JavaScript:** Funciones del lado del servidor disponibles en scripts de flujo de trabajo y aplicaciones web

**Casos de uso comunes de API:**

* Integración de Campaign con CRM, ERP o aplicaciones personalizadas
* Automatización de operaciones de campaña y ejecución de flujo de trabajo
* Sincronización de datos entre sistemas en tiempo real
* Creación de soluciones personalizadas de monitorización y alertas
* Creación de interfaces externas para datos y operaciones de Campaign

**Acceso:** [Documentación de la API de Campaign v8](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=es){target="_blank"}

+++


+++ ¿Cómo superviso los flujos de trabajo desde la API?

Las API de Campaign permiten controlar y monitorizar mediante programación la ejecución del flujo de trabajo, lo que permite sistemas de monitorización externos, alertas automatizadas y soluciones de orquestación personalizadas.

**Lo que puede hacer a través de la API:**

* **Iniciar flujos de trabajo**: ejecución del flujo de trabajo de Déclencheur mediante programación
* **Pausar/Reanudar flujos de trabajo** - Controlar el flujo de ejecución del flujo de trabajo
* **Detener flujos de trabajo** - Finalizar flujos de trabajo en ejecución
* **Estado del flujo de trabajo de consulta**: compruebe si los flujos de trabajo se están ejecutando, están en pausa o están completados
* **Recuperar registros** - Acceder a los registros de ejecución del flujo de trabajo y mensajes de error
* **Monitorizar progreso de la actividad** - Rastrear finalización de actividad de flujo de trabajo individual

**Métodos API:**

* `xtk:workflow#Start` - Iniciar una instancia de flujo de trabajo
* `xtk:workflow#Pause` - Pausar flujo de trabajo en ejecución
* `xtk:workflow#Stop` - Detener la ejecución del flujo de trabajo
* `xtk:workflow#GetState` - Obtener estado actual del flujo de trabajo
* `xtk:workflow#GetLogs` - Recuperar registros de ejecución

**Casos de uso comunes:**

* Creación de paneles de monitorización personalizados que muestren el estado del flujo de trabajo
* Implementar alertas automatizadas cuando los flujos de trabajo fallan o se ejecutan demasiado tiempo
* Organización de flujos de trabajo desde programadores externos o sistemas de eventos
* Crear dependencias de flujo de trabajo en varias instancias de Campaign
* Generar informes de ejecución de flujo de trabajo personalizados

**Práctica recomendada:** Combine la supervisión de la API con el seguimiento de auditoría del flujo de trabajo para un control exhaustivo del flujo de trabajo. Utilice herramientas de monitorización externas para rastrear los SLA y las métricas de rendimiento del flujo de trabajo.

[Control de flujos de trabajo mediante API](../dev/api/controlling-a-workflow.md)

+++

+++ ¿Cómo se puede actualizar la estructura de la base de datos?

Después de modificar los esquemas de Campaign (adición de campos, creación de tablas, cambio de tipos de datos), debe actualizar la estructura física de la base de datos para aplicar los cambios. Esta sincronización garantiza que la base de datos coincida con las definiciones de esquema.

**Cuando se necesitan actualizaciones de la base de datos:**

* Adición de nuevos campos a esquemas existentes
* Creación de tablas personalizadas o ampliación de tablas integradas
* Modificación de las propiedades del campo (tipo de datos, longitud, estado requerido)
* Adición o eliminación de vínculos entre tablas
* Creación de nuevos índices para la optimización de consultas


**Consideraciones importantes:**

* **Copia de seguridad primero**: realiza siempre una copia de seguridad de la base de datos antes de realizar cambios estructurales
* **Prueba en desarrollo**: valide los cambios de esquema en el entorno de desarrollo antes de la producción
* **Planificación del tiempo de inactividad**: los cambios estructurales grandes pueden requerir breves períodos de mantenimiento
* **Para Cloud Services administrados**: coordine los cambios más importantes con la asistencia de Adobe
* **Reversibilidad**: algunos cambios (como eliminar campos) pueden causar pérdida de datos

**Práctica recomendada:** Usar el control de versiones y el seguimiento de cambios del esquema. Documente todas las modificaciones de esquema personalizadas para el mantenimiento y la resolución de problemas.

[Actualizar estructura de base de datos](../dev/update-database-structure.md) | [Ampliar esquema](../dev/extend-schema.md)

+++

+++ ¿Cuáles son las limitaciones de Campaign v8?

La versión 8 de Campaign introduce cambios de arquitectura (especialmente en implementaciones de FDAC) que aportan mejoras de rendimiento significativas, pero también algunas diferencias con respecto a la versión 7 de Campaign Classic. Comprender estos factores ayuda a planificar las migraciones y a establecer las expectativas adecuadas.

**Consideraciones principales de la versión 8:**

* **Arquitectura de FDAC**: las implementaciones empresariales utilizan la base de datos en la nube (Snowflake) con diferentes patrones de acceso a datos
* **Actualizaciones de unidades**: las actualizaciones de datos deben realizarse en flujos de trabajo, no a través de API o acceso directo a bases de datos
* **Escrituras en tiempo real**: optimizadas para operaciones por lotes en lugar de actualizaciones individuales de alta frecuencia
* **Modelo de datos**: algunas personalizaciones de esquema requieren enfoques diferentes
* **Acceso a base de datos externa** - La configuración de FDA (Acceso de datos federado) difiere de la versión 7

**Características no disponibles en implementaciones de FDAC:**

* Encuestas (disponibles en implementaciones estándar de la versión 8)
* Administración de recursos de marketing (MRM)
* Algunas configuraciones específicas del conector

**Consideraciones de migración:**

* Es necesario refactorizar el código personalizado que utiliza escrituras directas de base de datos
* Las integraciones de API pueden requerir una adaptación para el procesamiento por lotes
* Los flujos de trabajo deben seguir las prácticas recomendadas de FDAC para operaciones de datos
* Las pruebas son esenciales para validar los desarrollos personalizados

**Importante:** Estas limitaciones están evolucionando a medida que Adobe continúa mejorando la versión 8. Consulte la documentación más reciente sobre el estado actual y la hoja de ruta.

[Migración de Campaign v7 a v8](../start/v7-to-v8.md#limitations) | [Arquitectura de FDAC](../architecture/enterprise-deployment.md)

+++

## Privacidad {#privacy}

Comprenda cómo Adobe Campaign le ayuda a cumplir con las regulaciones de privacidad, como el RGPD y la CCPA, y a administrar las solicitudes de los interesados.

+++ ¿Cuáles son los conceptos clave de privacidad en Campaign?

Campaign le ayuda a cumplir con las regulaciones de privacidad (RGPD, CCPA, PDPA, LGPD) a través de herramientas para administrar los derechos de los interesados, el consentimiento y la retención de datos. Los conceptos clave incluyen regulaciones de privacidad, identificación de datos personales, derechos de los interesados (acceso, eliminación, portabilidad), administración de consentimiento y políticas de retención de datos.

Como controlador de datos, es responsable de administrar las solicitudes de los sujetos de datos, mantener los registros de consentimiento y garantizar un uso transparente de los datos.

[Administración de la privacidad](../start/privacy.md)

+++

+++ ¿Cómo puedo garantizar el cumplimiento de la privacidad en Campaign?

Campaign proporciona herramientas para el cumplimiento de la privacidad, pero usted es el responsable legal. Trabaje con un asesor legal para su programa de privacidad.

**Acciones esenciales:**

* Establezca procesos para administrar las solicitudes de los interesados (acceso, eliminación)
* Implementación de la administración de consentimiento con marcas de tiempo y seguimiento de ámbito
* Incluir vínculos de cancelación de suscripción en todos los correos electrónicos de marketing
* Auditoría de fuentes de datos y eliminación de datos no utilizados
* Aplicar controles de acceso con menos privilegios

Campaign ofrece integración del Servicio principal de privacidad, seguimiento del consentimiento, flujos de trabajo de eliminación automatizados y pistas de auditoría para el cumplimiento.

[Administración de la privacidad](../start/privacy.md)

+++

+++ ¿Cómo se debe recopilar y administrar el consentimiento del usuario?

Un consentimiento válido requiere un acuerdo activo, específico, informado y revocable. Los usuarios deben realizar acciones explícitas (sin casillas premarcadas ni silencio como consentimiento). Separe los consentimientos para diferentes fines (no agrupados), proporcione explicaciones claras y mantenga registros con marcas de tiempo.

**Prácticas recomendadas:** Proporcione opciones de inclusión granulares, actualice periódicamente el consentimiento, facilite el acceso a los centros de preferencias y convierta el consentimiento en marco para generar confianza.

Campaign ofrece servicios de suscripción, centros de preferencias, campos de consentimiento personalizados con seguimiento de marca de tiempo y actualización de consentimiento basada en flujo de trabajo.

[Suscripciones](../start/subscriptions.md) | [Privacidad y consentimiento](../start/privacy.md#consent-retention-roles)

+++

+++ ¿Cómo implemento la administración de consentimiento en Campaign?

Campaign proporciona servicios de suscripción, centros de preferencias, indicadores de exclusión y campos de consentimiento personalizados para el seguimiento del consentimiento.

**Método de implementación:** amplíe el esquema de destinatarios para los campos de consentimiento (fecha, tipo, origen), cree servicios de suscripción para cada tipo de consentimiento, cree formularios web del centro de preferencias, utilice flujos de trabajo para aplicar el consentimiento en el direccionamiento y mantenga los seguimientos de auditoría.

Consulte con un asesor legal para asegurarse de que su implementación cumple con los requisitos regulatorios.

[Servicios de suscripción](../start/subscriptions.md) | [Administración de privacidad](../start/privacy.md)

+++

+++ ¿Qué datos se eliminan al procesar una solicitud de eliminación?

Campaign elimina automáticamente todos los datos vinculados a un interesado: perfil de destinatario, registros de envío y seguimiento, datos personalizados con relaciones de propiedad, historial de suscripciones y datos de seguimiento web.

**Cómo funciona:** Campaign elimina todos los datos donde el vínculo al destinatario tiene `integrity="own"` en la definición del esquema, lo que garantiza la eliminación en cascada en las tablas relacionadas.

Puede personalizar el ámbito de eliminación modificando la integridad del vínculo en los esquemas, pero primero consulte con un asesor jurídico. La eliminación es permanente y no se puede deshacer.

[Administración de privacidad](../start/privacy.md) | [Vínculos de esquema](../dev/schemas.md)

+++

+++ ¿Las eliminaciones de privacidad afectan a mis informes de envío?

No. Los informes de campaña se basan en métricas agregadas precalculadas (total enviado, aperturas, clics), no en consultas activas de registros individuales. La eliminación de datos de destinatarios individuales no cambia las estadísticas agregadas históricas.

Las estadísticas de envío generales y las métricas de rendimiento permanecen intactas, mientras que los registros de seguimiento individuales y los detalles personales se eliminan. Esto le permite mantener los análisis de marketing respetando los derechos de los interesados.

[Administración de privacidad](../start/privacy.md) | [Informes](../reporting/gs-reporting.md)

+++

+++ ¿Cómo evito volver a importar los datos eliminados?

Debe eliminar los datos de todos los sistemas de origen, no solo de Campaign. Los datos suelen proceder de sistemas externos (CRM, comercio electrónico, almacenes de datos).

**Acciones necesarias:** Identifique todas las fuentes de datos, elimine de los sistemas de origen, agregue a listas de exclusión/supresión, actualice los flujos de trabajo de importación para respetar los indicadores de eliminación y documente el proceso.

Como controlador de datos, es responsable de la eliminación completa de datos en todo el ecosistema tecnológico.

[Administración de privacidad](../start/privacy.md) | [Importar flujos de trabajo](../config/workflows.md)

+++

+++ ¿Pueden los usuarios eliminados adherirse de nuevo?

Sí. Los interesados pueden volver a incluirse tras la eliminación. Campaign crea un registro de destinatario completamente nuevo sin vínculo a los datos eliminados anteriormente; el perfil comienza con una pizarra limpia.

La pista de auditoría de Campaign registra tanto el evento de eliminación como la nueva creación de perfiles, lo que demuestra que se cumple y que se muestra que la nueva opción de inclusión se proporcionó libremente después de la eliminación.

[Administración de privacidad](../start/privacy.md) | [Suscripciones](../start/subscriptions.md)

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
* **[Versiones y actualizaciones](upgrades.md)**: Obtenga información sobre las versiones de Campaign, las actualizaciones y cómo comprobar su versión
* **[Prácticas recomendadas](delivery-best-practices.md)** - Enfoques recomendados para tareas comunes

### Recursos técnicos

Encuentre documentación técnica detallada y recursos para desarrolladores.

* **[API de Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=es){target="_blank"}**: documentación de referencia de API completa
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.es-ES)**: Contribuya a la documentación
* **[Notas técnicas](https://experienceleague.adobe.com/es/docs/campaign/technotes-ac/technotes-home){target="_blank"}**: artículos técnicos detallados
* **[Matriz de compatibilidad](compatibility-matrix.md)** - Sistemas y versiones compatibles
* **[Preguntas frecuentes sobre versiones y actualizaciones](upgrades.md#upgrades-faq)**: comprueba tu versión y obtén información sobre las actualizaciones

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
* **[Rutas de aprendizaje de Experience League](https://experienceleague.adobe.com/es?lang=es#dashboard/learning){target="_blank"}** - recorridos de aprendizaje guiados

### Otros recursos útiles

* **[Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=es){target="_blank"}** - Referencia para usuarios de Classic v7
* **[Documentación de la interfaz de usuario web de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Nueva guía de la interfaz web
* **[Prácticas recomendadas de envío](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es){target="_blank"}** - Optimizar envío de correo electrónico
* **[Actualizaciones de productos](https://experienceleague.adobe.com/es/docs/release-notes/experience-cloud/current){target="_blank"}**: últimas actualizaciones de Adobe Experience Cloud

**Última actualización:** noviembre de 2025 | **Se aplica a:** Campaign v8.6 y versiones posteriores

*¿Encontró un error o desea sugerir una mejora? [Editar esta página en GitHub](https://github.com/AdobeDocs/campaign.es-ES/edit/main/help/v8/start/campaign-faq-comprehensive.md)*

