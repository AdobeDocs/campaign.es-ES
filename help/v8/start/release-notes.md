---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '1489'
ht-degree: 55%

---

# Último lanzamiento{#latest-release}

Adobe Campaign se actualiza periódicamente. Esta frecuencia regular de actualizaciones tiene como objetivo ofrecerle lo más novedoso y lo mejor, mantener el entorno seguro y mejorar su experiencia con nuestro producto. El Adobe recomienda encarecidamente a todos los clientes que actualicen a la versión más reciente.

Como usuario de Cloud Services administrados, la instancia se actualiza en Adobe con cada nueva versión. El Adobe se pondrá en contacto con usted y actualizará sus entornos. Consola del cliente de Campaign **debe actualizarse a la misma versión** como servidores de Campaign. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).

Además, como cliente de, asegúrese de que está utilizando las últimas versiones compatibles de los sistemas que se enumeran en la [Matriz de compatibilidad](compatibility-matrix.md).

## Versión 8.5.2 {#release-8-5-2}

_2 de agosto de 2023_

Se ha corregido un problema de seguridad que se podía producir al actualizar a 8.5.1. (NEO-64767)

## Versión 8.5.1 {#release-8-5}

_30 de junio de 2023_


**Servicio de notificaciones push mejorado**

La versión 8.5.1 de Campaign presenta nuestro último servicio de notificaciones push, con una estructura sólida basada en una tecnología moderna de vanguardia. Este servicio está diseñado para desbloquear nuevos niveles de escalabilidad, lo que garantiza que las notificaciones puedan llegar a una audiencia más grande con una eficiencia perfecta. Con nuestra infraestructura mejorada y los procesos optimizados, puede esperar una mayor escala y fiabilidad, lo que le permite interactuar y conectarse con los usuarios de sus aplicaciones móviles como nunca antes. Esta capacidad solo está disponible para un grupo seleccionado de clientes (disponibilidad limitada).

Para obtener más información, consulte la [documentación detallada](../send/push-data-collection.md).



<!--
The newly introduced Push notification service showcases significant improvements in throughput for both Push Android and Push iOS compared to our previous version (v8.4). Users will experience notably enhanced performance with the upgraded service in the latest version (v8.5).

* Push Notifications (Android): up to **5x** faster
* Push Notifications (iOS): up to **2.2x** faster

SMS throughput has undergone substantial enhancements through a series of optimizations, resulting in notable improvements in speed and efficiency for SMS communication. These upgrades have led to increased throughput from the previous version (v8.4) to the latest version (v8.5), encompassing both sending and feedback updates. Users can now experience the benefits of this enhanced SMS service.</p>

* SMS throughput: up to **5x** faster

These max throughput performances have been measured by Adobe testing teams, in lab conditions.
-->

<table style="table-layout:fixed" text-align="bottom"><tr style="border: 0;">
<td>
<br/><img alt="Mejoras de rendimiento" src="../start/assets/do-not-localize/improvements.jpeg">
<p>
</td>
<td>
<div>
<p><strong>Rendimiento aumentado del canal móvil</strong></p>
<p>El recién introducido servicio de notificaciones push muestra mejoras significativas en el rendimiento tanto para Push Android como para Push iOS en comparación con nuestra versión anterior (v8.4). Los usuarios experimentarán un rendimiento notablemente mejorado con el servicio actualizado en la última versión (v8.5). </p>
<ul>
<li>Notificaciones push (Android): hasta <strong>5x</strong> más rápido </li>
<li>Notificaciones push (iOS): hasta <strong>2,2x</strong> más rápido</li>
</ul>
<p>El rendimiento de los SMS ha experimentado mejoras sustanciales a través de una serie de optimizaciones, lo que resulta en mejoras notables en velocidad y eficiencia para la comunicación SMS. Estas actualizaciones han llevado a un mayor rendimiento desde la versión anterior (v8.4) a la última versión (v8.5), lo que incluye actualizaciones de envíos y comentarios. Los usuarios ahora pueden experimentar las ventajas de este servicio de SMS mejorado.</p>
<ul>
<li>Rendimiento de SMS: hasta <strong>5x</strong> más rápido</li>
</ul>
<p><em>Estos resultados máximos de rendimiento han sido medidos por equipos de prueba de Adobe, en condiciones de laboratorio.</em></p>
</div>
<p></p>
</td>
</tr></table>


**Mejoras generales**

* Ahora puede aprovechar la conexión de destino de Adobe Experience Platform para sincronizar atributos de perfil como datos de exclusión entre Adobe Experience Platform y la base de datos de Campaign v8.
* La preparación de envíos se ha optimizado en todos los canales.
* Se ha añadido una nueva opción de autenticación basada en claves para la cuenta externa SFTP, junto con el método de autenticación de usuario/contraseña existente. Los usuarios ahora pueden autenticarse de forma segura con una clave privada, lo que mejora la seguridad y proporciona un mecanismo de autenticación alternativo para el acceso SFTP. Obtenga más información en [esta sección](../config/external-accounts.md).

**Mejoras de seguridad**

* Con Campaign v8.5.1, se ha mejorado y protegido el proceso de autenticación en Campaign v8. Los operadores técnicos ahora deben utilizar Adobe Identity Management System (IMS) para conectarse a Campaign. Obtenga información sobre cómo migrar sus cuentas técnicas existentes en [esta nota técnica](../../technotes/upgrades/ims-migration.md).
* A partir de la próxima versión 8.6, ya no se le permitirá crear operadores desde la consola del cliente de Campaign. Si utiliza la autenticación nativa de inicio de sesión y contraseña, debe migrar los operadores a Adobe Identity Management System (IMS). Obtenga información sobre cómo migrar los operadores en [esta nota técnica](../../technotes/upgrades/migrate-users-to-ims.md).
* Se han actualizado varias herramientas de terceros para optimizar la seguridad.

**Actualizaciones de compatibilidad**

* La versión de 32 bits de la consola del cliente ya no se utiliza. A partir de la versión 8.6, la consola de cliente solo estará disponible en 64 bits. La actualización a la versión de 64 bits de la consola del cliente se realiza sin problemas. Para obtener más información sobre cómo actualizar el sistema operativo, consulte esta [nota técnica](../../technotes/upgrades/console.md).
* Ahora puede conectar la instancia de Campaign v8 a la base de datos externa de Azure synapse. Esta conexión se administra mediante una nueva cuenta externa. Obtenga más información en [Matriz de compatibilidad de Campaign](../start/compatibility-matrix.md#federated-data-access-fdafederateddataaccessfda).


**Parches**

* Se ha corregido un problema que podía provocar que los caracteres especiales del contenido del HTML de un envío se codificaran incorrectamente en varios exploradores. (NEO-60081)
* Se ha corregido un problema que podía impedir que guardara un informe en una implementación de Campaign v8 Enterprise (FDAC). (NEO-56836)
* Se ha corregido un problema que se producía al insertar o actualizar datos en un esquema de FDAC personalizado mediante una actividad de flujo de trabajo Actualizar datos. (NEO-54708)
* Se ha corregido un problema que impedía que el flujo de trabajo de limpieza de la base de datos eliminara direcciones en la tabla nms:address de FDAC. (NEO-54460)
* Se ha corregido un problema con el flujo de trabajo de facturación que podía fallar con un error de &quot;Memoria de compilación agotada&quot;. (NEO-51137)
* Se ha corregido un problema que podía impedir que el descifrado GPG funcionara correctamente en la actividad de flujo de trabajo Carga de datos (archivo). (NEO-50257)
* Se ha corregido un problema que impedía el funcionamiento de la función `JSPContext.sqlExecWithOneParam`. (NEO-50066)
* Se ha corregido un problema que provocaba errores de entrega al utilizar caracteres no imprimibles en campos de personalización. (NEO-48588)
* Se ha corregido un problema que podría provocar errores de entrega al insertar imágenes dinámicas de Adobe Target. (NEO-62689)
* Se ha corregido un problema para evitar que los exploradores agregaran espacios adicionales al utilizar contenido condicional en un envío. (NEO-62132)
* Se ha corregido un problema que provocaba que se abriera una ventana emergente al hacer clic en una imagen en el editor de contenido de correo electrónico. (NEO-60752)
* Se ha corregido un problema que podría provocar un error e impedir que usted se desplace al editar el contenido de un envío. (NEO-61364)
* El conector de Adobe Analytics ahora exporta las métricas con el tipo de canal correcto. Antes siempre se establecía como canal de &quot;correo electrónico&quot;. (NEO-26340)
* Se ha corregido un problema que podría provocar errores al utilizar el conector de Big Query con campos de fecha y hora. (NEO-49768)


## Versión 8.4.5 {#release-8-4-5}

_3 de abril de 2023_

**Parches**

* Se ha corregido un problema que podía provocar un error de restricción de clave duplicada si se establecían varios flujos de trabajo de aprobación en el mismo programa. (NEO-48968)
* Se ha corregido un problema de regresión introducido por NEO-54474 (8.4.4) que provocaba que el atributo de estilo de la etiqueta de cuerpo cambiara al cargar una imagen en el editor de contenido digital (DCE). (NEO-57697)
* Se ha corregido un problema que podía provocar un error al exportar datos mediante un conector CRM si la tabla temporal tenía una clave principal definida como long en lugar de uuid. (NEO-54153)
* Se ha corregido un problema de regresión introducido en la versión 8.4.1 que podía provocar errores en la exportación de paquetes, FDA sobre HTTP y creación de informes. (NEO-57731)
* Se ha corregido un problema de regresión introducido en la versión 8.3.8 que podía impedir que el estado de entrega se actualizara correctamente para los envíos con ID negativos. (NEO-54675)
* Se ha corregido un problema con los campos booleanos al importar datos mediante el conector Big Query (NEO-49181)


## Versión 8.4.4 {#release-8-4-4}

_8 de marzo de 2023_

**Mejora de la seguridad**

* Para mejorar la seguridad, Tomcat se ha actualizado de la versión 8.5.81 a la 8.5.85. (NEO-50530)

**Parches**

* Se ha corregido un problema que podía impedir que se desplazara en la pestaña **Editar** del Editor de contenido digital (DCE). (NEO-54474)
* Se ha corregido un problema durante la replicación que podría provocar el bloqueo de un servidor web. (NEO-53670)


## Versión 8.4.3 {#release-8-4-3}


_27 de enero de 2023_

**Mejoras**

* Se ha corregido un problema de sincronización en el indicador de entrega entre el servidor de marketing y el servidor intermediario. (NEO-50724) <!--OKKKK-->
* Se ha corregido un problema que podría provocar un error al exportar un flujo de trabajo. (NEO-50555) <!--OKKKK-->
* Se ha corregido un problema al ampliar un esquema que se había ampliado anteriormente. (NEO-49118) <!--OKKKK-->
* Se ha corregido un problema que se producía al usar dos actividades de enriquecimiento con el mismo identificador en la definición del vínculo. (NEO-48851)
* Se han corregido dos problemas de error en la preparación de envíos. La preparación del envío podría fallar cuando el número de ofertas potenciales que se están manipulando fuera demasiado alto. El segundo problema se producía cuando las direcciones URL de la imagen se definían como direcciones URL para rastrear en un envío en formato de texto. (NEO-48807) <!--OKKKK-->
* Se ha corregido un problema que podría provocar un error en el que un flujo de trabajo sobrescribía el nombre del almacén definido en la cuenta externa para cuentas que no son de FDAC. (NEO-43209) <!--OKKKK-->
* Se ha mejorado la seguridad en las aplicaciones web para evitar ataques DDoS. (NEO-50757) <!--OKKKK-->
* La administración de los datos de seguimiento consolidados se ha mejorado en la tabla de FDAC **[!UICONTROL Consolidated tracking]** (nms:trackingStats) para evitar duplicados. (NEO-46409)
* Se ha corregido un problema de operadores lógicos en las consultas de flujo de trabajo al usar un `enableIf` en una condición de operador lógico. Se ha sobrescrito la condición lógica anterior. (NEO-45815)  <!--OKKKK-->
* La generación de perfiles activos se ha optimizado en el flujo de trabajo de facturación para mejorar el rendimiento. (NEO-47658) <!--OKKKK-->
* Se ha corregido un problema con la importación de archivos HTML cuando los nodos de imagen (img) contenían direcciones URL con campos de personalización. (NEO-48396)
* Se ha corregido un problema con Snowflake (todas las implantaciones) al utilizar el parámetro de ordenación en una actividad de **División** del flujo de trabajo. (NEO-45899) <!--OKKKK-->
* Se ha corregido un problema que provocaba un error cuando un usuario con derechos de acceso de lectura en la carpeta nmsDeliveryMapping intentaba ejecutar una campaña o un flujo de trabajo. (NEO-48230)
* Se ha corregido un problema de rendimiento en la pestaña HTML de un envío que se podía producir en código HTML extenso. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Se ha corregido un problema que impedía usar la opción de flujo de trabajo **Combinar líneas seleccionadas**. (NEO-48488)
* Se ha corregido un problema en la versión del conector de FDA de Snowflake que provocaba la eliminación de registros al utilizar la opción “combinación simple de cardinalidad 0 o 1” durante el enriquecimiento. (NEO-48737)
* Las referencias restantes a la biblioteca log4j se han eliminado de la instalación de Campaign en Windows. (NEO-44851)
* Se ha corregido un problema que podría provocar un error al añadir el indicador **Destinatarios que han abierto** (estimatedRecipientOpen) en los datos adicionales de una actividad del flujo de trabajo **Consulta**. (NEO-46665)
* La administración de las direcciones URL de seguimiento se ha mejorado en los flujos de trabajo con varios envíos para mejorar el rendimiento. (NEO-50894) <!--OKKKK-->
* Se ha corregido un problema que podría provocar errores en la replicación de esquemas que utilizan Xtkfolder. (NEO-46787) <!--OKKKK-->
* Se ha corregido un problema que podría provocar que la columna personalizada “lastModified” se suelte en la tabla NmsSubscription. (NEO-48402)


