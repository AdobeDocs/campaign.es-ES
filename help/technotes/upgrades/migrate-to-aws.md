---
title: Migración de la infraestructura de envío de Campaign a Amazon Web Service (AWS)
description: Migración de la infraestructura de envío de Campaign a Amazon Web Service (AWS)
hide: true
hidefromtoc: true
exl-id: 50279a2f-0296-43f5-8967-16cc6a0c88f6
source-git-commit: 3e95a56825a143a4457ab7ee242208d7daaeb414
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 3%

---

# Migración de la infraestructura de envío de Campaign a Amazon Web Service (AWS) {#migrate-infra-to-aws}

## ¿Qué ha cambiado?{#aws-changes}

Como parte de nuestro esfuerzo continuo por proporcionar el servicio de envío de correo electrónico de la más alta calidad, la infraestructura de envío de correo electrónico de Campaign se está trasladando de los centros de datos alojados de Adobe a Amazon Web Service (AWS).

Este movimiento garantizará una alta disponibilidad, un rendimiento óptimo y la capacidad de escalar para satisfacer las necesidades de nuestros clientes.

## ¿Se ha visto afectado?{#aws-impact}

Este cambio afecta a:

* Clientes híbridos y alojados de Campaign Classic v7
* Clientes de Campaign Managed Services
* Todos los clientes de la versión 8 de Campaign
* clientes de Campaign Standard

## ¿Cuándo se producirá esta migración?{#aws-timeline}

La migración de los entornos de ensayo y desarrollo se realizará en **octubre de 2023**.

La migración de los entornos de producción está programada para el **enero de 2024**. Se proporcionarán más detalles a medida que se aproxime la fecha.

Como cliente de Campaign, recibirá una notificación adicional a medida que se programen las olas de migración. Las notificaciones se enviarán al menos 7 días antes de la migración para los entornos de ensayo y al menos 30 días antes de la migración para los entornos de producción.

## ¿Cuál es el impacto?{#impact}

Este movimiento será transparente para los clientes:

* La longitud de cada ola de migración puede variar según el número de instancias de Campaign afectadas. Cuando se programa una ola de migración, la notificación incluirá la duración esperada.

* Las instancias de Campaign no podrán enviar correos electrónicos durante la ventana de migración. Ninguna otra función de Campaign se verá afectada.


## Preguntas frecuentes {#aws-faq}

* **¿Por qué es una actualización obligatoria?**

  Adobe planea eliminar el antiguo centro de datos, las instancias de Adobe Campaign que se ejecuten allí deben transferirse al nuevo centro de datos de referencia, Amazon Web Service (AWS).

  La nube de Adobe Managed Services está alojada en Amazon Web Service (AWS), un entorno moderno, seguro y optimizado. [Más información sobre Amazon Web Service](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}.

* **¿Cuáles son los clientes objetivo de esta migración?**

  Todos los clientes de la versión 8 de Campaign y Campaign Classic v7 hybrid, alojados y Campaign Managed Services verán migrados sus entornos. Los clientes de Campaign Standard también se ven afectados.

* **¿Cuál es el tiempo de inactividad esperado?**

  Se espera que la migración tarde entre 30 y 60 minutos, pero la longitud de cada ola de migración puede variar según el número de instancias de Campaign afectadas. Cuando se programa una ola de migración, la notificación incluirá la duración esperada.

* **¿El cliente requiere alguna acción para la migración?**

  No se requiere ninguna acción, ya que Adobe ejecutará automáticamente la migración.

* **¿Qué validaciones deben ejecutar los clientes?**

  No se necesitan pruebas específicas para esta migración. Si se observa algún problema, comuníquese con el [Servicio de atención al cliente de Adobe](https://experienceleague.adobe.com/es?support-solution=Campaign#support){target="_blank"}.


* **¿Puedo solicitar un cambio de fecha y hora en el intervalo programado de actualización de seguridad?**

  Dado que se trata de una migración obligatoria, no podemos admitir modificaciones en la programación existente.

Para cualquier otra pregunta, puede contactar con el [Servicio de atención al cliente de Adobe](https://experienceleague.adobe.com/es?support-solution=Campaign#support){target="_blank"}.
