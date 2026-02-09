---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4fe8b8eaf88f763e796dbe06ef3c1477de12bad6
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 18%

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
* Se corrigieron las vulnerabilidades de acceso a archivos de flujo de trabajo restringiendo las operaciones a directorios autorizados, evitando el acceso no autorizado y la posible ejecución de código remoto. (NEO-88460)
* Se han agregado controles de inclusión en la lista de permitidos de URL de FTP a las actividades de flujo de trabajo de código JavaScript, restringiendo las conexiones FTP salientes solo a direcciones autorizadas. (NEO-89083)

### Otros cambios {#changes-8-9-1}

* Se ha mejorado la administración de la memoria contenedora mediante la implementación de restricciones automáticas del flujo de trabajo durante condiciones de alta memoria, con capacidades inteligentes de reinicio del flujo de trabajo y protecciones de memoria para procesos no críticos. (NEO-89041)
* Se ha agregado compatibilidad con las funciones asimétricas de cifrado y descifrado en los flujos de trabajo de Campaign. (NEO-80257)
* Rendimiento mejorado del agente de replicación y resistencia de la memoria para cargas de datos grandes en implementaciones de FDAC. (NEO-88430)


### Correcciones {#fixes-8-9-1}

* Se corrigió un problema en el cual la estructura de la base de datos no se podía actualizar después de cambios en sysFilter. (NEO-93306)
* Se ha resuelto un problema por el que faltaban datos de informes dinámicos después de la migración. (NEO-92962)
* Se ha corregido un problema en el cual el estado de entrega no se actualizaba correctamente. (NEO-92908)
* Se ha añadido una solución para la restricción CATÁLOGO DE USO DE FDA de Databricks. (NEO-92900)
* Se ha corregido un problema en el cual el Editor visual dañaba el diseño de HTML en el escritorio de Outlook Windows. (NEO-92611)
* Se ha resuelto un problema crítico de integridad de datos en el que las claves principales de entrega se duplicaban en la instancia media después de la actualización. (NEO-92424)
* Se ha corregido un problema en el cual los vínculos no se podían deshabilitar en el Seguimiento e imágenes (Cuadro de diálogo) de una entrega. (NEO-92381)
* Se ha corregido un problema por el que la función nms.subscription.RecipientSubscribe() no funcionaba para la suscripción masiva. (NEO-92308)
* Se ha resuelto un problema en el cual se producían errores de envío debido a la falta de piezas de envío después de la actualización. (NEO-92278)
* Se ha corregido un problema en el flujo de trabajo de seguimiento. (NEO-92239)
* Se ha resuelto un problema en el cual faltaban referencias de enumeración temporales en el XML de lista después de la creación de la lista mediante un flujo de trabajo. (NEO-91158)
* Se ha corregido un problema en el cual el cuadro de diálogo Publicación de RT/Cancelar la publicación no se cerraba ni se bloqueaba. (NEO-91038)
* Se ha resuelto un problema en el cual los destinatarios que se quedaban con el estado &quot;Tenido en cuenta por el proveedor de servicios&quot; no llegaban a Momentum. (NEO-90927)
* Se ha corregido un problema por el que el origen de la suscripción (o cancelarla) faltaba en la versión 8 para los vínculos de no participación. (NEO-90714)
* Se corrigió un problema en el cual la adición de cupones fallaba en la preparación de envíos. (NEO-90547)
* Se ha corregido un problema por el cual Insertar recuento de rechazos no se reflejaba con precisión en la pestaña Auditoría. (NEO-90318)
* Se ha resuelto un problema de seguridad que podría provocar la denegación de servicio de la aplicación. (NEO-89984)
* Se ha corregido un problema por el cual el PDF descargado del informe de clic interactivo estaba dañado. (NEO-89954)
* Se ha resuelto un error de SSL que se producía después de la actualización y que provocaba un EOF inesperado al leer errores. (NEO-89108)
* Se corrigió un problema en el cual no se podían consultar los datos en el esquema de datos después de la actualización. (NEO-88663)
* Se ha corregido un error que se producía al concatenar un campo &quot;char&quot; en PostgreSQL 15. (NEO-88028)
* Se ha corregido un problema en el cual el orden de las variables de plantilla de envíos cambiaba al guardar o duplicar la plantilla. (NEO-87845)
* Se ha resuelto un problema en el cual la interfaz web se bloqueaba al crear un nuevo esquema de biblioteca de datos. (NEO-87816)
* Se ha corregido un problema en el cual el código de segmento del conjunto de complementos de la actividad de anulación de duplicación no funcionaba. (NEO-87711)
* Se ha resuelto una solicitud de paquete de instalación sin dependencia de X11. (NEO-87471)
* Se ha corregido un problema en el cual los códigos de segmento no se podían usar en informes dinámicos. (NEO-87276)
* Se ha resuelto un problema en el cual los flujos de trabajo se quedaban atascados en la actividad Actualizar datos. (NEO-87252)
* Se ha corregido un problema por el cual BigQuery usaba una zona horaria incorrecta. (NEO-86622)
* Se ha corregido un error de JavaScript que se producía al evaluar el script &quot;mcSynch_mcExec1/jsReplicateUrl&quot;. (NEO-86553)
* Se ha resuelto un problema en el cual aparecían eventos duplicados en la tabla eventHisto debido al método de cálculo de identificador. (NEO-86544)
* Se ha corregido un problema en el cual la pestaña Avanzado no se mostraba para iOS Push upon copy. (NEO-86231)
* Se ha resuelto un problema en el cual el flujo de trabajo Replicar tablas de referencia no podía replicar el esquema nms:delivery. (NEO-85884)
* Se ha corregido un problema en el cual los errores de dominio nulo correspondientes a las direcciones MXIP aparecían en los registros de errores al realizar entregas. (NEO-85238)
* Se ha añadido una forma de actualizar las plantillas de envío técnicas después de cualquier cambio que se haya realizado en las opciones. (NEO-84149)
* Se ha corregido un error en el flujo de trabajo de facturación predeterminado. (NEO-83624)
* Se ha resuelto un problema con la exclusión de duplicados basados únicamente en la clave principal de los registros de destino. (NEO-82910)
* Se han corregido discrepancias en los informes de la interfaz de usuario web de Campaign en los que las estadísticas de seguimiento mostraban valores diferentes en comparación con la consola. Los informes Indicadores de seguimiento, Resumen de envío y Flujos de clic en URL ahora muestran métricas coherentes en ambas interfaces. (NEO-82339)
* Se ha corregido un problema por el cual la última fecha de modificación cambiaba aunque el registro no se actualizara en la actividad Actualizar datos. (NEO-82002)
* Se ha corregido un problema en el cual la adición de nuevos atributos en una lista provocaba que fallaran los flujos de trabajo que leían la lista. (NEO-80258)
* Se ha resuelto una anomalía en el informe Indicadores de seguimiento. (NEO-79466)