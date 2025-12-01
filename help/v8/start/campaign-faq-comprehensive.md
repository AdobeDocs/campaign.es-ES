---
title: Preguntas más frecuentes sobre la versión 8 de Campaign
description: Obtenga respuestas a preguntas comunes de la versión 8 de Adobe Campaign sobre configuración, mensajería, flujos de trabajo y mucho más
feature: Overview
role: User
level: Beginner
keywords: Preguntas más frecuentes, Campaign v8, preguntas, respuestas, ayuda, asistencia, solución de problemas
version: Campaign v8
hide: true
hidefromtoc: true
source-git-commit: abbbe4c59847a64142cc80704c1a77348a7c35ff
workflow-type: tm+mt
source-wordcount: '9819'
ht-degree: 12%

---

# Preguntas frecuentes {#faq}

Obtenga respuestas rápidas a las preguntas más comunes sobre Adobe Campaign v8. Tanto si acaba de empezar como si busca ayuda para la configuración avanzada, encontrará respuestas organizadas por temas a continuación.

**¿Es nuevo en Campaign?** comienza con [Preguntas generales](#general) y [Conceptos clave](#key-concepts).\
**¿Necesita ayuda con las versiones?** Comprueba [Actualizaciones](#upgrades) para obtener información sobre la versión y los procesos de actualización.\
**¿Está migrando desde la versión 7 o estándar?** Consulte [Campaign v8 frente a versiones anteriores](#v7-differences) para ver las diferencias y las directrices de transición.\
**¿Necesita ayuda técnica?**: comprobar [desarrolladores](#developers) y [configuración de la campaña](#settings).\
**¿No encuentra la respuesta?** Visite nuestros [Foros de la comunidad](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} o [comuníquese con la atención al cliente](#get-help).

**Sugerencia:** Utilice Ctrl+F (Cmd+F en Mac) para buscar palabras clave específicas en esta página. Haga clic en cualquier pregunta para ampliar la respuesta.


## Preguntas generales {#general}

Obtenga respuestas a las preguntas más comunes sobre Adobe Campaign v8, como cómo conectarse, empezar y acceder a la asistencia.

+++ ¿Cómo puedo conectarme a Campaign v8?

Debe descargar e instalar la consola del cliente de Campaign para conectarse a Adobe Campaign. [Más información](connect.md).

A partir de la versión 8.6 de Campaign, tiene acceso a la **interfaz de usuario web de Campaign**, disponible a través del entorno central de Adobe Experience Cloud. Experience Cloud es la familia integrada de aplicaciones, productos y servicios de marketing digital de Adobe.

Obtenga información sobre cómo conectarse a Adobe Experience Cloud y obtener acceso a la interfaz web de Adobe Campaign [en esta página](campaign-ui.md#ac-web-ui). Obtenga más información en la [documentación de la interfaz de usuario web de Adobe Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Temas relacionados:**

[Instalar la consola de cliente](connect.md) | [Interfaz de usuario de Campaign](campaign-ui.md) | [Permisos de usuario](gs-permissions.md)

+++

+++ ¿Cómo configurar el envío del correo electrónico?

La capacidad de envío de correo electrónico, un componente esencial para el éxito del programa de marketing de cada remitente, se caracteriza por criterios y reglas que cambian constantemente. La navegación eficaz en este mundo digital requiere un ajuste regular de su estrategia de correo electrónico, teniendo en cuenta las tendencias clave de envío, para llegar mejor a su público.

Consulte esta guía para obtener más información [Prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es){target="_blank"}

Aprenda a implementar la entregabilidad en Campaign [con esta guía](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=es){target="_blank"}

**Temas relacionados:**

[Introducción a las entregas](../send/about-deliverability.md) | [Control del contenido del mensaje](../send/control-message-content.md) | [Supervisar la capacidad de entrega](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ ¿Cómo puedo asegurarme de que mi entrega se envíe sin errores?

**Antes de enviar:** Ejecute el análisis de envío, envíe pruebas de prueba, revise advertencias y compruebe el recuento de destinatarios.

**Durante/después del envío:** Controle el panel de envío (enviado, entregado, rechazos, errores), compruebe los registros de envío, rastree las tasas de éxito/rechazo y revise las direcciones en cuarentena.

**Prácticas recomendadas:** Configurar alertas, usar olas para grandes volúmenes, probar primero con volúmenes pequeños, limpiar la base de datos de destinatarios con regularidad y supervisar la reputación del remitente.

[Supervisar envíos](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es){target="_blank"} | [Prácticas recomendadas de envío](delivery-best-practices.md)

+++

+++ ¿Se puede monitorizar la ejecución del flujo de trabajo?

Sí. Campaign proporciona varias herramientas de monitorización: panel de flujo de trabajo (estado y errores en tiempo real), registros de flujo de trabajo (registros de ejecución detallados), mapa de calor (visualización de actividad y cuellos de botella), pista de auditoría (seguimiento de modificaciones) y alertas (notificaciones de errores).

Para supervisar, abra el flujo de trabajo y haga clic en la ficha **Registros**. Las actividades fallidas aparecen en rojo.

[Supervisar la ejecución del flujo de trabajo](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} | [Prácticas recomendadas de flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=es){target="_blank"}

+++

+++ ¿Cómo puedo descargar Campaign?

Puede obtener el programa de instalación y la consola del cliente desde el Centro de descargas de Adobe.

Como usuario administrador, acceda a Adobe [Distribución de software](https://experience.adobe.com/#/downloads/content/software-distribution/es/campaign.html){target="_blank"} para descargar Adobe Campaign.

Obtenga más información acerca del Centro de distribución [en esta página](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=es){target="_blank"}.

+++

+++ ¿Cuál es el procedimiento para la delegación de dominios?

Un subdominio es una división de su dominio que puede utilizarse para aislar sus marcas o varios tipos de tráfico (mensajes transaccionales, información de marketing, etc.).

>[!NOTE]
>
>Como usuario de Managed Cloud Services, póngase en contacto con Adobe para delegar sus subdominios a Adobe.

+++

+++ ¿Cómo puedo registrar un problema?

Para ponerse en contacto con Atención al cliente de Adobe, conéctese a [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"} para crear un caso o iniciar una sesión de chat.

Requiere cuentas individuales con los permisos correctos. Si no puede iniciar sesión, solicite acceso a través de Experience League. [Más información](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

También puede unirse a [Campaign Community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} para buscar respuestas o preguntar a expertos.

+++

+++ ¿Con qué sistemas y componentes es compatible Campaign v8?

Puede obtener la lista de todos los sistemas y componentes compatibles con la última versión de Campaign en [la matriz de compatibilidad de Adobe Campaign](compatibility-matrix.md).

+++

+++ ¿Puedo utilizar la versión 8 de Campaign con otras soluciones de Adobe?

Sí. La versión 8 de Campaign se integra perfectamente con las soluciones de Adobe Experience Cloud para lograr un ecosistema de marketing unificado.

**Integraciones clave:** Adobe Experience Platform (perfiles unificados, datos en tiempo real), Adobe Analytics (medición de rendimiento), Adobe Target (personalización), Adobe Experience Manager (administración de contenido), Adobe Audience Manager (segmentos de audiencia).

**Configuración:** Requiere autenticación IMS de Adobe, configurada automáticamente para Managed Cloud Services de Campaign v8.

[integraciones de Adobe Campaign](../connect/integration.md) | [Conectar con Adobe ID](connect.md)

+++

+++ ¿Cuáles son las limitaciones de Campaign v8?

La versión 8 de Campaign ofrece mejoras significativas del rendimiento, pero tiene algunas diferencias de arquitectura con respecto a la versión 7 de Campaign Classic, especialmente en implementaciones de FDAC.

**Consideraciones clave:**

* **Arquitectura de FDAC** - Utiliza la base de datos en la nube (Snowflake) con diferentes patrones de acceso a datos
* **Actualizaciones de datos**: deben realizarse en flujos de trabajo, no a través del acceso directo a la base de datos
* **Optimizado para lotes**: optimizado para operaciones por lotes en lugar de actualizaciones individuales de alta frecuencia
* **No disponible en FDAC** - Encuestas, Administración de recursos de marketing (MRM), algunos conectores específicos

**Impacto de la migración:** Es necesario refactorizar el código personalizado que utiliza escrituras directas de base de datos; es posible que las integraciones de API necesiten adaptación para el procesamiento por lotes.

Estas limitaciones evolucionan a medida que Adobe mejora la versión 8 de. Consulte la documentación más reciente sobre el estado actual.

[Migración de Campaign v7 a v8](../start/v7-to-v8.md#limitations) | [Arquitectura de FDAC](../architecture/enterprise-deployment.md)

+++

+++ Como usuario de Campaign Classic v7, ¿puedo migrar a Campaign v8?

La migración automatizada desde el entorno de la versión 7 de Campaign Classic existente aún no está disponible.

La versión 8 de Campaign **solo** está disponible as a Managed Cloud Service y no se puede implementar en entornos locales o híbridos.

Para obtener más información sobre el proceso de migración, póngase en contacto con su representante de Adobe.

Obtenga más información en la sección [Campaign v8 frente a versiones anteriores](#v7-differences).

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

+++ ¿Cómo puedo configurar los permisos de usuario?

Como administrador de Campaign, puede configurar permisos para usuarios de su organización.

Se trata de un conjunto de derechos y restricciones que autorizan o deniegan:

* Acceso a determinadas funcionalidades
* Acceder a determinados datos
* Creación, modificación o eliminación de datos

[Más información](../start/gs-permissions.md) acerca de los permisos de usuario en la versión 8 de Campaign.

**Temas relacionados:**

[Introducción a los permisos](gs-permissions.md) | [Administrar permisos de usuario](manage-permissions.md) | [Agregar permisos en carpetas](folder-permissions.md)

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

[Introducción a los flujos de trabajo](../config/workflows.md) | [Cree su primer flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=es){target="_blank"} | [Casos de uso del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Supervisar la ejecución del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=es){target="_blank"}

+++

+++ ¿Cómo se crea y se envía un primer correo electrónico?

**5 pasos clave:**

1. Crear envío a partir de plantilla
2. Definición de audiencias (consultas, listas o flujos de trabajo)
3. Diseño de contenido con personalización
4. Envío de pruebas de prueba para validar
5. Ejecutar análisis y enviar

La versión 8 de Campaign ofrece dos interfaces: **Consola de cliente** (con todas las funciones) y **IU web de Campaign** (moderna e intuitiva).

[Diseño y validación de correo electrónico](../send/email.md) | [Crear primer envío](create-message.md) | [Plantillas de envío](../send/create-templates.md) | [Personalizar contenido](../send/personalize.md)

+++

+++ ¿Cómo se envían mensajes SMS?

El envío de SMS requiere una configuración inicial (configurar el canal SMS, la conexión SMPP, el enrutamiento) y la creación de envíos estándar.

**Proceso básico:**

1. Configuración del canal de SMS y la conexión del proveedor (configuración única)
2. Creación de envíos SMS a partir de plantillas
3. Definir destinatarios y escribir contenido (estándar de 160 caracteres, concatenación automática durante más tiempo)
4. Añadir personalización y enviar pruebas de prueba
5. Analizar y enviar

**Funcionalidades:** Múltiples conectores SMPP, seguimiento de envíos, compatibilidad con GSM7/Unicode, autoconcatenación de SMS largos, SMS bidireccional con flujos de trabajo.

[Más información sobre la configuración y el envío de SMS](../send/sms/sms.md) | [Configuración de envío de SMS](../send/sms/sms-delivery-settings.md) | [Crear envío de SMS](../send/sms/create-sms.md)

+++

+++ ¿Cómo se envían notificaciones push?

El envío de notificaciones push requiere la configuración inicial de la integración de la aplicación móvil y, a continuación, la creación de envíos estándar.

**Proceso básico:**

1. **Configuración inicial** (única): configure el canal push, integre Campaign SDK o Recopilación de datos, registre aplicaciones de iOS/Android y configure certificados APNS/FCM
2. **Crear envío**: cree una notificación push desde una plantilla, seleccione una plataforma, defina una audiencia y diseñe una notificación con medios enriquecidos
3. **Probar y enviar**: valide en dispositivos reales y envíe

**Capacidades:** Inserción enriquecida (imágenes, vídeos, botones), personalización, vinculación profunda, programación, pruebas A/B, seguimiento. Funciones específicas de la plataforma para iOS y Android.

[Más información sobre las notificaciones push](../send/push.md) | [Configurar canal push](../send/push-settings.md) | [Inserción enriquecida de Android](../send/rich-push-android.md) | [Inserción enriquecida de iOS](../send/rich-push-ios.md)

+++

+++ ¿Cómo se crea la página de destino?

Puede utilizar el editor de contenido digital de Adobe Campaign para diseñar páginas de aterrizaje y definir la asignación con campos de base de datos.

[Obtenga más información](../dev/landing-pages.md) en la documentación de Campaign v8.

También puede usar la interfaz de usuario de Campaign Web para crear y publicar páginas de aterrizaje: [Más información](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ ¿Cómo puedo hacer un seguimiento de las entregas?

Puede hacer un seguimiento de las entregas realizadas con Campaign v8 a través de [informes de entregas](../reporting/delivery-reports.md) dedicados y luego monitorizarlos.

Obtenga más información acerca de la administración de seguimiento en Campaign [en esta página](../start/tracking.md).

**Temas relacionados:**

[Mensajes de seguimiento y supervisión](tracking.md) | [Informes de envío](../reporting/delivery-reports.md) | [Comprender los errores de entrega](../send/delivery-failures.md) | [Configurar vínculos rastreados](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"}

+++

+++ ¿Cómo se puede traducir un mensaje de error?

¿Aparece un mensaje de error en un idioma extranjero? En [esta página](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=es){target="_blank"} se muestran todos los mensajes de error y su traducción.

+++

+++ ¿Puedo crear un formulario web y recopilar respuestas en Campaign?

Sí. Cree formularios web mediante **Campaign Web Applications &amp; Forms** (consola de cliente) para tener un control total sobre la lógica y validación de los formularios, o use **Campaign Landing Pages** (interfaz de usuario web) con una moderna interfaz de arrastrar y soltar para las suscripciones y la generación de posibles clientes. Ambos recopilan datos directamente en Campaign e integran flujos de trabajo para acciones automatizadas.

**Temas relacionados:**

[Más información sobre las aplicaciones web y los formularios](../dev/webapps.md) | [Páginas de aterrizaje de la interfaz web de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++


## Actualizaciones {#upgrades}

Obtenga información sobre cómo comprobar la versión de Campaign, comprender el proceso de actualización y mantenerse informado sobre las nuevas versiones. Managed Cloud Services de Campaign v8 gestiona las actualizaciones automáticamente con una interrupción mínima.

+++ ¿Cuál es mi versión de Campaign?

Compruebe su [versión y su número integrado](upgrades.md#version) en el menú **Ayuda > Acerca de...** de la consola del cliente de Campaign.

+++

+++ ¿Cómo puedo actualizar Campaign a la versión más reciente?

Adobe Campaign se actualiza periódicamente. Cada año se publican versiones menores con nuevas funciones, mejoras y correcciones. Además, lanzamos versiones periódicamente solamente con correcciones acumulativas.

Esta frecuencia regular de actualizaciones tiene como objetivo ofrecerle lo más novedoso y lo mejor, mantener el entorno seguro y mejorar su experiencia con nuestro producto. Esta es la razón por la que creemos que es esencial que ejecute la versión más reciente de Adobe Campaign.

**Nota:** Como usuario de Cloud Services administrados, Adobe actualiza su instancia con nuevas versiones.

Más información sobre [versiones y actualizaciones de Campaign](upgrades.md).

+++

+++ ¿Cómo puedo estar informado del lanzamiento de una nueva versión?

Manténgase informado sobre las nuevas versiones de Campaign a través de estos canales:

* **representante de Adobe**: se pone en contacto directamente con usted cuando hay una nueva versión disponible
* **Notas de la versión** - Todas las versiones y cambios documentados en [Notas de la versión de Campaign](release-notes.md)
* **Actualizaciones prioritarias de productos de Adobe** - [Suscribirse](https://www.adobe.com/es/subscription/priority-product-update.html){target="_blank"} para recibir notificaciones por correo electrónico
* **Comunidad de Campaign** - Únase a [discusiones](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} para recibir actualizaciones tempranas

Como usuario de Cloud Services administrados, Adobe gestiona las actualizaciones y coordina el tiempo con usted.

**Temas relacionados:**

[Notas de la versión](release-notes.md) | [Novedades](whats-new.md) | [Versiones y actualizaciones de Campaign](upgrades.md)

+++

+++ ¿Por qué necesita mi organización una actualización?

La actualización a la versión más reciente de Campaign es fundamental para la seguridad, el rendimiento y la calidad de la asistencia.

**Ventajas principales:**

* **Seguridad mejorada**: protección contra vulnerabilidades, parches más recientes y protección de datos mejorada
* **Mejor soporte** - Resolución de problemas más rápida, acceso a correcciones de errores, soporte prioritario en versiones recientes
* **Rendimiento mejorado**: optimizaciones de la base de datos y del flujo de trabajo, mejor escalabilidad y operaciones más confiables
* **Nuevas funciones**: últimas funciones, integraciones de Adobe Experience Cloud mejoradas y mejoras en la IU moderna

Adobe recomienda encarecidamente ejecutar la versión más reciente. Como cliente de Cloud Services administrados, las actualizaciones las realiza Adobe con una interrupción mínima.

**Temas relacionados:**

[Versiones y actualizaciones de Campaign](upgrades.md) | [Novedades](whats-new.md) | [Matriz de compatibilidad](compatibility-matrix.md)

+++

+++ ¿Cuál es el proceso y la cronología de una actualización?

Como cliente de Cloud Services administrados, Adobe administra todo el proceso de actualización con un impacto mínimo en sus operaciones.

**Proceso:**

1. **Notificación**: Adobe le notifica con semanas de anticipación
2. **Planificación**: programe la actualización a una hora óptima con su representante de Adobe
3. **Preparación**: Adobe prepara el entorno y valida
4. **Ejecución**: Adobe actualiza la infraestructura con un tiempo de inactividad mínimo
5. **Validación** - Pruebas posteriores a la actualización realizadas por Adobe
6. **Actualización de la consola de cliente**: Actualiza las consolas de cliente para que coincidan con la versión del servidor

**Sus responsabilidades:**

* Coordinación de las partes interesadas internas para el calendario
* [Actualizar las consolas de cliente](connect.md#upgrade-ac-console) a la nueva versión
* Prueba de campañas y flujos de trabajo después de la actualización
* Notificar problemas al Soporte de Adobe

Adobe realiza la actualización de la infraestructura. No es necesario realizar ninguna acción técnica en los servidores de.

**Temas relacionados:**

[Versiones y actualizaciones de Campaign](upgrades.md) | [Actualizar la consola de cliente](connect.md#upgrade-ac-console) | [Notas de la versión](release-notes.md)

+++


## Campaign v8 frente a versiones anteriores {#v7-differences}

Comprenda las diferencias clave entre Campaign v8 y las versiones anteriores (Classic v7 y Standard), incluida la arquitectura, la implementación, las rutas de migración y los cambios de funciones. Tanto si viene de Campaign Classic v7 como de Campaign Standard, aprenda las novedades y cómo realizar la transición sin problemas.

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

+++ ¿Cuáles son las principales diferencias entre la versión 8 de Campaign y las versiones anteriores?

La versión 8 de Campaign se basa en una arquitectura nativa de la nube moderna con mejoras significativas:

* **Solo servicios administrados en la nube** - Totalmente hospedado por Adobe (sin opciones locales/híbridas)
* **Rendimiento superior**: hasta 20 millones de operaciones/hora con arquitectura de acceso de datos federado completo (FDAC)
* **Nueva IU web de Campaign**: interfaz moderna e intuitiva junto con la consola clásica
* **Actualizaciones automáticas**: siempre en la versión más reciente sin tiempo de inactividad
* **Funciones mejoradas**: asistente de IA, notificaciones push enriquecidas, SMS actualizados e integraciones mejoradas con Adobe Experience Cloud

**Para usuarios de Campaign Classic v7:** Obtenga información acerca de [la transición de v7 a v8](v7-to-v8.md) que incluye cambios de arquitectura, características no disponibles y consideraciones de migración.

**Para usuarios de Campaign Standard:** Descubra la [ruta de transición a la versión 8](acs-to-v8.md) y la [guía de migración de Campaign Standard](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

**Temas relacionados:**

[Funciones clave de Campaign v8](whats-new.md) | [Arquitectura de Campaign v8](../architecture/architecture.md) | [Matriz de capacidades](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Protecciones y limitaciones](ac-guardrails.md)

+++

+++ ¿Debería migrar de Campaign Classic v7 o Campaign Standard a v8?

La versión 8 de Campaign es la plataforma estratégica de Adobe, ideal para organizaciones que necesitan campañas de gran volumen (20 millones de operaciones por hora), una interfaz de usuario web moderna, beneficios nativos de la nube y asistencia a largo plazo. Las versiones anteriores llegarán al fin del soporte en los próximos años.

**Ventajas principales:**

* **Para usuarios de Campaign Standard**: interfaz de usuario web familiar, paridad de características (informes dinámicos, API de REST, páginas de aterrizaje), migración de datos sin problemas
* **Para usuarios de Campaign Classic v7**: interfaz doble (consola + interfaz de usuario web), mejor rendimiento, actualizaciones automáticas y arquitectura de FDAC mejorada

**Considere migrar si:**

* Gestionar grandes volúmenes de datos o problemas de rendimiento de experiencias
* Desea reducir la sobrecarga de TI y la administración de la infraestructura
* Necesita integración de Adobe Experience Cloud/Platform
* Desea una tecnología preparada para el futuro con actualizaciones automáticas

**Pasos siguientes:** Póngase en contacto con su representante de Adobe para evaluar la preparación para la migración y acceder a las herramientas de migración.

**Más información:** [De Campaign Classic v7 a v8](v7-to-v8.md) | [Guía de transición de Campaign Standard](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Matriz de capacidades](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}

+++

+++ ¿Cómo migre mi entorno local o híbrido de Campaign Classic v7 a Adobe Managed Services?

La migración a Adobe Managed Services proporciona una ruta estratégica desde la versión 7 local/híbrida hasta la nube, lo que ofrece una escalabilidad, seguridad y una reducción de la sobrecarga de TI mejoradas. A menudo es un paso importante antes de pasar a Campaign v8.

**Puntos clave:**

* No hay ninguna herramienta de migración automatizada disponible: se requiere planificación y ejecución manuales
* Se recomienda encarecidamente soporte de Adobe Professional Services
* Las ventajas incluyen infraestructura en la nube, parches de seguridad automáticos, asistencia técnica especializada y una ruta más sencilla hacia la versión 8 de
* La migración implica la diligencia debida, la auditoría del entorno, la limpieza de datos, la migración de etapas y la migración total de la producción

**Introducción:** Póngase en contacto con su representante de Adobe para evaluar su entorno y desarrollar un plan de migración detallado con Adobe Professional Services.

Obtenga más información acerca de [migrar a Managed Services](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605){target="_blank"}, incluidos desafíos, prácticas recomendadas y hoja de ruta de migración detallada.

+++

+++ ¿Cuáles son las diferencias clave de terminología y características en la versión 8 de Campaign?

La versión 8 de Campaign incorpora la mayoría de las funciones de la versión 7/Standard con mejoras, pero algunos términos y características difieren debido a la arquitectura nativa de la nube.

**Cambios terminológicos clave (Campaign Standard → v8):**

* Recursos personalizados → **Esquemas** | Mensajes → **Envíos** | Usuarios de productos → **Operadores**
* Grupos de seguridad → **Grupos de operadores** | Unidades organizativas → **Permisos de carpeta**

**Actualizaciones de la interfaz de usuario web de Campaign:**

* Destinatarios → **Perfiles** | Direcciones semilla → **Perfiles de prueba** | Análisis de envío → **Preparación de envío**
* Listas → **Audiencias** | Vista previa de correo electrónico → **Simular contenido**

**No disponible en la versión 8:**

* Implementaciones on-premise/híbridas (solo Cloud Services administrados)
* Acceso directo a la base de datos (API de uso)
* Gestión manual de la infraestructura (gestionada por Adobe)

**Nuevas características para usuarios de Campaign Standard:**

* Informes dinámicos, promoción centralizada de marca, API de REST, mejoras en las páginas de aterrizaje y fragmentos visuales

**Más información:** [Matriz de capacidades](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Guía de transición de v7 a v8](v7-to-v8.md) | [Transición de Campaign Standard a la versión 8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++


## Perfiles y públicos {#audiences}

Encuentre respuestas a preguntas sobre la administración de perfiles, la creación de audiencias, la importación de datos y la segmentación de destinatarios para sus campañas.

+++ ¿Cómo se crean los destinatarios? 

Cree destinatarios manualmente en la consola del cliente para perfiles individuales, importe desde archivos (CSV/TXT) para adiciones masivas, utilice formularios web para el registro automático o integre a través de API desde sistemas externos. Utilice flujos de trabajo de importación para cargas de datos recurrentes.

**Temas relacionados:**

[Crear perfiles manualmente](../audiences/create-profiles.md) | [Importar perfiles de un archivo](../audiences/import-profiles.md) | [Recopilar perfiles con formularios web](../audiences/collect-profiles.md)

+++

+++ Forma de importar los perfiles

Campaign ofrece varios métodos de importación: importación de archivos sencilla mediante el asistente de importación, importación basada en flujos de trabajo para transformaciones complejas, importación recurrente con flujos de trabajo programados desde SFTP e importación de API para la integración mediante programación.

Para las importaciones de archivos, prepare el archivo de datos (codificación CSV/TXT, UTF-8), utilice el asistente de importación o el flujo de trabajo, asigne columnas a campos de Campaign, defina reglas de actualización/inserción y realice la prueba primero con un pequeño ejemplo. Utilice flujos de trabajo para importaciones recurrentes y aplique reglas de anulación de duplicación.

**Temas relacionados:**

[Guía de importación de datos](../start/import.md) | [Flujo de trabajo de importación recurrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [Actividad de carga de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=es){target="_blank"}

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

**Temas relacionados:**

[Crear audiencias](../audiences/create-audiences.md) | [Actividad de actualización de lista](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ ¿Cómo duplicar una población antes de enviar un mensaje? 

Utilice la actividad **[!UICONTROL Deduplication]** en un flujo de trabajo para eliminar los destinatarios duplicados antes de la entrega. Colóquela entre sus actividades **[!UICONTROL Query]** y **[!UICONTROL Delivery]** y, a continuación, elija los criterios de anulación de duplicación (generalmente la dirección de correo electrónico o el ID de destinatario) y qué registro desea mantener.

**Sugerencia:** Anule siempre la duplicación antes de enviar para asegurarse de que cada persona reciba su mensaje solo una vez.

Más información sobre la [actividad de deduplicación](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=es){target="_blank"}

+++

+++ ¿Cómo se identifican y se segmentan los suscriptores a un newsletter? 

Campaign realiza automáticamente un seguimiento de las suscripciones a boletines informativos a través de servicios informativos. Para dirigirse a suscriptores:

* Use una actividad **[!UICONTROL Query]** y filtre en **[!UICONTROL Subscriptions]** > seleccione el servicio del boletín informativo
* Seleccione a los suscriptores directamente de su envío eligiendo **[!UICONTROL To > Subscribers of an information service]**
* Generar listas de suscriptores con la actividad de flujo de trabajo **[!UICONTROL Subscription Services]**

Campaign realiza un seguimiento del historial de suscripciones/bajas y administra automáticamente la inclusión/exclusión.

**Temas relacionados:**

[Administrar suscripciones](../start/subscriptions.md) | [Actividad de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=es){target="_blank"}

+++

+++ ¿Cuál es la práctica recomendada para excluir perfiles de una población objetivo? 

Utilice la actividad **[!UICONTROL Exclusion]** en un flujo de trabajo para eliminar perfiles no deseados del destinatario. Colóquelo después de las actividades de segmentación y defina qué población excluir.

Más información sobre la [Actividad de exclusión](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ ¿Puedo utilizar perfiles externos sin importarlos en Campaign?

Sí, la versión 8 de Campaign le permite trabajar con perfiles externos almacenados en una base de datos externa sin cargarlos en Adobe Campaign. [Más información](../audiences/external-profiles.md).

+++

+++ ¿Cómo creo perfiles de prueba para mis envíos?

Los perfiles de prueba son destinatarios especiales que se utilizan para enviar pruebas y validar envíos sin afectar a la base de datos de producción. Créelos en **[!UICONTROL Profiles and Targets > Test profiles]** o use la característica **[!UICONTROL Seed addresses]** para agregar automáticamente destinatarios de prueba a sus envíos para garantizar la calidad y supervisar la bandeja de entrada.

Más información sobre [Perfiles de prueba](../audiences/test-profiles.md)

+++

## Diseño de mensaje {#design}

Aprenda a diseñar mensajes de marketing eficaces en Campaign v8, incluidas plantillas de correo electrónico, técnicas de personalización y contenido multilingüe. Diseñe sus mensajes en la consola del cliente o use el moderno **Designer de correo electrónico** de la interfaz de usuario web de Campaign para disfrutar de una experiencia de edición visual mejorada.

+++ ¿Cuáles son las prácticas recomendadas para diseñar correos electrónicos en Campaign?

Directrices clave: Garantice un diseño adaptable a dispositivos móviles, utilice un código compatible con HTML 4.0/XHTML con CSS en línea, optimice las imágenes (menos de 100 KB) con texto alternativo, utilice campos de combinación de personalización, realice pruebas en clientes de correo electrónico antes de enviarlo e incluya una versión de texto sin formato. Consiga un tamaño total de correo electrónico inferior a 500 KB para conseguir una entrega óptima.

[Guía de diseño de correo electrónico](../send/email.md) | [Prácticas recomendadas de envío](delivery-best-practices.md)

+++

+++ ¿Qué es una plantilla de envíos?

Una plantilla de envíos es un envío preconfigurado que guarda todos los ajustes y parámetros para reutilizarlos en varias campañas. Las plantillas incluyen reglas de destino, diseño de contenido, personalización, configuración técnica (remitente, respuesta) y reglas de tipología. Cree una vez y reutilice para mantener la coherencia y acelerar la creación de campañas.

Aprenda a [crear plantillas de envío](../send/create-templates.md)

+++

+++ ¿Puedo importar fácilmente un HTML existente para crear un correo electrónico en Campaign?

Sí. Importe contenido de HTML mediante copiar/pegar directamente en el editor de contenido, cargar archivos desde el equipo o cargar desde una dirección URL. Asegúrese de que HTML utiliza código compatible con el correo electrónico (HTML 4.0/XHTML) con CSS en línea y aloje imágenes en un servidor público. Campaign añade automáticamente la personalización y el seguimiento a HTML importado.

**Sugerencia:** Para obtener la mejor experiencia de diseño de correo electrónico, use **Email Designer** en la interfaz de usuario de Campaign Web, que ofrece funciones modernas de arrastrar y soltar y plantillas adaptables integradas, en lugar de importar HTML sin procesar.

Aprenda a [importar contenido de HTML](../send/defining-the-email-content.md)

+++

+++ ¿Cómo puedo crear una newsletter basada en suscripción en Campaign?

Sí. Utilice los servicios informativos de Campaign para administrar las suscripciones al boletín informativo. Las funciones clave incluyen la administración automática de la inclusión/exclusión, el seguimiento de la suscripción, la administración del cumplimiento (RGPD, CAN-SPAM), la compatibilidad con varios boletines informativos, la integración web para formularios de registro y la entrega segmentada a los suscriptores.

Aprenda a [administrar suscripciones](../start/subscriptions.md)

+++

+++ ¿Cómo puedo personalizar los mensajes?

Campaign ofrece funcionalidades de personalización para crear mensajes relevantes y dirigidos en función de los datos del destinatario, el comportamiento y las preferencias.

**Opciones de Personalization:**

* **Campos de personalización** - Insertar datos de destinatario (por ejemplo, `"Hello {{firstName}}")`
* **Bloques de personalización**: utilice bloques de contenido predefinidos o personalizados
* **Contenido condicional**: muestra contenido diferente según los criterios del destinatario
* **Datos de comportamiento**: aprovecha el historial de navegación, los patrones de compra o las métricas de participación

Pruebe la personalización antes de enviar para verificar que los campos de combinación y la lógica condicional funcionan correctamente.

**Temas relacionados:**

[Guía de Personalization](../send/personalize.md) | [Campos de personalización](../send/personalization-fields.md) | [Contenido condicional](../send/conditions.md)

+++

+++ ¿Puedo enviar mensajes multilingües?

Sí. La versión 8 de Campaign ofrece funcionalidades multilingües, con la **IU web de Campaign** que proporciona el enfoque más sencillo. La interfaz de usuario web ofrece un envío multilingüe nativo con variantes de idioma: agregue variantes de idioma al envío y Campaign enviará automáticamente la versión adecuada en función del idioma preferido del destinatario. Disponible para correo electrónico, notificaciones push, SMS y mensajes transaccionales.

Funciones clave: duplicación automática de contenido, envío automático basado en idiomas, reserva de idioma predeterminada y administración sencilla de variantes.

La consola del cliente también admite contenido multilingüe mediante contenido condicional y flujos de trabajo, pero requiere una configuración más manual.

[Envíos multilingües (interfaz de usuario web)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Contenido condicional (consola de cliente)](../send/conditions.md)

+++

+++ ¿Puedo localizar un formulario web?

Sí. Las aplicaciones web de Campaign admiten la localización en varios idiomas. Defina traducciones para todos los elementos del formulario (etiquetas, botones, mensajes, texto de error), con detección automática de idioma basada en la configuración del perfil de destinatario o del explorador. Se admiten versiones en varios idiomas dentro de una sola aplicación web, con reserva a un idioma predeterminado cuando sea necesario.

Más información sobre la [localización de aplicaciones web](../dev/webapps.md)

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

[Descripción general del Asistente de IA](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Casos de uso del Asistente de IA](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Alineación de marca](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Prueba y envío de mensajes {#send}

Conozca las prácticas recomendadas para probar, validar, enviar y rastrear sus mensajes de marketing para garantizar el éxito de la entrega de campañas.

+++ ¿Qué es el análisis de entrega?

El análisis de envío es una fase de validación en la que Campaign se ejecuta antes de enviar. Calcula la población objetivo, valida el contenido, comprueba si hay errores, aplica reglas de tipología y calcula el volumen de entrega.

Campaign genera registros que muestran advertencias y errores. Los errores bloquean la entrega y deben corregirse; las advertencias son aconsejables. Revise siempre los registros de análisis antes de enviar.

Obtenga más información en la [guía de análisis de envío](../send/delivery-analysis.md)

+++

+++ ¿Por qué debería generar pruebas?

Las pruebas son mensajes de prueba que validan la entrega antes de enviarlo a la audiencia principal. Utilice pruebas para verificar la personalización, probar el procesamiento de contenido en clientes de correo electrónico, confirmar vínculos y realizar un seguimiento del trabajo, comprobar imágenes y archivos adjuntos y validar la capacidad de respuesta móvil.

Las pruebas ayudan a detectar errores antes de que lleguen a miles de destinatarios, habilitan la aprobación de las partes interesadas y prueban la ubicación en la bandeja de entrada. Envíe pruebas a varios clientes de correo electrónico y dispositivos, y obtenga siempre la aprobación antes de que se envíe el flujo de trabajo de producción.

Obtenga más información en la [Guía de pruebas y vista previa](../send/preview-and-proof.md)

+++

+++ ¿Cómo se utilizan las direcciones semilla en Adobe Campaign?

Las direcciones semilla son destinatarios especiales que se añaden automáticamente a cada entrega para realizar pruebas, garantizar la calidad y supervisar el contenido, sin coincidir con los criterios de destino. Útil para la monitorización continua, las pruebas de ubicación de bandeja de entrada, la validación de correo directo y la visibilidad de las partes interesadas.

**Diferencias clave de las pruebas:**

* **Direcciones semilla**: agregadas automáticamente a los envíos de producción, cuente para enviar el volumen
* **Pruebas**: la prueba se envía antes de la producción, no se cuenta en el volumen, se usa para la validación

Administrar direcciones semilla en **[!UICONTROL Resources > Campaign management > Seed addresses]**. Mantenga las listas pequeñas para evitar afectar a las métricas de envío.

[Guía de direcciones semilla](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ ¿Cómo puedo configurar un proceso de aprobación antes de enviar mensajes?

Campaign proporciona flujos de trabajo de aprobación para garantizar que los mensajes cumplan los estándares de calidad antes de enviarlos. Configure aprobaciones para el contenido, el destinatario, la extracción (correo postal) y el presupuesto en el nivel de campaña o entrega.

**Configuración:**

Cree grupos de operadores en **[!UICONTROL Administration > Access management > Operator groups]** y luego asigne grupos de aprobación en las propiedades de campaña o entrega. Campaign envía correos electrónicos de notificación a los revisores que pueden aprobar, rechazar o solicitar cambios.

**Para envíos independientes (no en una campaña):**

Use **pruebas como proceso de aprobación**. Envíe pruebas al grupo de aprobación para su validación y envíe siempre una nueva prueba después de realizar cambios para garantizar que las partes interesadas revisen la versión más reciente.

**Temas relacionados:**

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

Aprenda a [Configurar el envío de ondas](../send/configure-and-send.md#sending-using-multiple-waves)

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

**Temas relacionados:**

[Cree su primer correo electrónico](create-message.md) | [Guía de diseño de correo electrónico](../send/email.md)

+++

+++ ¿Cómo se puede programar una entrega?

Campaign le permite programar envíos para envíos futuros a fin de optimizar los tiempos de envío y coordinar las campañas.

**Opciones de programación:**

* **Propiedades de envío** - Enviar inmediatamente, programar para una fecha/hora específica o diferir por horas/días
* **Nivel de campaña**: coordine todas las entregas dentro de una campaña
* **Actividad del Planificador de flujo de trabajo**: para envíos recurrentes, patrones complejos y campañas activadas por eventos

Campaign también admite la optimización de la fecha de contacto (mejor hora de envío por destinatario) y la adaptación de la zona horaria (misma hora local para todos los destinatarios).

Aprenda a [programar envío](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ ¿Se puede añadir un archivo adjunto a los correos electrónicos?

Sí. Campaign admite archivos adjuntos estáticos (el mismo archivo para todos los destinatarios) y personalizados (diferentes archivos por destinatario según los datos del perfil). Agregue archivos adjuntos en la sección **[!UICONTROL Attachments]** de sus propiedades de entrega.

**Consideraciones importantes:**

* Mantener los archivos adjuntos en 1 MB para una entrega óptima
* Los archivos adjuntos pueden almacenar en déclencheur los filtros de correo no deseado; pruébelos a fondo antes de enviarlos
* Evite los tipos de archivo que suelen bloquear los clientes de correo electrónico (.exe, .zip, .js)
* Para archivos grandes, considere la posibilidad de utilizar vínculos de descarga rastreados en su lugar

Utilice formatos de archivo seguros (PDF, JPEG, PNG, DOCX) y pruébelos con direcciones semilla antes de que se envíe el proceso de producción.

Obtenga más información en la [guía de archivos adjuntos de correo electrónico](../send/email.md#attachments)

+++

+++ ¿Cómo puedo configurar los vínculos rastreados en una entrega de correo electrónico?

Campaign convierte automáticamente todas las direcciones URL del correo electrónico en vínculos rastreados para supervisar la participación de los destinatarios. Acceda a la sección **[!UICONTROL Tracking]** de su envío para configurar las opciones de seguimiento de cada vínculo.

**Opciones de configuración:**

* **Habilitar/deshabilitar seguimiento** - Control de seguimiento por vínculo
* **Etiquetas de vínculos** - Agregue nombres descriptivos para los informes (por ejemplo, &quot;Comprar ahora en CTA&quot;)
* **Categorías de vínculos**: agrupe vínculos por tipo para el análisis agregado
* **Tipo de seguimiento** - Rastrear clics, aperturas o ambos

Campaign realiza un seguimiento de los vínculos de contenido, de las páginas espejo y de los vínculos de cancelación de suscripción, y puede incluir un píxel de seguimiento opcional para las aperturas de correo electrónico. Utilice etiquetas y categorías significativas para simplificar la creación de informes e identificar rápidamente contenido de alto rendimiento.

**Temas relacionados:**

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

**Temas relacionados:**

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

**Temas relacionados:**

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

**Temas relacionados:**

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

[Crear un flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=es){target="_blank"} | [Actividades de flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [Prácticas recomendadas de flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=es){target="_blank"} | [Casos de uso del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ ¿Cómo se pueden importar datos en Campaign?

**Métodos:** Asistente para importación (CSV/TXT de un solo uso), importación basada en flujo de trabajo (**[!UICONTROL Data loading (file)]** actividad para importaciones complejas/recurrentes con transformaciones), API de REST (sincronización programática/en tiempo real).

**Prácticas recomendadas:** Realice pruebas con muestras pequeñas, utilice la codificación UTF-8, asigne los campos correctamente, aplique la anulación de duplicación y programe importaciones grandes fuera del pico.

[Prácticas recomendadas de importación](../start/import.md) | [Actividad de carga de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=es){target="_blank"} | [Flujo de trabajo de importación recurrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ ¿Cuáles son los casos más comunes de uso de flujos de trabajo en Campaign?

Los flujos de trabajo automatizan los procesos de marketing, incluidos:

**Administración de datos:** Importar/cargar datos, limpiar, ampliar, administrar listas\
**Automatización de la campaña:** Serie de bienvenida, campañas de cumpleaños, renovación de la participación, abandono del carro de compras\
**Segmentación avanzada:** pruebas A/B, segmentación dinámica, puntuación de posibles clientes, orquestación entre canales\
**Supervisión:** Supervisión de flujo de trabajo/entrega, alertas, mantenimiento de la base de datos\
**Integración:** sincronización de CRM, integraciones de API, flujos de trabajo activados por eventos

[Biblioteca de casos de uso del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Crear un flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=es){target="_blank"} | [Prácticas recomendadas de flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=es){target="_blank"}

+++

+++ ¿Cómo se pueden actualizar los datos de Campaign con un flujo de trabajo?

Utilice la actividad **[!UICONTROL Update data]** para operaciones de base de datos en lotes: Insertar (agregar nuevos registros), Actualizar (modificar los existentes), Insertar o actualizar (actualizar), Eliminar (eliminar los registros coincidentes).

**Usuarios comunes:** Actualizar atributos de perfil, sincronizar con sistemas externos, mantener suscripciones a listas, limpiar/deduplicar datos y aplicar cambios de estado masivos.

Configure las claves de reconciliación para conseguir una coincidencia precisa y elija las opciones de actualización.

[Actualizar actividad de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=es){target="_blank"} | [Actividades de administración de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ ¿Cómo se pueden aprovechar las funcionalidades de administración de datos?

Las actividades de gestión de datos permiten operaciones sofisticadas: Enrichment (adición de datos de tablas relacionadas), Split (poblaciones de segmentos), Deduplication (eliminación de duplicados), Update data (operaciones masivas), Change dimension (cambio de dimensiones de segmentación), Intersection/Union/Exclusion (combinación/filtrado de poblaciones).

**Usos comunes:** Enriquezca con datos de compra/comportamiento, segmente audiencias, elimine duplicados, integre bases de datos externas (FDA) y cree consultas complejas de varias tablas.

[Actividades de administración de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [Actividad de enriquecimiento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=es){target="_blank"}

+++

+++ ¿Se puede automatizar la entrega de mensajes personalizados?

Sí. Generar flujos de trabajo automatizados: Query (audiencia de destino) → Enrichment (adición de datos de personalización) → Split (segmentos opcionales) → Delivery (mensajes personalizados) → Scheduler (ejecución recurrente).

**Personalization:** Use datos de perfil, datos de comportamiento, contenido condicional y valores dinámicos. Escenarios comunes: campañas de cumpleaños, abandono del carro de compras, programas de fidelidad, recuperación, mensajes activados por eventos.

[Guía de Personalization](../send/personalize.md) | [Casos de uso del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=es){target="_blank"}

+++

+++ ¿Cómo se puede dividir un público en subconjuntos con un flujo de trabajo?

Utilice la actividad **[!UICONTROL Split]** para dividir poblaciones: Condiciones de filtrado (edad, ubicación, estado de VIP), Distribución porcentual (pruebas A/B), Límite de registros (primer N, X % superior), Agrupación de datos (un subconjunto por valor).

**Usos comunes:** pruebas A/B, enrutamiento de preferencias de canal, despliegue progresivo, mensajería específica de segmento, equilibrio de carga. Cada subconjunto fluye a una transición independiente para un procesamiento diferente.

[Dividir actividad](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=es){target="_blank"} | [Guía de pruebas A/B](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ ¿Cómo se pueden actualizar los datos de destinatario de un archivo externo?

Sí. Flujo de trabajo: Carga de datos (archivo) → Enriquecimiento (opcional) → Reconciliación (claves de coincidencia como correo electrónico/ID) → Actualización de datos (actualice los registros coincidentes, inserte nuevos si no coinciden).

**Usuarios comunes:** actualizar atributos de perfil desde CRM, actualizar estados de suscripción, sincronizar puntos de lealtad, actualizar preferencias de inclusión/exclusión.

**Prácticas recomendadas:** Use identificadores únicos, valide primero los datos, pruebe con muestras y programe actualizaciones regulares.

[Guía de importación de datos](../start/import.md) | [Actividad de carga de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=es){target="_blank"} | [Actualizar actividad de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=es){target="_blank"}

+++

+++ ¿Cómo se pueden identificar y segmentar nuevos destinatarios?

Campo de consulta **[!UICONTROL Created date]** para seleccionar destinatarios agregados dentro de un intervalo de tiempo específico.

**Flujo de trabajo de bienvenida automatizado:** Programador (ejecutar a diario) → Consulta (seleccionar nuevos destinatarios) → Anulación de duplicación (opcional) → Entrega (mensaje de bienvenida) → Actualizar datos (marcar como &quot;bienvenido&quot;).

**Avanzadas:** Utilice funciones de agregado para identificar dinámicamente las adiciones recientes.

[Actividad de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=es){target="_blank"} | [Uso de agregados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=es){target="_blank"}

+++

+++ ¿Cómo utilizo las actividades de flujo de trabajo?

Cuatro categorías de actividades:

**Segmentación:** Consulta, división, deduplicación, enriquecimiento, intersección, unión, exclusión (definir/refinar audiencia)\
**Control de flujo:** Planificador, espera, prueba, bifurcación, AND-join, OR-join, salto (administrar lógica/tiempo)\
**Acción:** Entrega, Actualización de datos, Carga/extracción de datos, Código JavaScript (realizar operaciones)\
**Evento:** Señal externa, Recolector de archivos, Transferencia HTTP (reaccionar a déclencheur)

Arrastre desde la paleta, haga doble clic para configurar y conectar con transiciones.

[Actividades de segmentación](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"} | [Control de flujo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"} | [Actividades de acción](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=es){target="_blank"}

+++

+++ ¿Cuáles son las prácticas recomendadas de flujo de trabajo?

**Diseño:** Borrar nombres, agregar etiquetas/descripciones, agrupar actividades relacionadas, dividir procesos complejos en flujos de trabajo más pequeños\
**Rendimiento:** Limite los tamaños de las consultas, utilice tablas temporales, programe fuera del pico y evite bucles excesivos\
**Control de errores:** Agregar rutas de error, configurar alertas, probar con muestras, revisar registros\
**Mantenimiento:** Archivar flujos de trabajo obsoletos, control de versiones, limitar complejidad (&lt;20 actividades), usar plantillas\
**Seguridad:** Aplicar permisos, limpiar datos temporales, usar variables y no valores codificados

[Guía de prácticas recomendadas de flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=es){target="_blank"} | [Supervisar flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=es){target="_blank"}

+++

## Configuración de campaña {#settings}

Configure la instancia de Campaign con las configuraciones, integraciones y ajustes adecuados para optimizar las operaciones de marketing.

+++ ¿Puedo cambiar el idioma de la interfaz de Campaign? 

Depende de la interfaz que esté utilizando. El idioma de la consola de cliente **1} es fijo, pero la interfaz de usuario web de** Campaign **permite que los usuarios individuales cambien sus preferencias de idioma.**

**Consola de cliente (aplicación de escritorio):**

* El idioma se establece cuando se crea la instancia y no se puede cambiar
* La consola de cliente y el servidor deben utilizar el mismo idioma
* Cada instancia de Campaign funciona en un solo idioma
* Para las instalaciones en inglés, puede elegir entre inglés de EE. UU. o inglés de Reino Unido (difieren en los formatos de fecha y hora)

**IU web de Campaign:**

* Los usuarios pueden cambiar el idioma de la interfaz de forma independiente mediante las preferencias de perfil
* Se admiten varios idiomas con un formato específico de la configuración regional para fechas, horas y números
* La preferencia de idioma de la interfaz de usuario web es independiente del idioma del servidor de Campaign y de la consola del cliente


**Temas relacionados:**

[Cambiar idioma en la interfaz de usuario web de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Introducción a la consola del cliente de Campaign](connect.md)

+++

+++ ¿Qué es el Panel de control de Campaign de Campaign y cómo puedo acceder a él?

El Panel de control de Campaign de Campaign es una interfaz administrativa basada en web que ayuda a los administradores de Campaign a aumentar la eficacia mediante la administración de la configuración y la supervisión del uso en todas las instancias de Campaign. Proporciona funciones de autoservicio para administrar configuraciones de instancia críticas sin ponerse en contacto con el soporte de Adobe.

**Funcionalidades clave:**

* **Administración de subdominios**: delegue y administre subdominios, supervise certificados SSL
* **Supervisión del almacenamiento**: haga un seguimiento del uso de la base de datos y evite problemas de almacenamiento
* **Administración SFTP**: supervise el almacenamiento SFTP, administre las listas de permitidos IP y las claves SSH
* **Configuración de instancia**: configure listas de permitidos IP, administre permisos de URL y revise detalles de instancias
* **Supervisión de perfiles activos**: realice un seguimiento del uso de perfiles activos en relación con los derechos
* **Supervisión del rendimiento**: supervise el rendimiento de la base de datos y del flujo de trabajo
* **Capacidad de envío de correo electrónico**: configuración de DMARC, BIMI y otros registros de autenticación

**Requisitos de acceso:**

* **Solo usuarios administradores** - El Panel de control de Campaign está restringido a usuarios con derechos de administrador
* **Autenticación IMS de Adobe**: acceso a través de Adobe Experience Cloud con su Adobe ID
* **Cloud Services administrados de Campaign v8**: solo disponible para instancias hospedadas

**Recursos adicionales:**

[Documentación de Panel de control de Campaign](https://experienceleague.adobe.com/es/docs/control-panel/using/control-panel-home){target="_blank"} | [Tutoriales en Panel de control de Campaign](https://experienceleague.adobe.com/en/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

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

**Temas relacionados:**

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

**Temas relacionados:**

[Acerca de la capacidad de entrega en Campaign](../send/about-deliverability.md) | [Guía de prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es){target="_blank"}

+++

+++ ¿A qué bases de datos externas puedo conectar Campaign? 

La versión 8 de Campaign admite conexiones de acceso de datos federado (FDA) a los principales sistemas de bases de datos empresariales (bases de datos en la nube, bases de datos empresariales, almacenes de datos y plataformas de big data).

Las versiones de base de datos compatibles y los requisitos de conexión varían. Compruebe la [Matriz de compatibilidad](compatibility-matrix.md) de su versión de Campaign v8 para confirmar la compatibilidad con bases de datos específicas y garantizar las licencias adecuadas para los conectores FDA.

[Configuración de conexiones de FDA](../connect/fda.md)

+++

+++ ¿Se puede integrar Adobe Campaign con sistemas CRM?

Sí. Campaign proporciona conectores CRM nativos para la sincronización bidireccional con los principales sistemas CRM. Sincroniza datos de contacto, posibles clientes, cuentas, registros de envío, datos de seguimiento y métricas de participación. Admite modos de sincronización programados, manuales y en tiempo real (mediante API).

Utilice el asistente del conector CRM de Campaign para asignar campos, seleccionar tablas y programar la sincronización. Compruebe la [matriz de compatibilidad](compatibility-matrix.md) para ver las versiones de CRM admitidas.

[Configuración del conector CRM](../connect/crm.md) | [Actividades de CRM de flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html){target="_blank"}

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

**Temas relacionados:**

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

**Temas relacionados:**

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

**Temas relacionados:**

[Ampliar modelo de datos](../dev/extend-schema.md) | [Estructura del esquema](../dev/schemas.md) | [Prácticas recomendadas del modelo de datos](../dev/datamodel-best-practices.md)

+++

## Creación de informes {#reporting}

Obtenga información sobre las funcionalidades de creación de informes de Campaign, incluidos informes integrados, informes personalizados y herramientas de análisis de datos como cubos.

+++ ¿Cómo se pueden crear nuevos informes?

Campaign ofrece varias opciones de creación de informes en función de sus necesidades y experiencia técnica: informes integrados, análisis descriptivo, informes personalizados en la consola del cliente y cubos.

**Opciones de informes:**

* **Informes integrados**: se puede acceder a los informes de envío, campaña y seguimiento listos para usar desde la pestaña **[!UICONTROL Reports]**
* **Análisis descriptivo**: informes estadísticos rápidos sobre cualquier dato con una interfaz dirigida por un asistente
* **Informes personalizados**: informes avanzados creados por usuarios técnicos con el editor de informes
* **Cubos**: exploración de datos multidimensional y análisis de tabla dinámica

**Importante:** La campaña está diseñada para generar informes de operaciones de marketing, no como una herramienta de inteligencia empresarial especializada. Para necesidades analíticas complejas, considere la posibilidad de integrar con Adobe Analytics o plataformas de BI dedicadas.

**Temas relacionados:**

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

Más información sobre [Análisis descriptivo](../reporting/built-in-reports.md)

+++

+++ ¿Cómo se puede diseñar informes avanzados con mis datos?

Utilice la consola del cliente para crear informes personalizados avanzados con funcionalidades de análisis complejas.

En la consola del cliente, puede:

* Creación de informes complejos con consultas SQL y cálculos personalizados
* Creación de informes de varias páginas con gráficos, tablas y tablas dinámicas
* Diseño de formato condicional y contenido dinámico
* Acceso al modelo de datos completo de Campaign y a las bases de datos externas (FDA)

Obtenga información sobre cómo [crear informes personalizados (consola de cliente)](../reporting/custom-reports.md)

+++

+++ ¿Qué es un cubo y cómo puedo utilizarlo para la creación de informes?

Los cubos son estructuras de datos multidimensionales que permiten a los usuarios empresariales explorar y analizar datos de Campaign a través de tablas dinámicas sin habilidades técnicas. Considérelos como modelos de datos preconfigurados que simplifican los informes complejos. Esta herramienta de creación de informes está disponible tanto en la consola del cliente como en la interfaz de usuario web de Campaign.

* Los usuarios técnicos crean y configuran cubos que definen dimensiones (tiempo, geografía, canales) y medidas (aperturas, clics, ingresos)
* Los usuarios empresariales seleccionan un cubo al crear informes y arrastran y sueltan dimensiones para explorar datos
* Los datos se agregan y calculan automáticamente en función de la configuración del cubo
* Los resultados se pueden mostrar como tablas dinámicas, gráficos o exportarse a Excel

Aprenda a [explorar datos con cubos](../reporting/gs-cubes.md)

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

**Análisis avanzado:**

* Acceder a las respuestas de encuestas desde la ficha **[!UICONTROL Responses]** y exportar datos
* Utilice la actividad **[!UICONTROL Survey responses]** en flujos de trabajo para segmentar destinatarios según sus respuestas
* Combinación de datos de encuestas con otros datos de Campaign para la segmentación y personalización
* Creación de informes y cubos personalizados para análisis de encuestas multidimensional

**Temas relacionados:**

[Introducción a las encuestas](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Informes de encuesta](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ ¿Cómo se puede compartir el acceso a mis informes?

Controle la visibilidad del informe mediante permisos de carpeta y derechos asignados en Campaign.

**Métodos de control de acceso:**

* **Permisos de carpeta** - Colocar informes en carpetas con acceso apropiado para grupos de usuarios
* **Derechos asignados**: asigne derechos para ver, crear o modificar informes
* **Contexto de visualización**: defina dónde aparecen los informes (carpeta Informes, fichas de campaña, pantallas de envío)

**Configuración:** Guarde el informe en una carpeta específica → Configure el acceso a carpetas para grupos de operadores → Defina las propiedades del informe y el contexto de visualización.

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

**Temas relacionados:**

[Informes personalizados](../reporting/custom-reports.md) | [Informes de IU web de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Desarrolladores {#developers}

Acceda a información técnica para desarrolladores, incluidos detalles del modelo de datos, esquemas, API y funcionalidades de personalización.

+++ ¿Qué es el modelo de datos de Campaign?

El modelo de datos de Campaign es una estructura de base de datos relacional basada en esquemas que consta de tablas integradas (destinatarios, envíos, campañas) que se pueden ampliar para satisfacer sus necesidades comerciales.

**Conceptos clave:** esquemas (definiciones XML), tablas integradas, vínculos (relaciones), enumeraciones (listas de valores), extensiones (campos/tablas personalizados).

**Esquemas principales:** Destinatario (`nms:recipient`), Envío (`nms:delivery`), Flujo de trabajo (`xtk:workflow`), Campaña (`nms:operation`), Registros de seguimiento.

Es esencial comprender el modelo de datos para flujos de trabajo, consultas, extensiones de esquema e integraciones.

[Modelo de datos de Campaign](../dev/datamodel.md) | [Prácticas recomendadas del modelo de datos](../dev/datamodel-best-practices.md)

+++

+++ ¿Cómo se trabaja con los esquemas de Campaign?

Los esquemas definen la estructura de datos de Campaign en formato XML, especificando la estructura de tabla, las propiedades de campo, las relaciones, los índices y el control de acceso.

**Trabajando con esquemas:**

* **Vista:** Acceso mediante **[!UICONTROL Administration > Configuration > Data schemas]**
* **Ampliar:** Cree esquemas de extensión (por ejemplo, `cus:recipient`) para agregar campos personalizados sin modificar los esquemas principales
* **Crear:** Crear nuevas tablas para datos específicos de la empresa
* **Actualización:** Aplicar cambios mediante **[!UICONTROL Tools > Advanced > Update database structure]**

**Usos comunes:** Agregue campos personalizados a la tabla de destinatarios, cree tablas personalizadas, defina relaciones e implemente modelos específicos de la empresa.

**Importante:** Nunca modifique directamente los esquemas integrados. Utilice siempre esquemas de extensión para mantener la compatibilidad de actualización.

[Introducción a los esquemas](../dev/schemas.md) | [Ampliar un esquema](../dev/extend-schema.md)

+++

+++ ¿Cómo se utiliza una tabla de destinatarios personalizada?

Utilice una tabla de destinatarios personalizada al segmentar cuentas B2B, datos de suscriptores independientes, sistemas externos o arquitecturas de varias marcas en lugar de la tabla de destinatarios estándar.

**Implementación:** crear esquema personalizado con campos obligatorios (correo electrónico, clave principal, exclusiones) → configurar asignaciones de destino → actualizar plantillas de entrega → adaptar flujos de trabajo/consultas.

**Consideraciones clave:** debe incluir los campos de envío requeridos, los flujos de trabajo o formularios necesitan adaptación y las pruebas son críticas antes de la migración de producción.

**Práctica recomendada:** Extienda primero la tabla de destinatarios estándar. Utilice únicamente tablas personalizadas cuando sea realmente necesario debido a la complejidad añadida.

[Tabla de destinatarios personalizada](../dev/custom-recipient.md) | [Asignaciones de destino](../audiences/target-mappings.md)

+++

+++ ¿Cuáles son las mejores prácticas para definir las consultas en Campaign? 

El editor de consultas de Campaign crea consultas de base de datos visualmente sin SQL, utilizadas en actividades de flujo de trabajo, direccionamiento de envíos, listas, informes y filtros.

**Prácticas recomendadas:**

* Inicio simple: generación incremental, prueba cada paso
* Uso de dimensiones de filtrado: aprovechar las relaciones de tabla
* Optimización del rendimiento: indexe campos consultados, evite cálculos complejos
* Reutilización de filtros predefinidos para mantener la coherencia
* Pruebe primero con muestras pequeñas
* Documentar consultas complejas

**Patrones comunes:** Los abridores de envíos de destino, los contactos inactivos, los segmentos por comportamiento y los destinatarios anteriores excluidos.

**Acceso:** **[!UICONTROL Tools > Generic query editor]** para exploración ad hoc.

[Editor de consultas](../start/query-editor.md) | [Actividad de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=es){target="_blank"}

+++

+++ ¿Cómo puedo importar un paquete de datos? 

Importe paquetes mediante **[!UICONTROL Tools > Advanced > Import package]** en la consola del cliente. Los paquetes contienen configuraciones de Campaign (esquemas, flujos de trabajo, tipologías) y datos para su implementación entre instancias.

**Tipos de paquetes:** Paquete de usuario (configuraciones personalizadas), Paquete de plataforma (proporcionado por Adobe), Paquete de datos (datos reales).

**Prácticas recomendadas:** Realice primero una prueba en el desarrollo, realice una copia de seguridad antes de importarla y exporte desde la misma versión o una anterior.

[Trabajo con paquetes de datos](../dev/packages.md)

+++

+++ ¿Dónde puedo encontrar la lista de las API de Campaign v8?

La versión 8 de Campaign proporciona API de SOAP (operaciones de consola del cliente), API de REST (integraciones modernas) y API de JavaScript (scripts de flujo de trabajo).

**Usuarios comunes:** Integrar con CRM/ERP, automatizar campañas, sincronizar datos, crear soluciones de supervisión, crear interfaces externas.

**Acceso:** [Documentación de la API de Campaign v8](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=es){target="_blank"}

+++


+++ ¿Cómo superviso los flujos de trabajo desde la API?

Las API de Campaign permiten controlar mediante programación los flujos de trabajo: inicio, pausa/reanudación, parada, estado de la consulta, recuperación de registros, monitorización del progreso de la actividad.

**Extremo de API:** `POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**Comandos:** `{"method":"start"}`, `{"method":"pause"}`, `{"method":"resume"}`, `{"method":"stop"}`

**Casos de uso:** Cree paneles de supervisión, implemente alertas automatizadas, organice a partir de programadores externos, cree dependencias entre instancias y genere informes personalizados.

**Práctica recomendada:** Combine la supervisión de la API con la pista de auditoría para un control exhaustivo.

[Control de flujos de trabajo mediante API](../dev/api/controlling-a-workflow.md)

+++

+++ ¿Cómo se puede actualizar la estructura de la base de datos?

Después de modificar esquemas (agregar campos, crear tablas, cambiar tipos de datos), actualice la estructura de la base de datos física mediante **[!UICONTROL Tools > Advanced > Update database structure]** para aplicar los cambios.

**Cuando sea necesario:** Agregar campos, crear o ampliar tablas, modificar propiedades de campos, agregar o quitar vínculos, crear índices.

**Importante:** Realice primero la copia de seguridad, realice pruebas en desarrollo, planifique el tiempo de inactividad para cambios de gran tamaño, coordine con el soporte de Adobe (Managed Cloud Services), tenga en cuenta que algunos cambios pueden causar pérdida de datos.

**Práctica recomendada:** Usar el control de versiones de esquema, documentar todas las modificaciones.

[Actualizar estructura de base de datos](../dev/update-database-structure.md) | [Ampliar esquema](../dev/extend-schema.md)

+++

## Privacidad {#privacy}

Comprenda cómo Adobe Campaign le ayuda a cumplir con las regulaciones de privacidad, como el RGPD y la CCPA, y a administrar las solicitudes de los interesados.

+++ ¿Cuáles son los conceptos clave de privacidad en Campaign?

Campaign le ayuda a cumplir con las regulaciones de privacidad (RGPD, CCPA, PDPA, LGPD) a través de herramientas para administrar los derechos de los interesados, el consentimiento y la retención de datos. Los conceptos clave incluyen regulaciones de privacidad, identificación de datos personales, derechos de los interesados (acceso, eliminación, portabilidad), administración de consentimiento y políticas de retención de datos.

Como controlador de datos, es responsable de administrar las solicitudes de los sujetos de datos, mantener los registros de consentimiento y garantizar un uso transparente de los datos.

Más información sobre [Administración de privacidad](../start/privacy.md)

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

Más información sobre [Administración de privacidad](../start/privacy.md)

+++

+++ ¿Cómo recopilo y administro el consentimiento del usuario en Campaign?

Un consentimiento válido requiere un acuerdo activo, específico, informado y revocable. Los usuarios deben realizar acciones explícitas (sin casillas premarcadas ni silencio como consentimiento). Separe los consentimientos para diferentes fines (no agrupados), proporcione explicaciones claras y mantenga registros con marcas de tiempo.

**Prácticas recomendadas:** Proporcione opciones de inclusión granulares, actualice periódicamente el consentimiento, facilite el acceso a los centros de preferencias y convierta el consentimiento en marco para generar confianza.

**Implementación técnica en Campaign:**

Campaign proporciona servicios de suscripción, centros de preferencias, indicadores de exclusión y campos de consentimiento personalizados para el seguimiento del consentimiento.

* Ampliación del esquema de destinatario para campos de consentimiento (fecha, tipo, origen)
* Creación de servicios de suscripción para cada tipo de consentimiento
* Generar formularios web del centro de preferencias
* Uso de flujos de trabajo para aplicar el consentimiento en la segmentación
* Mantener pistas de auditoría

Consulte con un asesor legal para asegurarse de que su implementación cumple con los requisitos regulatorios.

**Temas relacionados:**

[Servicios de suscripción](../start/subscriptions.md) | [Privacidad y consentimiento](../start/privacy.md#consent-retention-roles) | [Administración de privacidad](../start/privacy.md)

+++

+++ ¿Qué datos se eliminan al procesar una solicitud de eliminación?

Campaign elimina automáticamente todos los datos vinculados a un interesado: perfil de destinatario, registros de envío y seguimiento, datos personalizados con relaciones de propiedad, historial de suscripciones y datos de seguimiento web.

**Cómo funciona:** Campaign elimina todos los datos donde el vínculo al destinatario tiene `integrity="own"` en la definición del esquema, lo que garantiza la eliminación en cascada en las tablas relacionadas.

Puede personalizar el ámbito de eliminación modificando la integridad del vínculo en los esquemas, pero primero consulte con un asesor jurídico. La eliminación es permanente y no se puede deshacer.

**Temas relacionados:**

[Administración de privacidad](../start/privacy.md) | [Vínculos de esquema](../dev/schemas.md)

+++

+++ ¿Las eliminaciones de privacidad afectan a mis informes de envío?

No. Los informes de campaña se basan en métricas agregadas precalculadas (total enviado, aperturas, clics), no en consultas activas de registros individuales. La eliminación de datos de destinatarios individuales no cambia las estadísticas agregadas históricas.

Las estadísticas de envío generales y las métricas de rendimiento permanecen intactas, mientras que los registros de seguimiento individuales y los detalles personales se eliminan. Esto le permite mantener los análisis de marketing respetando los derechos de los interesados.

**Temas relacionados:**

[Administración de privacidad](../start/privacy.md) | [Informes](../reporting/gs-reporting.md)

+++

+++ ¿Cómo evito volver a importar los datos eliminados?

Debe eliminar los datos de todos los sistemas de origen, no solo de Campaign. Los datos suelen proceder de sistemas externos (CRM, comercio electrónico, almacenes de datos).

**Acciones necesarias:** Identifique todas las fuentes de datos, elimine de los sistemas de origen, agregue a listas de exclusión/supresión, actualice los flujos de trabajo de importación para respetar los indicadores de eliminación y documente el proceso.

Como controlador de datos, es responsable de la eliminación completa de datos en todo el ecosistema tecnológico.

**Temas relacionados:**

[Administración de privacidad](../start/privacy.md) | [Importar flujos de trabajo](../config/workflows.md)

+++

+++ ¿Pueden los usuarios eliminados adherirse de nuevo?

Sí. Los interesados pueden volver a incluirse tras la eliminación. Campaign crea un registro de destinatario completamente nuevo sin vínculo a los datos eliminados anteriormente; el perfil comienza con una pizarra limpia.

La pista de auditoría de Campaign registra tanto el evento de eliminación como la nueva creación de perfiles, lo que demuestra que se cumple y que se muestra que la nueva opción de inclusión se proporcionó libremente después de la eliminación.

**Temas relacionados:**

[Administración de privacidad](../start/privacy.md) | [Suscripciones](../start/subscriptions.md)

+++

## ¿Todavía necesitas ayuda? {#get-help}

¿No encuentras lo que estás buscando? Estos son recursos adicionales para ayudarle a tener éxito con Adobe Campaign v8.

### Compatibilidad con la comunidad

Conéctese con otros usuarios de Campaign y con expertos en Adobe para compartir conocimientos y obtener respuestas.

* **[Comunidad de Adobe Campaign](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}**: haga preguntas, comparta soluciones y conecte con la comunidad de Campaign
* **[Foros de Experience League](https://experienceleaguecommunities.adobe.com/){target="_blank"}**: Examine los debates en todos los productos de Adobe
* **[Horario de oficina de la comunidad de Campaign](https://experienceleague.adobe.com/){target="_blank"}**: únase a las sesiones en directo con los expertos de Adobe

### Documentación y aprendizaje

Acceda a guías completas, tutoriales y materiales de formación.

* **[Tutoriales de Campaign](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=es){target="_blank"}**: guías de vídeo paso a paso y tutoriales prácticos
* **[Novedades](whats-new.md)**: características y funciones más recientes
* **[Notas de la versión](release-notes.md)** - Información de la versión actual y anterior
* **[Versiones y actualizaciones](upgrades.md)**: Obtenga información sobre las versiones de Campaign, las actualizaciones y cómo comprobar su versión

### Recursos técnicos

Encuentre documentación técnica detallada y recursos para desarrolladores.

* **[API de Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=es){target="_blank"}**: documentación de referencia de API completa
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

* **[Ayuda de Experience League](https://experienceleague.adobe.com/en/browse/campaign/campaign-v8){target="_blank"}** - Recursos de ayuda para Campaign v8 (interfaz de usuario web y consola de cliente)
* **[Servicios de aprendizaje digital de Adobe](https://learning.adobe.com/){target="_blank"}** - Cursos oficiales guiados por instructores y con ritmo personalizado
* **[Certificación Adobe Campaign](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - Valide su experiencia con certificación profesional
* **[Rutas de aprendizaje de Experience League](https://experienceleague.adobe.com/?lang=es#dashboard/learning){target="_blank"}** - recorridos de aprendizaje guiados

### Otros recursos útiles

* **[Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=es){target="_blank"}** - Referencia para usuarios de Classic v7
* **[Documentación de la interfaz de usuario web de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Nueva guía de la interfaz web
* **[Prácticas recomendadas de envío](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es){target="_blank"}** - Optimizar envío de correo electrónico

