---
product: campaign
title: Nota técnica - Adobe Campaign - Actualización de seguridad de la versión de Apache
description: 'Adobe Campaign: Actualización de seguridad de la versión de Apache'
hide: true
hidefromtoc: true
exl-id: 68e42fe4-7fb6-4b53-9f39-e77374e3753d
source-git-commit: 50dcdf1f6bcc8c8a195a0bf0a37af254f33b80d5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Adobe Campaign: Actualización de seguridad de la versión de Apache {#apache-update}

>[!CAUTION]
>Este artículo se aplica a: clientes de Campaign Classic v7 Managed Cloud Service, clientes de Campaign v8 y clientes de Campaign Standard.

Adobe Campaign funciona con herramientas de terceros y la compatibilidad se actualiza de forma regular para implementar únicamente versiones compatibles y beneficiarse de las últimas correcciones y mejoras.

Adobe Campaign incluye Apache Tomcat, que actúa como punto de entrada en el servidor de aplicaciones a través de HTTP y está integrado con el servidor web Apache. Apache Software Foundation ha lanzado Apache HTTP Server 2.4.53. Esta versión aborda las vulnerabilidades que pueden permitir a un atacante remoto tomar el control de un sistema afectado. Obtenga más información en [Anuncio de Apache 2.4.53](https://downloads.apache.org/httpd/Announcement2.4.html){target="_blank"}.

El equipo de Adobe Campaign llevará a cabo la actividad de actualización de seguridad de la versión de Apache mediante **15 de junio de 2022** para mitigar esta vulnerabilidad de Apache y hacer que su entorno de instancia sea más seguro. Esta actualización se aplica a todos los clientes de Campaign Classic v7 Managed Cloud Service, Campaign v8 y los clientes de Campaign Standard que se ejecutan en una versión vulnerable de Apache HTTP Server. Si se ve afectado, Adobe ya se ha puesto en contacto con usted para informarle sobre esta actualización.

Se espera que esta actualización se ejecute automáticamente fuera del horario laboral normal para que pueda seguir utilizando el servicio de Campaign sin interrupciones.

Nuestros equipos actualizarán primero sus instancias que no sean de producción antes de actualizar las instancias de producción. Dado que se trata de un proceso de actualización automática propiedad de Adobe, no se requiere ninguna acción por su parte. Sin embargo, si tiene algún problema, póngase en contacto con [Adobe del Servicio de atención al cliente](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


>[!NOTE]
>Esta actualización requiere reiniciar el servidor web Apache. El tiempo de inactividad no excederá los 10 minutos dentro del lapso de tiempo mencionado a continuación.
> 

## Preguntas frecuentes {#apache-faq}

* **¿Por qué es una actualización obligatoria?**

  La versión actual de Apache es vulnerable y tiene una amenaza de seguridad potencial. Es importante que las instancias de Campaign se actualicen a la última versión de Apache aplicable para hacer frente al riesgo de seguridad.


* **¿Qué clientes son el objetivo de las actualizaciones de seguridad?**

  Todos los clientes que utilizan entornos de Campaign implementados en versiones de Apache anteriores se actualizan a la última versión de Apache aplicable.

* **¿Cuál es el tiempo de inactividad esperado?**

  El tiempo de inactividad esperado es inferior a 10 minutos.

* **¿El cliente necesita llevar a cabo alguna acción para esta actualización de seguridad?**

  No se requiere ninguna acción, ya que la actualización de seguridad se ejecutará automáticamente.

* **¿Qué validaciones deben ejecutar los clientes?**

  No se necesitan pruebas específicas para esta actualización de seguridad. Si se observa algún problema, póngase en contacto con [Adobe del Servicio de atención al cliente](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **¿Puedo solicitar un cambio de fecha y hora en el intervalo de actualización de seguridad programado?**

  Como se trata de una corrección de seguridad, le recomendamos encarecidamente que se adapte a la programación existente.


Para cualquier otra pregunta, puede comunicarse con [Adobe del Servicio de atención al cliente](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
