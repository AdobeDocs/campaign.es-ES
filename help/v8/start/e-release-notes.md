---
title: Notas de la versión preliminar de Campaign v8
description: Versión preliminar de Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 33%

---

# Notas de la versión preliminar {#e-new-release}

Esta página describe las mejoras y correcciones incluidas en la próxima versión de Campaign v8. Este contenido está sujeto a cambios sin previo aviso hasta la fecha de lanzamiento. Las notas de la versión oficiales están disponibles en esta [página](../start/release-notes.md).

## Versión 8.5.1 {#release-8-5}

_30 de junio de 2023_

**Novedades**

<table> 
<thead>
<tr> 
<th> <strong>Servicio de notificaciones push mejorado</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Campaign 8.5.1 presenta nuestro último servicio de notificaciones push en la versión 8, con una estructura sólida basada en una tecnología moderna de vanguardia. Este servicio está diseñado para desbloquear nuevos niveles de escalabilidad, lo que garantiza que las notificaciones puedan llegar a una audiencia más grande con una eficiencia perfecta. Con nuestra infraestructura mejorada y los procesos optimizados, puede esperar una mayor escala y fiabilidad, lo que le permite interactuar y conectarse con los usuarios de sus aplicaciones móviles como nunca antes. Esta capacidad solo está disponible para un grupo seleccionado de clientes (disponibilidad limitada).</p>
</td> 
</tr> 
</tbody> 
</table>

**Actualizaciones de compatibilidad**

* La versión de 32 bits de la consola del cliente ya no se utiliza. A partir de la versión 8.6, la consola de cliente solo estará disponible en 64 bits. La actualización a la versión de 64 bits de la consola del cliente se realiza sin problemas. Para obtener más información sobre cómo actualizar el sistema operativo, consulte esta [nota técnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=es).
* Ahora puede conectar la instancia de Campaign v8 a la base de datos externa de Azure synapse. Esta conexión se administra mediante una nueva cuenta externa.

**Mejoras**

* El rendimiento de los SMS se ha mejorado significativamente mediante la implementación de una serie de optimizaciones, lo que resulta en una velocidad y eficiencia mejoradas para la comunicación SMS.
* A partir de la versión 8.5.1 de Campaign, se ha mejorado el proceso de autenticación en la versión 8 de Campaign. Los operadores técnicos deben utilizar Adobe Identity Management System (IMS) para conectarse a Campaign.
* Ahora puede aprovechar las conexiones de destino y origen para sincronizar atributos de perfil como los datos de exclusión entre Adobe Experience Platform y la base de datos de Campaign v8
* Se ha optimizado la preparación del envío.
* Se ha añadido una nueva opción de autenticación basada en claves para la cuenta externa SFTP, junto con el método de autenticación de usuario/contraseña existente. Los usuarios ahora pueden autenticarse de forma segura con una clave privada, lo que mejora la seguridad y proporciona un mecanismo de autenticación alternativo para el acceso SFTP.

**Mejoras de seguridad**

* Ya no puede crear operadores desde la consola de cliente. Ahora debe utilizar el Admin Console. [Más información](../start/gs-permissions.md).
* Se han actualizado varias herramientas de terceros para optimizar la seguridad.

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
