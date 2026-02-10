---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: c7f1edc27a7e09a3a7da172af1df7de01118c516
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 17%

---

# Últimas versiones {#latest-release}

En esta página se indican las nuevas funciones, mejoras y correcciones que se incluyen con las **últimas versiones** de la versión 8 de Campaign (consola). Obtenga más información sobre las versiones y actualizaciones de Campaign en [esta página](upgrades.md). Otras versiones se indican en la sección Versiones anteriores de esta documentación.

## Versión 8.9.1 {#release-8-9-1}

_27 de enero de 2026_

>[!CAUTION]
>
> La actualización de la consola de cliente es obligatoria. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).

### Nuevas funciones {#new-8-9-1}

El **nuevo conector de envío de SMS** ya está disponible para todos los clientes (GA). Consulte la [documentación detallada](../send/sms/sms.md).

Esta versión incorpora un conjunto de funcionalidades disponibles con la interfaz de usuario web de Campaign:

* [Funciones de envío multilingüe (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [Enriquecimiento de perfil en mensajes transaccionales (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Copias de Adobe Experience Manager en vivo y de idioma](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [Experimentos de contenido: pruebas A/B](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html){target="_blank"}
* [Actividad de envío continuo](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html){target="_blank"}
* [Administración de aprobación de campaña](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html){target="_blank"}

Consulte las [notas de la versión](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=es){target="_blank"} de la IU web de Campaign

### Mejoras de seguridad {#security-8-9-1}

* Las cuentas externas de Snowflake ahora admiten la autenticación OAuth2, lo que proporciona métodos de autenticación modernos y seguros para conexiones de acceso a datos federadas. (NEO-87013)
* Las cuentas externas de Databricks ahora admiten la autenticación OAuth2 a través de la entidad de seguridad de servicio (flujo de credenciales de cliente no interactivo), lo que proporciona métodos de autenticación seguros para conexiones de acceso a datos federadas. La autenticación interactiva OAuth2 estará disponible en una versión futura. (NEO-87422)
* Se corrigieron las vulnerabilidades de acceso a archivos de flujo de trabajo restringiendo las operaciones a directorios autorizados, evitando el acceso no autorizado y la posible ejecución de código remoto. (NEO-88460)
* Se han agregado controles de inclusión en la lista de permitidos de URL de FTP a las actividades de flujo de trabajo de código JavaScript, restringiendo las conexiones FTP salientes solo a direcciones autorizadas. (NEO-89083)

### Otros cambios {#changes-8-9-1}

* Se ha mejorado la administración de la memoria contenedora mediante la implementación de restricciones automáticas del flujo de trabajo durante condiciones de alta memoria, con capacidades inteligentes de reinicio del flujo de trabajo y protecciones de memoria para procesos no críticos. (NEO-89041)
* Se ha agregado compatibilidad con las funciones asimétricas de cifrado y descifrado en los flujos de trabajo de Campaign. (NEO-80257)
* Rendimiento mejorado del agente de replicación y resistencia de la memoria para cargas de datos grandes en implementaciones de FDAC. (NEO-88430)


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