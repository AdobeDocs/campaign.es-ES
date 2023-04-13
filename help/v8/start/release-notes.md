---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 44743e585119e8cd81a8fcc9b4d667c25c0d438e
workflow-type: ht
source-wordcount: '678'
ht-degree: 100%

---

# Última versión{#latest-release}

Esta página lista las nuevas funcionalidades, mejoras y correcciones que se proporcionan con la **última versión de Campaign v8**.

## Versión 8.4.5 {#release-8-4-5}

_3 de abril de 2023_

**Parches**

* Se ha corregido un problema que podía provocar un error de restricción de clave duplicada si se establecían varios flujos de trabajo de aprobación en el mismo programa. (NEO-48968)
* Se ha corregido un problema de regresión introducido por NEO-54474 (8.4.4) que provocaba que el atributo de estilo de la etiqueta de cuerpo cambiara al cargar una imagen en el editor de contenido digital (DCE). (NEO-57697)
* Se ha corregido un problema que podía provocar un error al exportar datos mediante un conector CRM si la tabla temporal tenía una clave principal definida como long en lugar de uuid. (NEO-54153)
* Se ha corregido un problema de regresión introducido en la versión 8.4.1 que podía provocar errores en la exportación de paquetes, FDA sobre HTTP y creación de informes. (NEO-57731)
* Se ha corregido un problema de regresión introducido en la versión 8.3.8 que podía impedir que el estado de entrega se actualizara correctamente para los envíos con ID negativos. (NEO-54675)
* Se ha corregido un problema con los campos booleanos al importar datos mediante el conector Big Query (NEO-49181)

>[!CAUTION]
>
> La actualización de la consola de cliente es obligatoria. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).

## Versión 8.4.4 {#release-8-4-4}

_8 de marzo de 2023_

**Mejora de la seguridad**

* Para mejorar la seguridad, Tomcat se ha actualizado de la versión 8.5.81 a la 8.5.85. (NEO-50530)

**Parches**

* Se ha corregido un problema que podía impedir que se desplazara en la pestaña **Editar** del Editor de contenido digital (DCE). (NEO-54474)
* Se ha corregido un problema durante la replicación que podría provocar el bloqueo de un servidor web. (NEO-53670)


>[!CAUTION]
>
> La actualización de la consola de cliente es obligatoria. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).


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


>[!CAUTION]
>
> La actualización de la consola de cliente es obligatoria. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).
