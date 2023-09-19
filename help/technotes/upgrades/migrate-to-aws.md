---
title: Migración de la infraestructura de envío de Campaign a Amazon Web Service (AWS)
description: Migración de la infraestructura de envío de Campaign a Amazon Web Service (AWS)
hide: true
hidefromtoc: true
source-git-commit: f1b4002063c8b94eb7251a9bcde9fe11791d0be3
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 5%

---


# Migración de la infraestructura de envío de Campaign a Amazon Web Service (AWS) {#migrate-infra-to-aws}

## ¿Qué ha cambiado?{#aws-changes}

Como parte de nuestro esfuerzo continuo por proporcionar el servicio de envío de correo electrónico de la más alta calidad, la infraestructura de envío de correo electrónico de Campaign se está trasladando de los centros de datos alojados en el Adobe a Amazon Web Service (AWS).

Este movimiento garantizará una alta disponibilidad, un rendimiento óptimo y la capacidad de escalar para satisfacer las necesidades de nuestros clientes.

## ¿Se ha visto afectado?{#aws-impact}

Este cambio afecta a:

* Clientes alojados e híbridos de Campaign Classic v7
* Clientes de Campaign Managed Services
* Todos los clientes de la versión 8 de Campaign

## ¿Cuándo se producirá esta migración?{#aws-timeline}

La migración de los entornos de desarrollo y ensayo se producirá en **Octubre de 2023**.

La migración de los entornos de producción está programada para empezar en **Enero de 2024**. Se proporcionarán más detalles a medida que se aproxime la fecha.

Como cliente de Campaign, recibirá una notificación adicional a medida que se programen las olas de migración. Las notificaciones se enviarán al menos 7 días antes de la migración para los entornos de ensayo y al menos 30 días antes de la migración para los entornos de producción.

## ¿Cuáles son las consecuencias?{#impact}

Este movimiento será transparente para los clientes:

* Se espera que la migración tarde entre 30 y 60 minutos.

* Las instancias de Campaign no podrán enviar correos electrónicos durante la ventana de migración. Ninguna otra función de Campaign se verá afectada.


## Preguntas frecuentes {#aws-faq}

* **¿Por qué es una actualización obligatoria?**

  La nueva infraestructura de envío de Campaign alojada en Adobe Web Services (AWS) ofrece mejor calidad y fiabilidad a nuestros clientes. También proporciona una infraestructura sólida y moderna para garantizar una mejor disponibilidad y un rendimiento óptimo.

* **¿Qué clientes son los destinatarios de esta migración?**

  Se migrarán todos los entornos de los clientes de Campaign v8 y de Campaign Classic v7 hybrid, alojados y Campaign Managed Services.

* **¿Cuál es el tiempo de inactividad esperado?**

  El tiempo de inactividad esperado es de entre 30 y 60 minutos.

* **¿El cliente requiere alguna acción para la migración?**

  No se requiere ninguna acción, ya que la migración se ejecutará automáticamente mediante Adobe.

* **¿Qué validaciones deben ejecutar los clientes?**

  No se necesitan pruebas específicas para esta migración. Si se observa algún problema, póngase en contacto con [Adobe del Servicio de atención al cliente](https://experienceleague.adobe.com/?support-solution=Campaign#support)


* **¿Puedo solicitar un cambio de fecha y hora en el intervalo de actualización de seguridad programado?**

  Dado que se trata de una migración obligatoria, le recomendamos encarecidamente que se adapte a la programación existente.


Para cualquier otra pregunta, puede contactar con el [Servicio de atención al cliente de Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support).
