---
title: Introducción a las funcionalidades de seguimiento y monitorización
description: Introducción a las funcionalidades de seguimiento y monitorización
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f3de901f-519f-42ae-846c-f20c7cb560df
source-git-commit: 00a88cf9217faf32070a3cd34a2c1ae5243d9a6e
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 50%

---

# Seguimiento y monitorización de mensajes{#gs-ac-reports}

## Capacidades de seguimiento en Campaign

Las funcionalidades de seguimiento de campañas hacen un seguimiento de los mensajes enviados y ayudan a analizar el comportamiento de los destinatarios: abrir, hacer clic en vínculos, suscripciones/cancelar suscripción, etc. Puede acceder a registros, informes y métricas específicos, consultar la base de datos para revisar los datos recopilados, etc.

Para obtener más información, consulte la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#tracking-tab){target=&quot;_blank&quot;}.

El panel de envío es una herramienta clave para monitorizar los envíos y los problemas potenciales durante el envío de mensajes.

Para obtener más información, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

A continuación se enumeran las funciones de seguimiento clave disponibles en Campaign.

### Seguimiento de mensajes {#message-tracking}

<img src="assets/do-not-localize/icon-message-tracking.svg" width="60px">

**Vínculos seguidos**

Puede realizar un seguimiento de la recepción de mensajes y de la activación de los vínculos insertados en el contenido del mensaje para comprender mejor el comportamiento de los destinatarios.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html?lang=en#sending-messages){target=&quot;_blank&quot;}

**Seguimiento de URL**

Las opciones de seguimiento se pueden configurar activando o desactivando las direcciones URL rastreadas.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/personalizing-url-tracking.html?lang=en#sending-messages){target=&quot;_blank&quot;}


**Personalización de vínculos rastreados**

Las funciones de seguimiento de Campaign le permiten añadir vínculos en correos electrónicos que se pueden personalizar y que admiten el seguimiento.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/tracking-personalized-links/tracking-personalized-links.html?lang=en#sending-messages){target=&quot;_blank&quot;}

**Registros de seguimiento**

La variable **Seguimiento** flujo de trabajo técnico recupera los datos de seguimiento una vez que se ha realizado el envío y se ha activado el seguimiento. Estos datos se encuentran en la pestaña Seguimiento del envío.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/accessing-the-tracking-logs.html?lang=en#sending-messages){target=&quot;_blank&quot;}

**Seguimiento de pruebas**

Antes de enviar los mensajes con el seguimiento, puede probar el seguimiento en su página espejo, los registros de correo electrónico y los vínculos.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/testing-tracking.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### Seguimiento de aplicaciones web {#web-application-tracking}

<img src="assets/do-not-localize/icon-web-app.svg" width="60px">

**Seguimiento de una aplicación web**

También puede rastrear y medir visitas en páginas de aplicación web con etiquetas de seguimiento. Esta funcionalidad se puede utilizar para todos los tipos de aplicaciones web, como formularios y encuestas en línea.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/tracking-a-web-application.html?lang=en#designing-content){target=&quot;_blank&quot;}

**Exclusión del seguimiento de aplicaciones web**

La exclusión del seguimiento de aplicaciones web le permite detener el seguimiento de los comportamientos web de los usuarios finales que excluyen el seguimiento de comportamiento. Puede incluir la capacidad de mostrar un banner en aplicaciones web o páginas de destino para permitir que los usuarios puedan excluirse.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out.html?lang=en#designing-content){target=&quot;_blank&quot;}

### Seguimiento de informes {#tracking-reports}

<img src="assets/do-not-localize/icon_monitor.svg" width="60px">

**Estadísticas de seguimiento**

Este informe proporciona estadísticas sobre aperturas, clics y transacciones, y le permite rastrear el impacto del envío en marketing.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/about-message-tracking.html?lang=en#tracking-reports){target=&quot;_blank&quot;}

**URL y flujos de clics**

Este informe muestra la lista de páginas visitadas después de una entrega.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#urls-and-click-streams){target=&quot;_blank&quot;}

**Personas y destinatarios**

Comprenda mejor la diferencia de seguimiento entre una persona o personas y un destinatario en Adobe Campaign con este ejemplo.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html?lang=en#reporting){target=&quot;_blank&quot;}

**Indicadores de seguimiento**

Este informe combina los indicadores clave para rastrear el comportamiento de los destinatarios al recibir el envío, tales como las tasas de pulsaciones abiertas y los flujos de clics.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#reporting){target=&quot;_blank&quot;}

**Cálculo de indicador**

Las distintas tablas proporcionan la lista de los indicadores utilizados en los distintos informes y su fórmula de cálculo en función del tipo de envío.

[Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/indicator-calculation.html?lang=en#reporting){target=&quot;_blank&quot;}

## Directrices de monitorización

Adobe Campaign ofrece un conjunto de funcionalidades para supervisar sus procesos y su entorno.

### Monitorización de entregas

La monitorización de las entregas una vez enviadas es un paso clave para garantizar que las campañas de marketing sean eficientes y lleguen a los clientes.

Obtenga más información sobre la información que puede monitorizar después de realizar un envío, comprenda cómo se administran los errores y cuarentenas de envío en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages){target=&quot;_blank&quot;}

### Monitorización de los flujos de trabajo

Obtenga información sobre cómo monitorizar la ejecución del flujo de trabajo en  [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}

### Supervisión de la instancia

Las directrices de monitorización de instancias están disponibles en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/introduction/monitoring-guidelines.html?lang=en#monitoring-campaign-classic){target=&quot;_blank&quot;}

Utilice la interfaz de autoservicio de pista de auditoría para supervisar los cambios realizados dentro de la instancia. La pista de auditoría captura, en tiempo real, una lista completa de las acciones y eventos que se producen dentro de la instancia de Adobe Campaign. Puede acceder a un historial de datos para responder preguntas como: qué ha pasado con sus flujos de trabajo y quién los actualizó por última vez o qué han hecho los usuarios en la instancia.

Obtenga más información sobre la pista de auditoría en  [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/audit-trail.html?lang=en#accessing-audit-trail){target=&quot;_blank&quot;}
