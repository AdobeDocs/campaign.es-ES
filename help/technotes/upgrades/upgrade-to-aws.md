---
title: Actualización de la infraestructura de envío de correo electrónico de Campaign
description: Actualización de la infraestructura de envío de correo electrónico de Campaign
source-git-commit: 4478c4b4b1eb3697ff03acfcd618ebfb1d875df9
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 5%

---


# Actualización de la infraestructura de envío de correo electrónico de Campaign {#migrate-infra-to-aws}

## ¿Qué se actualizará?{#aws-changes}

Como parte de nuestro esfuerzo continuo por proporcionar una experiencia de usuario óptima, estamos actualizando nuestro servicio de entrega de correo electrónico.

## ¿Se ha visto afectado?{#aws-impact}

Este cambio afecta a:

* Clientes de Adobe Campaign Classic Managed Services
* clientes de Adobe Campaign Managed Cloud Services
* Clientes de Adobe Campaign Standard On-demand

## ¿Cuándo se producirá esta actualización?{#aws-timeline}

Se espera que las actualizaciones de los entornos de desarrollo y ensayo se realicen en **Octubre de 2023**.

Tenemos previsto programar las actualizaciones del entorno de producción a partir de **Enero de 2024**.

Como cliente de Campaign, recibirá una notificación adicional con respecto a la actualización de la producción con al menos treinta (30) días de anticipación.

## ¿Qué esperar?{#impact}

* La longitud de cada ola de actualización variará según el número de instancias de Campaign afectadas. Cuando se programa una ola de actualización de producción, la notificación incluirá la duración estimada.

* Las instancias de Campaign, tanto en los entornos de ensayo como de producción, no podrán enviar correos electrónicos durante la ventana de actualización. No se espera que otras funcionalidades de Campaign se vean afectadas.

## Preguntas frecuentes {#aws-faq}

* **¿Es obligatoria esta actualización?**

  Sí. Como cliente de Campaign, su funcionalidad de envío de correo electrónico requiere el uso de una infraestructura de envío de correo electrónico.

* **¿Qué clientes son los destinatarios de esta actualización?**

  Se actualizarán los entornos de todos los clientes de Campaign a los que se hace referencia arriba.

* **¿Cuál es el tiempo de inactividad esperado?**

  La longitud de cada ola de actualización puede variar según el número de instancias de Campaign afectadas. Cuando se programa una ola de actualización de producción, la notificación incluirá una duración estimada.

* **¿El cliente requiere alguna acción para la actualización?**

  No se requiere ninguna acción. Adobe administrará el proceso de actualización, que se ejecutará automáticamente.

* **¿Qué pruebas requieren los clientes?**

  No esperamos pruebas por parte de los clientes en relación con este evento de actualización. Si se observa algún problema, póngase en contacto con [Adobe del Servicio de atención al cliente](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **¿Puedo solicitar un cambio de fecha y hora en el intervalo de actualización de seguridad programado?**

  No. No podemos ajustar ninguna modificación solicitada a la programación existente, ya que esto probablemente interrumpa el evento de actualización asignado para otro cliente.

Para cualquier otra pregunta, puede contactar con el [Servicio de atención al cliente de Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.