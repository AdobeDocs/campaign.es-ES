---
title: Notas de la versión de la version 8 de Campaign de 2025 (consola)
description: Lista de funciones y mejoras incluidas en las versiones de Campaign v8 de 2025
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 784c74aaff23dbf1f35c6e8153f90610048e1c07
workflow-type: tm+mt
source-wordcount: '3063'
ht-degree: 36%

---

# Notas de la versión de 2025 {#2025-rn}

En esta página se indican las nuevas funcionalidades, mejoras y correcciones que se incluyen con la **la versión 8 de Campaign de 2025**. Para obtener la última versión, consulte [esta página](release-notes.md).

Para cualquier implementación nueva o actualización a un entorno existente, instale [la versión más reciente](release-notes.md).

>[!BEGINSHADEBOX]

**En esta página**

* [Versión 8.6.5](#release-8-6-5)
* [Versión 8.6.4](#release-8-6-4)
* [Versión 8.7.4](#release-8-7-4)
* [Versión 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## Versión 8.8.1 {#release-8-8-1}

_jueves, 09 de julio de 2025_

### Nuevas funciones {#features-8-8-1}

Lanzada anteriormente para un pequeño conjunto de clientes, la siguiente funcionalidad ya está disponible para todos los entornos de FDA de Campaign:

* **Nuevo conector de envío de SMS**: el conector de envío de SMS se ha modernizado y mejorado para habilitar conexiones SMPP en modo transceptor, habilitar conexiones SMPP persistentes y garantizar una mejor compatibilidad. Ya está disponible una nueva cuenta externa de SMS para todas las implementaciones de SMS nuevas. Las implementaciones existentes siguen siendo compatibles, pero se recomienda pasar a este nuevo conector moderno y extendido. Póngase en contacto con Adobe si desea realizar la transición al nuevo conector. [Más información](../send/sms/sms.md)

  >[!NOTE]
  >
  >Esta característica es **no** disponible para [implementaciones de FDAC de Campaign](../architecture/enterprise-deployment.md).

<!-- (from ACC rn, aleady in the product, to remove?) -->

<!-- * **Enrichment in transactional messages** (to remove?) -->

<!--
* **Multilingual delivery creation** in the Web UI - You can now send multiple email deliveries in different languages in Adobe Campaign Web User Interface. The Multilingual delivery feature allows you to choose the default language of your delivery as well as the different languages in which the delivery can be sent. You can also preview these deliveries in the languages you have chosen. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html?lang=es)

ACC - Multilingual deliveries - Starting Campaign Web User interface April release, you will be able to send multiple email deliveries in different languages, and access the related dynamic reports. This capability will only be available in Adobe Campaign Web User Interface at the end of April, and require a server update to Campaign v8.7.4.
-->

<!--
*  **Visual fragments** in the Web UI - You can now create, use and archive content fragments. Visual fragments are pre-defined visual blocks that you can reuse across multiple email deliveries, or in content templates. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments.html?lang=es){target="_blank"}

(already available in console and web, to remove?) 
web - * Visual fragments - You can now archive visual content fragments. Learn more
-->

<!--
* **Delivery alerting** in the Web UI - The Delivery alerting feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html?lang=es){target="_blank"}
-->

<!--
* **Landing pages improvements**  in the Web UI- The following improvements to landing pages are now available:

    * You can now reference a default subscription/unsubscription landing page when configuring a service. When designing an email, if you define a link to that landing page, users submitting the landing page form are automatically subscribed to or unsubscribed from this service. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/work-with-services/manage-services.html?lang=es#create-service){target="_blank"}
    * A new option in the landing page configuration allows anonymous visitors to access the landing page. If you unselect this option, only identified users can access and submit the form. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=es#create-landing-page){target="_blank"}
    * A new option in the landing page configuration allows to store additional internal data when the landing page is being submitted. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=es#create-landing-page){target="_blank"}
    * A new option enables to use a landing page for several services, making it dynamic. When adding a link to an email, if you select a dynamic landing page, you can select any service. If you select a landing page that has a specific service associated, this service will be automatically used (you cannot select another one). [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=es#define-actions-on-form-submission){target="_blank"}
    * Conditional content is now supported in landing pages. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html?lang=es){target="_blank"}
    * You can link a landing page to a service, and send a confirmation message when users validate it. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html?lang=es#lp-message){target="_blank"}
    * You can add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html?lang=es#captcha){target="_blank"}

web - * **Subscriptions with Landing pages** - You can now link a landing page to a service, and send a confirmation message when users validate it. [Learn more](../landing-pages/lp-content.md#lp-message){target="_blank"}.
Web - * **Captcha in landing pages** - You can now add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](../landing-pages/create-lp.md#captcha)
-->

<!--
* (from ACC rn, already in product, to remove?) **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 
ACC * Rich Push Notification templates - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. Read more.
-->

Publicada anteriormente en Disponibilidad limitada, la siguiente funcionalidad ya está disponible **bajo demanda**:

<!--
* **Dynamic Reporting** - You can now access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Dynamic reporting is also available for multilingual email deliveries and transactional messages. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=es){target="_blank"}

ACC **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/es/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}
ACC - Dynamic Reporting - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Read more
* **Dynamic Reporting for Multilingual** - Dynamic reporting is now available for multilingual email deliveries. For more information, refer to the [detailed documentation](../reporting/global-reports.md).
-->

* **API de REST**: ahora puede usar las API de REST para crear integraciones para Adobe Campaign y construir su propio ecosistema al interconectar Adobe Campaign con el panel de tecnologías que usa. La API de REST de mensajería transaccional también está disponible para el canal SMS. Cuando el correo electrónico como el teléfono móvil están presentes en la carga útil, puede utilizar el campo &quot;wishedChannel&quot; para especificar el canal. Si no se proporciona, el correo electrónico se utilizará de forma predeterminada a menos que wishedChannel solicite explícitamente un SMS. Las API transaccionales basadas en eventos también están disponibles para los correos electrónicos. [Más información](../dev/api/get-started-apis.md)

  >[!NOTE]
  >
  >Esta característica es **no** disponible para [implementaciones de FDAC de Campaign](../architecture/enterprise-deployment.md).

<!--
ACC - Rest APIs - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. Read more
* **SMS REST API support (LA)** - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. For more information, refer to the [detailed documentation](https://experienceleague.adobe.com/es/docs/experience-cloud/campaign/apis/managing-transactional-messages){target=_blank}.
ACC - SMS REST API support - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS.
ACC * **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/es/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}
-->

Además de las funciones enumeradas anteriormente, esta versión también incluye un conjunto de funcionalidades disponibles con la interfaz de usuario web de Campaign:

* [Creación de envíos multilingües](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html?lang=es#multilingual-delivery){target="_blank"}
* [Alertas de envío](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html?lang=es){target="_blank"}
* [Mejoras en las páginas de aterrizaje](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/get-started-lp.html?lang=es){target="_blank"}
* [Informes dinámicos](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=es){target="_blank"} (bajo demanda)
* [Promoción centralizada de marca](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html?lang=es){target="_blank"} (bajo demanda, nuevas implementaciones)

Consulte las [notas de la versión](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=es){target="_blank"} de la IU web de Campaign

### Mejoras generales {#improvements-8-8-1}

* Microsoft Fabrics ahora se admite como base de datos externa con Adobe Campaign Federated Data Access (FDA). [Más información](../config/external-accounts.md#transfer-data-external-accounts)
* La versión 8 de Campaign ahora es compatible con Android 15 y iOS 18 para las notificaciones push. [Más información](../start/compatibility-matrix.md#MobileSDK)
* Ahora se admiten bases de datos en la nube además de las bases de datos locales para el túnel de red privada virtual segura. [Más información](../config/enhanced-security.md#vpn-databases)
* Se ha añadido un nuevo conjunto de campos &quot;ID de proveedor&quot; en la sección &quot;Tráfico entrante&quot; del conector SMS 2.0. [Más información](../send/sms/smpp-external-account.md#incoming-traffic)
* Los destinatarios que cancelen su suscripción mediante el método &quot;mailto&quot; List-Unsubscribe ya no se envían a cuarentena. Se dan de baja del servicio asociado a la entrega o se envían a la lista de bloqueados de la (sección &quot;Ya no se puede contactar&quot; del perfil) si no se ha definido ningún servicio para la entrega. [Más información](../send/quarantines.md)
* Ya está disponible en la consola del cliente de Adobe Campaign una versión renovada del informe de renderización de la bandeja de entrada.
* El archivo `setup-client.exe` se ha reemplazado con un archivo `ac-client.msi`, lo que proporciona un método más sencillo para que los administradores realicen actualizaciones masivas sin que sea necesaria la intervención del usuario.

### Correcciones {#fixes-8-8-1}

* Se ha corregido un problema por el cual no se recibían respuestas automáticas debido a un periodo de validez no válido en SMS 2.0. Esto garantiza la entrega de mensajes adecuada después de la migración. (NEO-88088)
* Se ha resuelto un problema en SMS 2.0 en el cual algunos campos de la tabla `inSms` no se actualizaban correctamente, lo que garantizaba la inserción precisa de datos para las funcionalidades de SMS. (NEO-87906)
<!--
* NOOOO Addressed delivery preparation failures for IndiGo Aviation after upgrading to v7.4.2. This fix resolves personalization and deduplication-related errors, enabling smooth delivery workflows. (NEO-87693)
* NOOOO Corrected Redshift database function definitions in version 8.6.4, ensuring proper execution of functions like `AddDays`, `AddHours`, `AddMinutes`, and `AddSeconds`. (NEO-87305)
* Provided a silent installation mechanism for the client console to facilitate mass upgrades without user intervention. This resolves challenges with manual installations. (NEO-69772)
-->
* Se han corregido errores en el flujo de trabajo de limpieza de base de datos debido a referencias de columna incorrectas o que faltaban en consultas SQL. Esto garantiza la depuración adecuada de los registros y los datos de los visitantes. (NEO-86813)
* Se ha resuelto un problema en el cual faltaban fechas de evento en los registros de envío. Esta corrección garantiza una población de fechas de evento precisa, fundamental para los déclencheur y flujos de trabajo programados. (NEO-86708)
* Se corrigieron los problemas de inserción del registro de envío de SMS en SMS 2.0, lo que garantiza el registro adecuado en la tabla `nmsBroadLogMid`. (NEO-86556)
* Se han resuelto problemas de extracción de archivos con el modo de envío externo en plantillas de correo postal, lo que garantiza la compatibilidad y la funcionalidad. (NEO-86520)
* Se han resuelto problemas de procesamiento de entregas que implicaban un enrutamiento dividido en varias instancias de MID, lo que garantiza actualizaciones de estado de entrega y rendimiento precisos. (NEO-86500)
* Se han corregido los datos de seguimiento que faltaban en los informes dinámicos posteriores a la migración de Campaign Standard a Campaign v8, lo que garantiza unos informes precisos para los registros de seguimiento de entregas. (NEO-86419)
* Se ha resuelto un flujo de trabajo que activaba problemas en los que los flujos de trabajo se ejecutaban dos veces, lo que provocaba violaciones de clave duplicada. Esta corrección garantiza la correcta gestión y ejecución de los eventos. (NEO-86154)
* Se corrigieron problemas de compatibilidad con las funciones SQL de Redshift OOTB después de la implementación, lo que garantiza la ejecución adecuada de funciones como `GetDate()` en los flujos de trabajo. (NEO-85834)
* Se han resuelto problemas de procesamiento en compilaciones de correo electrónico en las que las imágenes desaparecían cuando se adjuntaban direcciones URL. Esta corrección garantiza la visualización adecuada de la imagen en las vistas previas de la bandeja de entrada. (NEO-85716)
* Se ha corregido la representación de comillas de cierre rizado en la interfaz de usuario web, lo que garantiza la visualización precisa de los caracteres en las entregas de correo electrónico. (NEO-85687)
* Se ha corregido la funcionalidad de vínculo de página espejo, lo que garantiza la navegación adecuada entre las variantes de idioma dentro de las páginas espejo. (NEO-85625)
* Se han resuelto problemas de formato de fecha en los selectores de fecha de la aplicación web, lo que garantiza la compatibilidad con los formatos de fecha japoneses (`yyyy-mm-dd`). (NEO-85234)
* Se corrigieron problemas del flujo de trabajo posterior al procesamiento con configuraciones de enrutamiento alternativas en intermediario, lo que garantiza la ejecución adecuada del flujo de trabajo. (NEO-85111)
* Se ha mejorado el rendimiento del envío de Android al utilizar olas, lo que garantiza que las partes del envío se procesen en el orden correcto según la programación. (NEO-84324)
* Se corrigieron errores de preparación de envíos debido a errores de procesamiento nulos en la función `to_varchar`, lo que garantiza inicios de campaña sin problemas. (NEO-84108)
* Se han resuelto problemas de conexión SFTP provocados por versiones `libcurl` y `libssh2` obsoletas, lo que garantiza la compatibilidad con servidores SFTP alojados en Azure. (NEO-84038)
* Se han corregido problemas del conector FDA de Snowflake que implicaban errores de autenticación de par de claves, lo que garantiza conexiones de base de datos correctas. (NEO-84024)
* Se han resuelto problemas de funcionalidad de reglas de tipología, lo que garantiza la correcta aplicación de las reglas de presión en las entregas PUSH. (NEO-84010)
* Se han resuelto los errores de consulta de BigQuery causados por comparaciones de fechas y marcas de hora no coincidentes después de la actualización, lo que garantiza la compatibilidad con las condiciones de filtrado. (NEO-83826)
* Se ha resuelto un problema en el cual las actividades de entrega fallaban al reanudar las entregas en pausa debido a errores de personalización. Esta corrección garantiza flujos de trabajo de envío más suaves y evita errores relacionados con actividades en pausa. (NEO-83809)
* Se corrigió un problema en FDAC al utilizar la opción &quot;consulta de carga de registro de destinatario&quot;. Se ha agregado compatibilidad con las cláusulas &quot;order by&quot; y &quot;where&quot;. (NEO-83793)
* Se han corregido errores de entrega recurrentes causados por valores nulos que se escribían en columnas que no admitían valores nulos en la tabla broadLogRcp. Esta corrección mejora la fiabilidad de la entrega y evita errores durante las campañas en directo. (NEO-83729)
* Se ha resuelto un problema en el cual las direcciones semilla se duplicaban durante la preparación de la entrega, lo que producía discrepancias en los recuentos de mensajes. Esta corrección garantiza un direccionamiento preciso y evita errores de duplicación. (NEO-83703)
* Se ha corregido un problema crítico por el que los envíos de producción se enviaban después de su periodo de validez, lo que podía causar problemas legales. Los envíos ahora respetan estrictamente los períodos de validez definidos. (NEO-83350)
* Se ha corregido un problema de espacio que se producía al cargar volúmenes de datos grandes en tablas de Teradata. Esta corrección optimiza el procesamiento de datos y resuelve errores intermitentes en entornos de producción. (NEO-83252)
* Se ha resuelto un error de flujo de trabajo técnico relacionado con los errores SendMetricsToNewRelic, que provocaban retrasos en el procesamiento de eventos RT. Esta corrección garantiza una ejecución más suave del flujo de trabajo y evita los retrasos de eventos. (NEO-83143)
* Se ha corregido un error en el flujo de trabajo de limpieza de base de datos debido a problemas de conversión de ID a UUID en instancias de interacción de FDAC. Esta actualización garantiza las operaciones de limpieza adecuadas y reduce la carga del sistema. (NEO-83138)
* Se han resuelto errores de entrega causados por restricciones en las longitudes de nombres internos de los miembros semilla. Esta corrección permite nombres internos más largos sin afectar a la personalización de la entrega. (NEO-83044)
* Se ha corregido un problema por el cual los envíos se quedaban atascados en la personalización pendiente debido a errores aleatorios. Esta actualización garantiza procesos de personalización más suaves y una ejecución de envíos fiable. (NEO-82781)
* Se ha corregido un problema en el cual las propuestas de ofertas no se podían revisar en la consola debido a errores y lentitud de API. Esta corrección mejora la capacidad de respuesta de la interfaz de usuario y garantiza la correcta funcionalidad de la oferta. (NEO-82742)
* Se han resuelto bloqueos intermitentes en la consola de Adobe Campaign al utilizar objetos de envío personalizados. Esta corrección garantiza estabilidad y fiabilidad al trabajar con flujos de trabajo personalizados. (NEO-82675)
* Se han corregido errores de flujo de trabajo y procesamiento lento notificados tras la migración de la versión 7 a la 8. Esta actualización optimiza los flujos de trabajo de la campaña y garantiza una ejecución oportuna. (NEO-82665)

<!--
* Resolved an issue where sysfilters were generating incorrect SQL queries after upgrading to v8.6.3. This fix ensures proper query generation and restores sysfilter functionality. (NEO-82591)
-->

* Se ha corregido un problema crítico en el que los procesos secundarios de MTA se atascaban y bloqueaban los envíos push y WhatsApp. Esta actualización garantiza flujos de trabajo de comunicación más fluidos y evita cuellos de botella en la entrega. (NEO-82351)
* Se ha corregido un problema de migración de datos en el que los campos de cadena de las tablas GCP provocaban errores durante las actualizaciones en Teradata. Esta corrección elimina la necesidad de buscar soluciones alternativas y mejora la eficacia del flujo de trabajo. (NEO-82260)
* Se ha actualizado la lógica de limpieza de bases de datos para tener en cuenta las bases de datos principales en instancias de FDAC, lo que evita intentos innecesarios de purgar tablas inexistentes. Esta corrección optimiza las operaciones de limpieza. (NEO-81879)
* Se han resuelto bloqueos de consola causados por el uso de subflujos de trabajo en combinación con campos de enumeración. Esta corrección garantiza la estabilidad al trabajar con flujos de trabajo enriquecidos. (NEO-81864)
* Se corrigió un problema en el cual los campos de subafinidad en las asignaciones de destino se modificaban incorrectamente después de la duplicación de envíos, lo que provocaba errores de flujo de trabajo. Esta actualización garantiza valores de subafinidad coherentes. (NEO-81809)
* Se ha agregado compatibilidad con caracteres comodín en las actividades de transferencia de archivos de Adobe Campaign Classic v8, lo que permite a los usuarios cargar archivos con nombres dinámicos (por ejemplo, `abc_*`) en los flujos de trabajo. (NEO-81758)
* Se ha introducido una opción para habilitar el indicador `content-available` en las notificaciones push de iOS para Adobe Campaign Classic v8. Esta mejora permite a las aplicaciones móviles almacenar notificaciones en la bandeja de entrada y admite actualizaciones en segundo plano, lo que soluciona problemas de descartes de entregas causados por limitaciones de APNS. (NEO-81721)

<!--
* Updated the Campaign 7.4.1 release upgrade process to require manual installation of dependencies. Documentation has been provided to guide users on installing required libraries such as `epel-release`, `java-11-openjdk-headless`, and others. (NEO-81433)
-->

* Se ha añadido una opción de configuración de tiempo de espera para conexiones BigQuery en Adobe Campaign Classic v8. Esta mejora permite a los usuarios ajustar el periodo de tiempo de espera para las consultas, resolviendo problemas con errores de consulta debido a los límites de tiempo de espera predeterminados. (NEO-81222)
* Se ha corregido un problema intermitente por el que las direcciones URL de la página espejo fallaban en los envíos enviados mediante cuentas externas de enrutamiento divididas y alternativas después de la migración a v8. Las partes de envío subyacentes ahora se copian correctamente en `mirrorPageInfo`. (NEO-81105)

<!--
* Resolved an authentication failure issue with inMail caused by token expiration. Restarting the `nlserver` process now resolves the error. (NEO-80683)
-->

* Se corrigió el botón &quot;Acceder a la nueva interfaz de usuario web&quot; en la consola del cliente para que apunte a la dirección URL correcta (`https://experience.adobe.com`) para las instancias de producción. Esto resuelve los problemas con las direcciones URL no válidas en los entornos de producción. (NEO-80673)
* Se ha corregido un problema en la actividad División por el cual el uso de Ordenación y Tamaño (como porcentaje del segmento) causaba errores de SQL. La funcionalidad ahora funciona correctamente. (NEO-80432)
* Se corrigió un problema de bloqueo en flujos de trabajo que usaban `CCurlAzureBlobStorage::UploadStream`. Los flujos de trabajo ahora se ejecutan sin errores de segmentación durante las cargas del almacenamiento del blob de Azure. (NEO-79598)
* Se ha resuelto un problema en el cual las páginas espejo no se podían ver desde la consola del cliente en entornos de producción. Los vínculos de página espejo ahora funcionan correctamente tanto en las vistas de correo electrónico como de consola. (NEO-78946)
* Se ha corregido un problema con el registro de envíos en el que algunos registros se marcaban incorrectamente como &quot;Envío cancelado&quot; a pesar de que la entrega del mensaje se había realizado correctamente. Se ha abordado la causa raíz relacionada con las discrepancias de fecha de contacto y fecha de evento. (NEO-78933)
* Se ha actualizado la biblioteca `com.google.code.gson:gson` para mejorar la seguridad. (NEO-78299)
* Se han resuelto errores de restricción de clave duplicada en los registros de conexión de FDA (`nmsconnectionlogs`) que ocasionaban errores en el flujo de trabajo. La lógica de inserción se ha ajustado para evitar ID duplicados. (NEO-78050)
* Se ha corregido un problema por el cual las direcciones de correo electrónico en cuarentena se marcaban incorrectamente como móviles en la tabla de direcciones, lo que provocaba errores de análisis de entregas. Se ha corregido la lógica de reconciliación entre los objetos de envío. (NEO-76986)
* Se corrigió un error de preparación de envíos al utilizar grupos de control con una base de datos de Oracle. La generación de consultas SQL se ha corregido para garantizar la compatibilidad con las bases de datos de Oracle. (NEO-76947)
* Se han resuelto errores de entrega causados por la creación simultánea de carpetas durante las transiciones del nuevo mes. La lógica de creación de la carpeta de envíos se ha ajustado para evitar violaciones de clave duplicadas. (NEO-76824)
* Se han corregido problemas de conversión de huso horario incoherentes en cuentas externas de Teradata. Las marcas de tiempo mostradas ahora se alinean correctamente con la configuración de zona horaria configurada. (NEO-76716)
* Flujos de trabajo de limpieza de bases de datos mejorados para gestionar conjuntos de datos grandes de forma eficaz. Se ha implementado un nuevo método que utiliza ID de fila y variables de enlace para optimizar el rendimiento de la eliminación. (NEO-76439)
* Se ha resuelto un problema en el cual los envíos externos con el canal &quot;Otro&quot; no generaban archivos de salida. Las propiedades de entrega ahora incluyen correctamente la ruta de archivo de los archivos generados. (NEO-75962)
* Se corrigieron errores en el flujo de trabajo `ffdaReplicateStagingData` causados por actualizaciones de datos grandes. La configuración de tiempo de espera y la administración del tamaño de la tabla se han optimizado para evitar errores en el flujo de trabajo. (NEO-75643)
* Se ha corregido un problema en el cual la previsualización de archivos de salida de correo postal provocaba que los paneles se volvieran vacíos. El tablero ahora se muestra correctamente después de las vistas previas de archivos. (NEO-75359)
* Indicadores de seguimiento mejorados para que las notificaciones push incluyan clics y aperturas. Los indicadores como `@recipientClick`, `@personClick` y `@totalRecipientClick` ahora contabilizan clics en notificaciones móviles. (NEO-75240)
* Se han corregido errores en los flujos de trabajo de limpieza para entregas con estados externos pendientes de cancelación. Se ha corregido la lógica de recuperación de registros de la base de datos. (NEO-74833)
* Se ha resuelto un problema de discrepancia de zona horaria en Rusia (UTC+3:00 Moscú) donde `nlserver` horas de salida eran incorrectas. Se ha actualizado la lógica de sincronización horaria. (NEO-74754)
* Se corrigieron errores en el flujo de trabajo `defaultMidSourcingDlvStat` causados por sintaxis SQL incorrecta para bases de datos MSSQL. La lógica de generación de consultas se ha ajustado por compatibilidad. (NEO-74156)
* Se han corregido varios bloqueos en el proceso web. (NEO-73174)
* Se ha corregido un problema con las consultas BigQuery que fallaban cuando los apóstrofos estaban presentes en las condiciones. La lógica de gestión de consultas se ha actualizado para interpretar correctamente los caracteres especiales. (NEO-72547)
* Se ha resuelto un problema en el cual las reglas de tipología con filtros de exclusión no funcionaban correctamente. Se ha corregido la generación de consultas SQL para la preparación de envíos. (NEO-72292)
* Se han corregido discrepancias en las fechas de evento y las fechas de contacto para la administración de devoluciones. Se ha mejorado la lógica de administración de huso horario. (NEO-72277)
* Tratamiento mejorado de caracteres UTF-8 convertidos incorrectamente en envíos de correo directo. Los caracteres ocultos ahora se procesan correctamente para evitar errores de entrega. (NEO-72148)
* Se han corregido errores en la actividad de Inbound SMS donde los filtros causaban problemas de guardado. El flujo de trabajo ahora se guarda correctamente sin generar errores. (NEO-70427)
* Se corrigió la generación de consultas SQL para criterios de idoneidad agrupados en los espacios de oferta. Se han agregado los paréntesis que faltan en las condiciones SQL para garantizar un filtrado adecuado. (NEO-70425)

<!--
* Updated the public documentation link in the `ffdaUnicity` workflow email template to point to the correct page for key management in v8. (NEO-67996)
-->

* Se han corregido errores intermitentes en los flujos de trabajo de carga de datos de BigQuery causados por problemas de contenido HTTP o codificación de transferencia. Se ha mejorado la lógica de administración de conexiones. (NEO-66989)

## Versión 8.6.5 {#release-8-6-5}

_25 de abril de 2025_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA).

### Nuevas funciones {#features-8-6-5}

**Nuevo conector de envío de SMS**: el conector de envío de SMS se ha modernizado y mejorado para habilitar conexiones SMPP en modo transceptor, habilitar conexiones SMPP persistentes y garantizar una mejor compatibilidad para entornos que realizan la transición desde Adobe Campaign Standard. Ya está disponible una nueva cuenta externa de SMS para todas las implementaciones de SMS nuevas. Las implementaciones existentes siguen siendo compatibles, pero se recomienda pasar a este nuevo conector moderno y ampliado. [Más información](../send/sms/sms.md).

### Mejoras generales {#improvements-8-6-5}

* Se ha mejorado el rendimiento global de la aplicación, en el contexto de una implementación empresarial (FDAC), incluyendo el envío de pruebas de entrega y la limpieza de la base de datos.

* Para aumentar la seguridad de todas las comunicaciones entre aplicaciones, mTLS se admite ahora para llamadas de API externas.

* Agente de transferencia de correo (MTA): se ha corregido que un elemento secundario de MTA huérfano quede bloqueado en estado **[!UICONTROL Start pending]**.

### Correcciones {#fixes-8-6-5}

En esta versión, también se han corregido los siguientes problemas:

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Versión 8.7.4 {#release-8-7-4}

_10 de abril de 2025_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario de Campaign Standard que está realizando la transición a la versión 8 de Campaign, obtenga más información sobre esta transición en la [documentación de la interfaz de usuario web de la versión 8 de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuevas funciones {#features-8-7-4}

* **Compatibilidad con la API REST de SMS**: la API REST de mensajería transaccional ya está disponible para el canal de SMS. Cuando el correo electrónico como el teléfono móvil están presentes en la carga útil, puede utilizar el campo “wishedChannel” para especificar el canal. Si no se proporciona, se utiliza de forma predeterminada el correo electrónico, a menos que wishedChannel solicite explícitamente un SMS.

* **Envíos multilingües**: a partir de la versión de abril de la interfaz de usuario web de Campaign, podrá realizar varios envíos de correo electrónico en diferentes idiomas y acceder a los informes dinámicos relacionados. Esta funcionalidad solo estará disponible en la interfaz de usuario web de Adobe Campaign a finales de abril y requiere una actualización del servidor a la versión 8.7.4 de Campaign.

### Correcciones {#fixes-8-7-4}

En esta versión se han solucionado los siguientes problemas:

NEO-80245, NEO-83559

## Versión 8.7.3 {#release-8-7-3}

_14 de febrero de 2025_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario de Campaign Standard que está realizando la transición a la versión 8 de Campaign, obtenga más información sobre esta transición en la [documentación de la interfaz de usuario web de la versión 8 de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuevas funciones {#features-8-7-3}

* **Informes dinámicos para mensajes transaccionales**: ahora puede supervisar los mensajes transaccionales en la interfaz de usuario de informes dinámicos. Estos informes permiten al experto en marketing ver todas las métricas y dimensiones de informes de los mensajes transaccionales, así como el desglose de envíos realizados a través de una plantilla en tiempo real. [Más información](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=es){target="_blank"}

* **API REST de mensajería transaccional**: las API transaccionales basadas en eventos ya están disponibles para los correos electrónicos. [Más información](../dev/api/get-started-apis.md)

### Correcciones {#fixes-8-7-3}

En esta versión se han solucionado los siguientes problemas:

NEO-79373, NEO-81908, NEO-83081

## Versión 8.6.4 {#release-8-6-4}

_15 de enero de 2025_

### Mejoras generales {#improvements-8-6-4}

* La estabilidad de la aplicación de Campaign se ha mejorado durante el análisis del envío en el contexto de una [implementación empresarial (FDAC)](../../v8/architecture/enterprise-deployment.md).
* Esta versión incorpora mecanismos de arquitectura de FDAC mejorados y reforzados, incluida la administración de claves, el ensayo y la replicación de datos.
* Se han introducido nuevos flujos de trabajo técnicos para la [implementación empresarial (FDAC)](../../v8/architecture/enterprise-deployment.md). Estos flujos de trabajo replican el envío y los datos relacionados centralizando las solicitudes de replicación paralelas en las tablas correspondientes. Estos flujos de trabajo comienzan con `Replicate nms`. [Más información](../architecture/replication.md)
* Ahora hay disponible una nueva opción **Habilitar el supervisor de vigilancia para mantener el flujo de trabajo en ejecución de forma permanente** en las propiedades del flujo de trabajo. Cuando esta opción está habilitada, los flujos de trabajo se reinician automáticamente si se produce un error. De forma predeterminada, el reinicio se produce cada 30 segundos si el flujo de trabajo sigue dando error. Para ajustar este intervalo, puede crear una nueva opción `XtkWorkflow_WatchdogRestartTimerTimeout` y establecer un tipo de datos Integer para especificar el nuevo retraso. Esta opción solo debe habilitarse en flujos de trabajo técnicos. [Más información](../../automation/workflow/workflow-properties.md#execution)

### Mejoras de seguridad {#security-8-6-4}

La conexión con las soluciones y aplicaciones de Adobe a través de la cuenta externa de **[!UICONTROL Adobe Experience Cloud]** se ha actualizado para reforzar la seguridad.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Actualizaciones de compatibilidad {#comp-8-6-4}

Se han añadido los siguientes conectores FDA. Consulte [esta página](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks ahora se admite como base de datos externa con acceso de datos federado (FDA) de Adobe Campaign.

* Ya está disponible el nuevo conector ODBC de Amazon Redshift FDA. Ofrece una conectividad mejorada, un mantenimiento más sencillo y una compatibilidad mejorada. Esta nueva versión incorpora las siguientes mejoras:

   * El nuevo conector se basa en la interfaz ODBC, que se alinea con los conectores FDA más recientes. Esto garantiza una asistencia a largo plazo.
   * También introduce un nuevo mecanismo de carga de datos mediante compartimentos s3, lo que mejora significativamente el rendimiento.

  El conector heredado aún se puede utilizar. Si desea probar el nuevo, póngase en contacto con su representante de Adobe.

### Correcciones {#fixes-8-6-4}

En esta versión se han solucionado los siguientes problemas:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

