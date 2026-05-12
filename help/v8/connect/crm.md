---
title: Trabaje con Campaign y su CRM
description: Aprenda a trabajar con Campaign y su CRM
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
version: Campaign v8, Campaign Classic v7
TQID: https://experienceleague.adobe.com/gYGdySWZC1j2VkvAkL9rVBes7iQvRkRjNjm-dvFsHBM
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: beb7a3c1-66ab-4786-b879-7621375b3c40id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 339
ht-degree: 35%

---

# Conexión de su CRM con Campaign {#gs-crm}

Adobe Campaign ofrece varios conectores CRM para vincular la plataforma de Adobe Campaign a los sistemas de terceros. Estos conectores de CRM le permiten sincronizar contactos, cuentas, compras, etc., para facilitar la integración de la aplicación con diversas aplicaciones de terceros y de negocios.

Estos conectores permiten una integración de datos rápida y sencilla: Adobe Campaign proporciona un asistente dedicado para recopilar y seleccionar información de las tablas disponibles en CRM. De este modo, se garantiza la sincronización bidireccional para asegurar que los datos estén actualizados en todo momento en todos los sistemas.

Las ventajas principales son:

* Mensajería coherente entre ventas y marketing: la integración de Adobe Campaign con su CRM proporciona a ambos sistemas acceso a insight del cliente e historial de marketing por correo electrónico, lo que permite que todos los mensajes al cliente compartan la misma mensajería coherente.

* Vista holística de todos los datos de clientes y clientes potenciales: al integrar Adobe Campaign con su CRM, es posible compartir y acceder al historial de marketing por correo electrónico en cada contacto desde el sistema CRM.

* Active los datos CRM en cualquier canal: con los datos de contacto sincronizados con Adobe Campaign, las comunicaciones se pueden enviar en cualquier canal en línea o sin conexión con Campaign, incluidas las notificaciones push móviles, en la aplicación, por correo electrónico o por correo directo.


>[!NOTE]
>
>Esta función está disponible en Adobe Campaign a través del paquete de **conectores de CRM** dedicados.

## Sistemas compatibles {#compatible-crm-systems-and-limitations}

Los CRM y versiones compatibles se detallan en la [matriz de compatibilidad de Campaign](../start/compatibility-matrix.md).

>[!CAUTION]
>
> Los conectores CRM de Campaign solo funcionan con una URL segura (https).

## Pasos de implementación {#crm-implementation-steps}

Aprenda el procedimiento paso a paso para conectar Campaign y Microsoft Dynamics en [esta página](ac-ms-dyn.md).

Aprenda el procedimiento paso a paso para conectar Campaign y Salesforce.com en [esta página](ac-sfdc.md).

La sincronización de datos entre Adobe Campaign y CRM se lleva a cabo mediante una actividad de flujo de trabajo dedicada. Cree sus flujos de trabajo para automatizar la sincronización entre Campaign y CRM. Puede crear un flujo de trabajo que importe los contactos a través de Microsoft Dynamics, los sincronice con los datos de Adobe Campaign existentes, elimine los contactos duplicados y, a continuación, actualice la base de datos de Adobe Campaign. Obtenga más información en [esta página](crm-data-sync.md).
