---
product: Adobe Campaign
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 5b81c8e9e391ea1a9ad1825e5102b66c7926c204
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 43%

---

# Última versión{#latest-release}

Esta página lista las nuevas funcionalidades, mejoras y correcciones que se proporcionan con la **última versión de Campaign v8**.

## Versión 8.1.20 {#release-8-1-20}

_7 de septiembre de 2021_

**Mejoras de seguridad**

* Se ha corregido un problema de seguridad para reforzar la protección contra ataques de recorrido de directorios. (NEO-28547)

**Mejoras**

* Tras finalizar su vida útil, el Flash se ha eliminado de todas las funciones y componentes de Campaign relacionados y se ha sustituido por HTML5. Se ha eliminado el tipo de gráfico **Medición**. (NEO-30330) [Más información](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html)
* Al instalar la consola del cliente en Windows, el instalador ahora comprueba si hay un nodo de registro principal y crea uno si falta. Esto evita posibles problemas al iniciar la consola. (NEO-34854)
* La función de firma de seguimiento se ha mejorado para evitar errores vinculados a la forma en que las herramientas de terceros (clientes de correo electrónico, navegadores de Internet, etc.) gestione caracteres especiales. Los parámetros de URL ahora están codificados.

**Otros cambios**

* Los conectores de Microsoft CRM obsoletos anteriormente (Office 365 e implementaciones locales) se han eliminado de la interfaz. [Más información](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html#configure-acc-for-microsoft)
* Después de la migración a Tomcat 8, el script de configuración de IIS se ha actualizado para solucionar los problemas de integración de IIS. (NEO-31019)
* Se ha agregado una protección para permitir que el [flujo de trabajo técnico de facturación](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html#billing-report) se ejecute en la instancia de marketing.
* La identificación de la fuente de datos se ha mejorado en las pestañas data y schema de la ventana **View population** de transiciones de flujo de trabajo.
* Los índices de base de datos que faltaban se agregaron a los siguientes esquemas para evitar problemas de actualización de la base de datos: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Parches**

* Se ha corregido un problema que impedía que el informe **Hot clicks** funcionara cuando las ofertas estaban vinculadas al envío. (NEO-26295)
* Se ha corregido un problema con la actividad **Sub-workflow** cuando su ejecución no generaba una tabla de salida. (NEO-36242)
* Se han corregido varios problemas al exportar el informe **Descriptive analysis** a PDF. (NEO-25847)
* Se ha corregido un problema que podría provocar errores en los envíos al utilizar un envío de correo externo. (NEO-37435)
* Se ha corregido un error al conectarse a Microsoft CRM mediante API web. El mensaje de error se ha eliminado porque las funcionalidades no se vieron afectadas.
* Se ha corregido un problema de deduplicación del registro de seguimiento cuando el servidor mid se establecía como reenvío entre los servidores de seguimiento y marketing. (NEO-36285)
* Se ha corregido una regresión que impedía que Vault se usara como almacén de código específico.
* Se ha corregido un problema que impedía usar variables en una actividad de flujo de trabajo **Enrichment** cuando la transición entrante era de una fuente de datos FDA.
* Se ha corregido un problema con FFDA que impedía la replicación adecuada de los grupos de operadores y los derechos.
* Se ha corregido un problema que podría provocar el envío de un vínculo de baja incorrecto a través de la entrega.
* Se ha corregido un problema en la administración de la replicación que afectaba a la duración de la posactualización.
* Se ha corregido un problema que podía impedir que se mostrara el **Hot click**.
* Se ha corregido un problema que podría provocar URL rotas en los mensajes de correo electrónico.

## Versión 8.1.14 {#release-8-1-14}

_23 de julio de 2021_

**Novedades**

<table>
<thead>
<tr>
<th><strong>Nueva actividad de flujo de trabajo: Cambiar fuente de datos</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>La nueva actividad de flujo de trabajo <b>Cambiar fuente de datos</b> permite cambiar la fuente de datos de la tabla de trabajo de un flujo de trabajo. Esto proporciona una flexibilidad mejorada para administrar datos en diferentes fuentes de datos (FDA, FDAC y base de datos local).</p>
<p>En los flujos de trabajo de Adobe Campaign, los datos se administran mediante tablas de trabajo (o temporales). A medida que se ejecuta el flujo de trabajo, las tablas de trabajo comparten datos entre las actividades de flujo de trabajo. De forma predeterminada, las tablas de trabajo se crean en la misma base de datos que el origen de los datos que consultamos.</p>
<p>Con Campaign v8, la tabla de perfiles principales se almacena directamente en la base de datos de la nube. Por lo tanto, al consultar la tabla Perfiles también se creará una tabla de trabajo en la base de datos de la nube. En algunos casos, puede tener sentido mover la tabla de trabajo a otra fuente de datos para realizar operaciones específicas.</p>
<p>Para obtener más información, consulte la <a href="../config/workflows.md#change-data-source-activity">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilidad del canal LINE</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>El <a href="../send/line.md">canal LINE</a> ya está disponible con Campaign v8, e incluye las siguientes mejoras cuando se combina con el módulo <a href="../send/transactional.md">mensajería transaccional</a>:
<ul> 
<li><p>Se ha corregido un problema que podía impedir que los visitantes se dirigieran a una entrega LINE. 
</p></li>
<li><p>Se ha corregido un problema que podría provocar errores al recuperar visitantes de la instancia de ejecución a la instancia de marketing.
</p></li>
<li><p>Se han corregido problemas durante el procesamiento de eventos en tiempo real.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Otras mejoras**

* Se ha corregido un problema que podía impedir que se mostrara el informe **Clics activos** para entregas específicas.
* Se ha corregido un problema con la actividad de flujo de trabajo **Anulación de duplicación** que podía provocar un recuento duplicado impreciso.
* Se ha corregido un problema que se producía al utilizar una consulta de flujo de trabajo con el filtro “El ID no está vacío”, lo que podía hacer que se mostrara un elemento vacío en la población de transición.
* Se ha corregido un problema que impedía que se crearan campos adicionales en una nueva asignación de destino.
