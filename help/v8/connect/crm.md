---
title: Trabaje con Campaign y su CRM
description: Aprenda a trabajar con Campaign y su CRM
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 79a9d60175b06a11cf27b44275a8ba3fe11e4d3e
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 29%

---

# Conecte su CRM con Campaign {#gs-crm}

Adobe Campaign ofrece varios conectores CRM para vincular la plataforma de Adobe Campaign a los sistemas de terceros. Estos conectores de CRM le permiten sincronizar contactos, cuentas, compras, etc., para facilitar la integración de la aplicación con diversas aplicaciones de terceros y de negocios.

Estos conectores permiten una integración de datos rápida y sencilla: Adobe Campaign proporciona un asistente dedicado para recopilar y seleccionar de las tablas disponibles en CRM. De este modo, se garantiza la sincronización bidireccional para garantizar que los datos estén actualizados en todo momento a lo largo de los sistemas.

Los beneficios principales son:

* Mensajería coherente entre ventas y marketing: la integración de Adobe Campaign con su CRM proporciona a ambos sistemas acceso a la perspectiva del cliente y al historial de marketing por correo electrónico, lo que permite que todos los mensajes al cliente compartan la misma mensajería coherente.

* Vista holística de todos los datos de clientes y posibles clientes: al integrar Adobe Campaign con su CRM, es posible compartir y acceder al historial de marketing por correo electrónico en cada contacto desde el sistema CRM.

* Active sus datos CRM en cualquier canal: con los datos de contacto sincronizados con Adobe Campaign, las comunicaciones se pueden enviar en cualquier canal en línea o sin conexión con Campaign, incluidos los mensajes push, en la aplicación, el correo electrónico o el correo postal móviles.


>[!NOTE]
>
>Esta función está disponible en Adobe Campaign a través del paquete de **conectores de CRM** dedicados.

## Sistemas compatibles {#compatible-crm-systems-and-limitations}

Los CRM y versiones compatibles se detallan en la [matriz de compatibilidad de Campaign](../start/compatibility-matrix.md).

![](../assets/do-not-localize/speech.png)  Los conectores CRM solo funcionan con una URL segura (https).

## Pasos de implementación {#crm-implementation-steps}

Obtenga información sobre el procedimiento paso a paso para conectar Campaign y Microsoft Dynamics en [esta página](ac-ms-dyn.md).

Obtenga información sobre el procedimiento paso a paso para conectar Campaign y Salesforce.com en [esta página](ac-sfdc.md).

La sincronización de datos entre Adobe Campaign y CRM se realiza mediante una actividad de flujo de trabajo dedicada. Cree sus flujos de trabajo para automatizar la sincronización entre Campaign y su CRM. Puede crear un flujo de trabajo que importe los contactos a través de Microsoft Dynamics, los sincronice con los datos de Adobe Campaign existentes, elimine los contactos duplicados y, a continuación, actualice la base de datos de Adobe Campaign.

![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)
