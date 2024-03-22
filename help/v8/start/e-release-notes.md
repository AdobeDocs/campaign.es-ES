---
title: Notas de la versión preliminar de Campaign v8
description: Versión preliminar de Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 68%

---

# Notas de la versión preliminar {#e-new-release}

Esta página describe las mejoras y correcciones incluidas en la próxima versión de Campaign v8. Este contenido está sujeto a cambios sin previo aviso hasta la fecha de lanzamiento. Las notas de la versión oficiales están disponibles en esta [página](../start/release-notes.md).

## Versión 8.6.1 {#release-8-6-1}

_14 de febrero de 2024_


### Nuevas características {#new-8-6-1}

* A partir de esta versión, tendrá acceso a la nueva **Interfaz de usuario web de Campaign**, disponible a través del entorno central de Adobe Experience Cloud. Experience Cloud es la familia integrada de aplicaciones, productos y servicios de marketing digital de Adobe. Desde su intuitiva interfaz, puede acceder rápidamente a sus aplicaciones, funciones de productos y servicios en la nube. Obtenga información sobre cómo conectarse a Adobe Experience Cloud y acceder a la interfaz de Adobe Campaign Web [en esta página](campaign-ui.md#ac-web-ui).

* La versión de 32 bits de la consola del cliente ya no se utiliza. A partir de la versión 8.6, la consola de cliente solo estará disponible en 64 bits. La actualización a la versión de 64 bits de la consola del cliente se realiza sin problemas. Para obtener más información sobre cómo actualizar el sistema operativo, consulte esta sección [nota técnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=es){target="_blank"}.


### Mejoras generales {#improvements-8-6-1}

* Campaign v8.6 ofrece un rendimiento mejorado para **indicadores de seguimiento de envíos de correo electrónico**. Con nuestros procesos optimizados, el seguimiento de la ingesta y el tiempo de cálculo se reducen, y puede comprobar los indicadores clave de envío mucho más rápido.

* Ahora puede conectar la instancia de Campaign v8 a la base de datos externa de Azure synapse. Esta conexión se administra mediante una nueva cuenta externa.

* Adobe Campaign v8 ahora se integra con **Adobe Experience Manager as a Cloud Service**, con la creación exclusivamente disponible a través de la interfaz de usuario web de Adobe Campaign.

* Ahora puede utilizar su **Biblioteca de Adobe Experience Manager Assets** junto con los recursos de Experience Cloud, incluso si la variable **Integración con Adobe Experience Cloud** El paquete de está instalado en la instancia de Adobe Campaign.

* Ya no puede crear operadores desde la consola del cliente. Ahora debe utilizar el Admin Console. [Más información](../start/gs-permissions.md).

* Se han actualizado varias herramientas de terceros para optimizar la seguridad.

### Actualizaciones de la entregabilidad {#deliverability-8-6-1}

* En febrero de 2024, cualquier compañía que envíe más de 5000 mensajes de correo electrónico a través de Google o Yahoo! tendrá que empezar a utilizar una tecnología de autenticación conocida como Domain based Message Authentication, Reporting and Conformance (DMARC). Asegúrese de tener configurado el registro DMARC para todos los subdominios que utilice con Adobe Campaign. [Más información](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=es){target="_blank"}

* A partir del 1 de junio de 2024, Google y Yahoo! exigirán a los remitentes que cumplan con la cancelación de la suscripción a una lista en un clic. Adobe Campaign ahora admite esta opción. [Más información](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=es#one-click-list-unsubscribe){target="_blank"}


### Correcciones {#fixes-8-6-1}

Los siguientes problemas se encuentran en esta versión: 
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-63815, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO- 58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789