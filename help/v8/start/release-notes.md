---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
TQID: https://experienceleague.adobe.com/Zdo52RLQFbxlRNgE54yLDn3yAMmmOqxKyRhnCJa0Xwg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ffeb9430b382b598af412555b1b0a6ff42bc68d0
workflow-type: tm+mt
source-wordcount: 1747
ht-degree: 6%

---

# Últimas versiones {#latest-release}

En esta página se indican las nuevas funciones, mejoras y correcciones que se incluyen con las **últimas versiones** de la versión 8 de Campaign (consola). Obtenga más información sobre las versiones y actualizaciones de Campaign en [esta página](upgrades.md). Otras versiones se indican en la sección Versiones anteriores de esta documentación.

## Versión 8.9.2 {#release-8-9-2}

>[!CAUTION]
>
> La actualización de la consola de cliente es obligatoria. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).

_3 de mayo de 2026_

### Mejoras de seguridad {#security-8-9-2}

* Para mantener una seguridad, estabilidad y conformidad óptimas, todas las instancias se han actualizado a Debian 13 y PostgreSQL 17.

### Correcciones {#fixes-8-9-2}

>[!NOTE]
>
> Las correcciones enumeradas a continuación se han implementado progresivamente en versiones sucesivas de 8.9.2. Vaya al **[!UICONTROL Help > About...]** [menú](upgrades.md#version) para comprobar que dispone de la última versión de 8.9.2 (11d1c68). Póngase en contacto con su representante de Adobe para obtener más información.

* Se ha corregido un problema por el cual las fechas de los eventos en eventos transaccionales se configuraban incorrectamente debido a un problema de conversión de tipo de datos, lo que provocaba fechas incorrectas en el sistema de informes dinámico. (NEO-93923)
* Se ha corregido un problema por el cual las notificaciones push silenciosas de Android y iOS fallaban durante la preparación de la entrega cuando los campos de título y cuerpo estaban vacíos. (NEO-93739)
* Se ha corregido un problema que impedía que el campo de idioma se capturara para tokens de registro de aplicaciones de Android debido a claves de reconciliación incorrectas. (NEO-93100)
* Se ha corregido un problema en el cual la preparación de la entrega fallaba al aplicar reglas de tipología personalizadas con reglas de presión. (NEO-94457)
* Se ha corregido un problema en el cual la consola del cliente podía experimentar errores de procesamiento de solicitudes HTTP. (NEO-94071)

<!-- BUILD 8.9.2.9829.9669833 -->

* La supervisión de FDA ahora está deshabilitada de forma predeterminada para evitar errores de inserción del registro de conexión. (NEO-94841)
* Se ha corregido un problema en el cual las llamadas de interacción de SOAP utilizadas para el canje de ofertas podían fallar con un error de resolución de área de nombres. (NEO-94787)
<!-- infra * Fixed an issue where Snowflake connections using private key authentication could fail on ARM64 architectures. (NEO-94350) -->
* Se corrigió un problema en el cual los campos de cadena con longitud 1 podrían causar errores de SQL en las tablas temporales de flujo de trabajo en PostgreSQL 17. (NEO-94487)
<!-- linked to previous build * Fixed an issue where the server could fail to restart after a Debian 13 build upgrade due to a missing dependency. (NEO-94598) -->

<!-- BUILD 8.9.2.9829.c90aa36 -->

* Se corrigió un problema en el cual la opción **Mostrar página espejo** en la consola del cliente y la interfaz de usuario web podría devolver un error de &quot;Página espejo incorrecta&quot;. (NEO-93303)

<!-- BUILD 8.9.2.9830.4a6f868 -->

* Se ha corregido un problema en el cual el flujo de trabajo técnico predeterminado **Tracking** podía fallar después de la instalación de un paquete multivariable en implementaciones de FDAC. (NEO-94972)
* Se ha corregido un problema en el cual la preparación de la entrega podría no agregar ningún destinatario al objetivo cuando la plantilla de entrega utilizaba una fórmula de peso que hacía referencia a la entrega actual. (NEO-94892)
<!-- hotfix -->
* Se ha corregido un problema en el cual los enriquecimientos de flujo de trabajo mediante uniones en dos vínculos 1-N consecutivos podían fallar con errores SQL después de una actualización. (NEO-94893)

<!-- BUILD 8.9.2.9831.f53d3d2 -->

* Se ha corregido un problema en la canalización de correo electrónico que podría provocar un consumo excesivo de memoria a lo largo del tiempo. (NEO-95088)
* Se ha corregido un problema en el cual la regla de tipología de correo electrónico en conflicto podía excluir incorrectamente los destinatarios no duplicados de un destino de entrega cuando se utilizaban direcciones semilla o de prueba. (NEO-95026)
* Se ha corregido un problema en el cual el flujo de trabajo técnico predeterminado de **Notificación de oferta** podía fallar después de una actualización. (NEO-95064)
* Se ha mejorado el proceso de instalación del paquete multivariable para evitar el seguimiento de los errores del flujo de trabajo durante las actualizaciones de la compilación. (NEO-95018)

<!-- BUILD 8.9.2.9831.11d1c68 -->

* Se ha corregido un problema que podía provocar que el servidor se bloqueara repetidamente, lo que provocaba interrupciones en la instancia. (NEO-95304)
* Se ha corregido un problema en el cual los vínculos de seguimiento y de página espejo no podían cargar los envíos. (NEO-95239)
* Se ha corregido un problema que podría provocar un bucle de redireccionamiento al iniciar sesión en aplicaciones web de Campaign protegidas con el inicio de sesión único de IMS. (NEO-95188)
* Se ha corregido un problema en el cual la fecha de creación de la entrega faltaba en los archivos de extracción de la entrega después de guardar la entrega. (NEO-95010)
* Se corrigió un problema en el cual los flujos de trabajo secundarios generados en gran volumen podían permanecer atascados en el estado **En proceso de edición**, lo que reducía la capacidad del flujo de trabajo transaccional. (NEO-95131)
* Se ha corregido un problema en el cual la actividad **Leer lista** podía sobrescribir plantillas de lista predefinidas con estructuras de lista generadas por el flujo de trabajo, lo que provocaba errores en los flujos de trabajo descendentes. (NEO-95103)
* Se ha corregido un problema en el cual la administración de comentarios de notificaciones push podía provocar que el servidor se bloqueara al procesar envíos de gran volumen. (NEO-95150)
* Se corrigió un problema en el cual al abrir la pestaña **Data** en el esquema `xtk:workflow` en el explorador de esquemas se podía almacenar en déclencheur un mensaje de error. (NEO-94923)
<!-- hotfixes -->
* Se ha corregido un problema en el cual la actividad **Enrichment** ya no podía recuperar atributos de salida de actividades **Subworkflow** de flujo ascendente, lo que provocaba que fallaran los flujos de trabajo. (NEO-95151)
* Se ha corregido un problema de ingesta de datos de seguimiento que podía impedir las actualizaciones de estado de entrega y bloquear el procesamiento descendente de mensajes. (NEO-94666)
* Se ha corregido un problema en el cual ciertas acciones de la consola del cliente relacionadas con las propuestas de ofertas podían almacenar en déclencheur consultas de larga ejecución en bases de datos de Snowflake, lo que provocaba bloqueos y lentitud. (NEO-92936)
* Se ha corregido un problema que impedía configurar las opciones personalizadas para almacenar claves cifradas en cuentas externas de Snowflake. (NEO-93302)

<!-- 
Internal/non-customer-facing:
* Internal test automation task added to cover NEO-94893. (NEO-94990) — autotest only
Customer-specific hotfixes:
* Fixed an issue affecting WhatsApp delivery preparation. (NEO-92480) — HeroMotoCorp only
* Added a feature-flagged optimization to use dynamic shared memory in Customer Targeting Audience (CTA) processing. (NEO-93542) — DerTour only
* Fixed an issue where the delivery alerting workflow could fire incorrect "long start pending" notifications even when deliveries were sent within the configured threshold. (NEO-93434) — non-ZDT hotfix, NORC only
* Added a new parameter in the mobile SDK to allow identification of the source instance for push notifications. (NEO-94650) — ICICI only
* Fixed an issue with the custom send time feature on the Web UI where deliveries waited until the contact date and time to execute instead of executing at the equivalent local time per recipient timezone, breaking parity with Campaign Standard behavior. (NEO-94762) — H&M only (in progress at time of writing)
-->

## Versión 8.9.1 {#release-8-9-1}

_27 de enero de 2026_

>[!CAUTION]
>
> La actualización de la consola de cliente es obligatoria. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).

### Nuevas funciones {#new-8-9-1}

El **nuevo conector de envío de SMS** ya está disponible para todos los clientes (GA). Consulte la [documentación detallada](../send/sms/sms.md).

Esta versión incorpora un conjunto de funcionalidades disponibles con la interfaz de usuario web de Campaign:

* [Funciones de envío multilingües (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=es){target="_blank"}
* [Enriquecimiento de perfil en mensajes transaccionales (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=es){target="_blank"}
* [Copias de Adobe Experience Manager en vivo y de idioma](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html?lang=es){target="_blank"}
* [Experimentos de contenido: pruebas A/B](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html?lang=es){target="_blank"}
* [Actividad de envío continuo](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html?lang=es){target="_blank"}
* [Administración de aprobación de campaña](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html?lang=es){target="_blank"}

Consulte las [notas de la versión](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=es){target="_blank"} de la IU web de Campaign

### Mejoras de seguridad {#security-8-9-1}

* Las cuentas externas de Snowflake ahora admiten la autenticación OAuth2, lo que proporciona métodos de autenticación modernos y seguros para conexiones de acceso a datos federadas. (NEO-87013) [Más información](../config/external-accounts.md#snowflake-external-accounts)
* Las cuentas externas de Databricks ahora admiten la autenticación OAuth2 a través de la entidad de seguridad de servicio (flujo de credenciales de cliente no interactivo), lo que proporciona métodos de autenticación seguros para conexiones de acceso a datos federadas. La autenticación interactiva OAuth2 estará disponible en una versión futura. (NEO-87422) [Más información](../config/external-accounts.md#databricks-external-accounts)
* Se corrigieron las vulnerabilidades de acceso a archivos de flujo de trabajo restringiendo las operaciones a directorios autorizados, evitando el acceso no autorizado y la posible ejecución de código remoto. (NEO-88460)
* Se han agregado controles de inclusión en la lista de permitidos de URL de FTP a las actividades de flujo de trabajo de código JavaScript, restringiendo las conexiones FTP salientes solo a direcciones autorizadas. (NEO-89083)

### Otros cambios {#changes-8-9-1}

* Se ha mejorado la administración de la memoria contenedora mediante la implementación de restricciones automáticas del flujo de trabajo durante condiciones de alta memoria, con capacidades inteligentes de reinicio del flujo de trabajo y protecciones de memoria para procesos no críticos. (NEO-89041)
* Se ha agregado compatibilidad con las funciones asimétricas de cifrado y descifrado en los flujos de trabajo de Campaign. (NEO-80257)
* Rendimiento mejorado del agente de replicación y resistencia de la memoria para cargas de datos grandes en implementaciones de FDAC. (NEO-88430)
* Las actividades de flujo de trabajo **[!UICONTROL SQL code]** y **[!UICONTROL SQL Data Management]** se han mejorado para proteger mejor las bases de datos PostgreSQL y mantener los flujos de trabajo funcionando sin problemas cuando se ejecuta SQL personalizado desde Campaign. Consulte [Administración de datos SQL](../../automation/workflow/sql-data-management.md#important-notes) y [Código SQL](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) para obtener más información y prácticas recomendadas. (NEO-86540)


### Correcciones {#fixes-8-9-1}

* Se corrigió un problema en el cual la estructura de la base de datos no se podía actualizar después de cambios en sysFilter. (NEO-93306)
* Se ha corregido un problema por el cual faltaban datos de informes dinámicos después de la migración. (NEO-92962)
* Se ha corregido un problema en el cual el estado de entrega no se actualizaba correctamente. (NEO-92908)
* Se ha corregido un problema relacionado con la restricción Catálogo de uso de FDA de Databricks. (NEO-92900)
* Se ha corregido un problema que podría provocar errores de diseño de HTML en el escritorio de Outlook Windows. (NEO-92611)
* Se ha corregido un problema de integridad de datos en el que las claves principales de entrega se duplicaban en la instancia media después de una actualización. (NEO-92424)
* Se ha corregido un problema que impedía deshabilitar los vínculos en el cuadro de diálogo Seguimiento e imágenes de una entrega. (NEO-92381)
* Se ha corregido un problema en el cual la función nms.subscription.RecipientSubscribe() no funcionaba para la suscripción masiva. (NEO-92308)
* Se ha corregido un problema en el cual se producían errores de envío debido a partes de envío faltantes después de una actualización. (NEO-92278)
* Se ha corregido un problema en el flujo de trabajo de seguimiento por el que los errores de estado duplicados y los errores de sintaxis SQL evitaban que se actualizaran los indicadores de seguimiento. (NEO-92239)
* Se corrigió un problema en el cual las etiquetas de campo de enumeración faltaban o se mostraban incorrectamente en las listas creadas mediante el flujo de trabajo al utilizar campos dbEnum. (NEO-91158)
* Se ha corregido un problema por el cual el cuadro de diálogo RT publicar/cancelar publicación no se cerraba ni se bloqueaba. (NEO-91038)
* Se ha corregido un problema que se producía con los destinatarios con el estado &quot;Tenido en cuenta por el proveedor de servicios&quot;. (NEO-90927)
* Se ha corregido un problema por el que faltaba el origen de la suscripción (o cancelarla) para los vínculos de exclusión. (NEO-90714)
* Se corrigió un problema en el cual al agregar cupones se producía un error en la preparación de envíos. (NEO-90547)
* Se ha corregido un problema por el cual Insertar recuento de rechazos no se reflejaba con precisión en la pestaña Auditoría. (NEO-90318)
* Se ha corregido un problema de seguridad que podría provocar la denegación de servicio de la aplicación. (NEO-89984)
* Se ha corregido un problema por el cual el PDF descargado del informe de clic interactivo estaba dañado. (NEO-89954)
* Se ha resuelto un error de SSL que se producía después de una actualización y que provocaba un EOF inesperado al leer errores. (NEO-89108)
* Se corrigió un problema en el cual no se podían consultar los datos en un esquema de datos después de una actualización. (NEO-88663)
* Se ha corregido un error que se producía al concatenar un campo &quot;char&quot; en PostgreSQL 15. (NEO-88028)
* Se ha corregido un problema en el cual el orden de las variables de plantilla de envíos cambiaba al guardar o duplicar la plantilla. (NEO-87845)
* Se ha corregido un problema por el cual la interfaz web se bloqueaba al crear un nuevo esquema de biblioteca de datos. (NEO-87816)
* Se ha corregido un problema en el cual con conjuntos de complementos en la actividad de anulación de duplicación. (NEO-87711)
* Se ha corregido una solicitud de paquete de instalación sin dependencia de X11. (NEO-87471)
* Se ha corregido un problema en el cual los códigos de segmento no se podían usar en informes dinámicos. (NEO-87276)
* Se ha corregido un problema en el cual los flujos de trabajo se quedaban atascados en la actividad Actualizar datos. (NEO-87252)
* Se ha corregido un problema por el cual BigQuery usaba una zona horaria incorrecta. (NEO-86622)
* Se ha corregido un error de JavaScript que se producía al evaluar el script &quot;mcSynch_mcExec1/jsReplicateUrl&quot;. (NEO-86553)
* Se ha corregido un problema por el cual aparecían eventos duplicados en la tabla eventHisto debido a un método de cálculo de identificador incorrecto. (NEO-86544)
* Se ha corregido un problema en el cual la pestaña Avanzado no se mostraba para iOS Push upon copy. (NEO-86231)
* Se corrigió un problema en el cual el flujo de trabajo replicar tablas de referencia no podía replicar el esquema nms:delivery. (NEO-85884)
* Se ha corregido un problema en el cual los errores de dominio nulo correspondientes a las direcciones MXIP aparecían en los registros de errores al realizar entregas. (NEO-85238)
* Se ha corregido un problema por el cual las plantillas de envío técnicas no se actualizaban después de realizar cambios en las opciones. (NEO-84149)
* Se ha corregido un error en el flujo de trabajo de facturación predeterminado. (NEO-83624)
* Se ha corregido un problema con la exclusión de duplicados basados únicamente en la clave principal de los registros de destino. (NEO-82910)
* Se han corregido discrepancias en los informes de la interfaz de usuario web de Campaign en los que las estadísticas de seguimiento mostraban valores diferentes en comparación con la consola. (NEO-82339)
* Se ha corregido un problema en el cual la última fecha de modificación cambiaba incluso si el registro no debería actualizarse en la actividad de actualización de datos. (NEO-82002)
* Se ha corregido un problema en el cual la adición de nuevos atributos en una lista provocaba que fallaran los flujos de trabajo que leían la lista. (NEO-80258)
* Se ha corregido un problema por el cual el informe Indicadores de seguimiento mostraba valores incorrectos para aperturas distintas. (NEO-79466)