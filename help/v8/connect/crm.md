---
solution: Campaign Classic
product: campaign
title: Trabaje con Campaign y su CRM
description: 'Aprenda a trabajar con Campaign y su CRM '
feature: Información general
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8c9f59067cd0e5a39e84315e5836a32bdf7a0864
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 31%

---

# Conecte su CRM con Campaign {#gs-crm}

Adobe Campaign ofrece varios conectores CRM para vincular la plataforma de Adobe Campaign a los sistemas de terceros. Estos conectores de CRM le permiten sincronizar contactos, cuentas, compras, etc., para facilitar la integración de la aplicación con diversas aplicaciones de terceros y de negocios.

Estos conectores permiten una integración de datos rápida y sencilla: Adobe Campaign proporciona un asistente dedicado para recopilar y seleccionar de las tablas disponibles en CRM. De este modo, se garantiza la sincronización bidireccional para garantizar que los datos estén actualizados en todo momento a lo largo de los sistemas.

>[!NOTE]
>
>Esta función está disponible en Adobe Campaign a través del paquete de **conectores de CRM** dedicados.

## Sistemas compatibles {#compatible-crm-systems-and-limitations}

Los CRM y versiones compatibles se detallan en la [matriz de compatibilidad de Campaign](../start/compatibility-matrix.md).

**NOTA** : Los conectores CRM solo funcionan con una URL segura (https).

## Pasos de implementación {#crm-implementation-steps}

:arrow_upper_right: Obtenga información sobre el procedimiento paso a paso para conectar Campaign y Microsoft Dynamics en la [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)

:arrow_upper_right: Obtenga información sobre el procedimiento paso a paso para conectar Campaign y Salesforce en la [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


La sincronización de datos entre Adobe Campaign y CRM se realiza mediante una actividad de flujo de trabajo dedicada. Cree sus flujos de trabajo para automatizar la sincronización entre Campaign y su CRM. Puede crear un flujo de trabajo que importe los contactos a través de Microsoft Dynamics, los sincronice con los datos de Adobe Campaign existentes, elimine los contactos duplicados y, a continuación, actualice la base de datos de Adobe Campaign.

:arrow_upper_right: Obtenga más información en la [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)

