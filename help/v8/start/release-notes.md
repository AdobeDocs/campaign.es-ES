---
product: Adobe Campaign
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Información general
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 5d266b22661be2817e06ea71c1b0bec7f44a152d
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 7%

---

# Última versión{#latest-release}

Esta página enumera las nuevas funciones, mejoras y correcciones que se incluyen en la **última versión de Campaign v8**.

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
<p>La nueva actividad de flujo de trabajo <b>Cambiar fuente de datos</b> permite cambiar la fuente de datos de la tabla de trabajo de un flujo de trabajo. Esto proporciona una flexibilidad mejorada para administrar datos en diferentes fuentes de datos (FDA, FFDA y base de datos local).</p>
<p>En los flujos de trabajo de Adobe Campaign, los datos se administran mediante tablas de trabajo (o temporales). A medida que se ejecuta el flujo de trabajo, las tablas de trabajo comparten datos entre las actividades de flujo de trabajo. De forma predeterminada, las tablas de trabajo se crean en la misma base de datos que el origen de los datos en los que consultamos.</p>
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
<td> <p>El canal LINE ya está disponible con Campaign v8. Se han realizado las siguientes mejoras al utilizar LINE con el Centro de mensajes:
</p>
<ul> 
<li><p>Se ha corregido un problema que podía impedir que los visitantes se dirigieran a una entrega LINE. 
</p></li>
<li><p>Se ha corregido un problema que podría provocar errores al recuperar visitantes de la instancia de ejecución a la instancia de marketing.
</p></li>
<li><p>Se han corregido problemas durante el procesamiento de eventos en tiempo real en el contexto de envíos LINE mediante el Centro de mensajes.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Otras mejoras**

* Se ha corregido un problema que podía impedir que se mostrara el informe **Hot clicks** para envíos específicos.
* Se ha corregido un problema con la actividad de flujo de trabajo **Deduplication** que podría provocar un recuento duplicado impreciso.
* Se ha corregido un problema que se producía al utilizar una consulta de flujo de trabajo con el filtro &quot;El ID no está vacío&quot;, lo que podía hacer que se mostrara un elemento vacío en la población de transición.
* Se ha corregido un problema que impedía que se crearan campos adicionales en una nueva asignación de destino.
