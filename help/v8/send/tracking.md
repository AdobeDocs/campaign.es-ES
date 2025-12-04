---
title: Introducción al seguimiento de mensajes
description: Obtenga más información acerca de las funcionalidades de seguimiento en Adobe Campaign
feature: Monitoring, Email
role: User
level: Beginner
exl-id: f3de901f-519f-42ae-846c-f20c7cb560df
source-git-commit: 57e177dc6c30502f2ed3bb08b18586fa5399e89c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 32%

---

# Introducción al seguimiento de mensajes {#get-started-tracking}

Gracias a sus funciones de seguimiento, Adobe Campaign le permite hacer un seguimiento de los mensajes enviados y comprobar el comportamiento de los destinatarios: aperturas de mensajes, clics en vínculos, bajas, etc.

Esta información se recupera en la pestaña **[!UICONTROL Tracking]** del perfil de cada destinatario de la entrega. Esta pestaña presenta todos los vínculos de URL rastreados y seleccionados por el destinatario seleccionado de la lista. Esta es la acumulación de todas las direcciones URL rastreadas en las entregas que aún están presentes en la pantalla de envío. La lista se puede configurar y normalmente contiene: la dirección URL donde se hizo clic, la fecha y la hora del clic y el documento en el que se encontró la URL.

El **tablero de entregas** también es una herramienta clave para monitorizar las entregas y los problemas potenciales durante la entrega de mensajes.

El siguiente diagrama muestra las etapas del diálogo entre el usuario y los distintos servidores.

<img src="assets/tracking-diagram.png" width="70%">

>[!NOTE]
>
>La configuración de seguimiento la realiza Adobe para implementaciones de Cloud Services administrados.

## Seguimiento de mensajes {#message-tracking}

**Vínculos seguidos**

Puede realizar un seguimiento de la recepción de mensajes y de la activación de los vínculos insertados en el contenido del mensaje para comprender mejor el comportamiento de los destinatarios.

[Más información sobre los vínculos rastreados](tracked-links.md)

**Seguimiento de URL**

Las opciones de seguimiento se pueden configurar activando o desactivando las direcciones URL rastreadas.

[Más información acerca de las opciones de seguimiento de URL](url-tracking.md)

**Personalización de vínculos rastreados**

Las funciones de seguimiento de campañas le permiten añadir vínculos en correos electrónicos que se pueden personalizar y que admiten el seguimiento.

[Más información sobre el seguimiento de vínculos personalizados](personalized-links.md)

**Registros de seguimiento**

El flujo de trabajo técnico **Tracking** recupera los datos de seguimiento una vez que se ha enviado el envío y se ha activado el seguimiento. Estos datos se encuentran en la pestaña Seguimiento del envío.

[Más información sobre los registros de seguimiento](tracking-logs.md)

**Seguimiento de pruebas**

Antes de enviar los mensajes con el seguimiento, puede probar el seguimiento en la página espejo, los registros de correo electrónico y los vínculos.

[Más información sobre las pruebas de seguimiento](testing-tracking.md)

## Seguimiento de informes {#tracking-reports}

**Estadísticas de seguimiento**

Este informe proporciona estadísticas sobre aperturas, clics y transacciones, y le permite rastrear el impacto del envío en marketing.

[Más información sobre el seguimiento de informes](../reporting/delivery-reports.md#tracking-indicators)

**URL y flujos de clics**

Este informe muestra la lista de páginas visitadas después de una entrega.

[Obtenga más información sobre las URL y las secuencias de clics](../reporting/delivery-reports.md#urls-and-click-streams)

**Personas y destinatarios**

Comprenda mejor la diferencia de seguimiento entre una persona o personas y un destinatario en Adobe Campaign con este ejemplo.

[Más información sobre las personas y los destinatarios objetivo](../reporting/metrics-calculation.md#targeted-persons---recipients)

**Indicadores de seguimiento**

Este informe combina los indicadores clave para rastrear el comportamiento de los destinatarios al recibir la entrega, como las tasas de pulsaciones abiertas y los flujos de clics.

[Más información sobre los indicadores de seguimiento](../reporting/delivery-reports.md#tracking-indicators)

**Cálculo de indicador**

Las distintas tablas proporcionan la lista de los indicadores utilizados en los distintos informes y su fórmula de cálculo en función del tipo de envío.

[Más información sobre el cálculo del indicador](../reporting/metrics-calculation.md)


