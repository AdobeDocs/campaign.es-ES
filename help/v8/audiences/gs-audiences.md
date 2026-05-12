---
title: Introducción a perfiles y audiencias en Campaign
description: Obtenga información sobre cómo crear y administrar perfiles y audiencias en Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
version: Campaign v8, Campaign Classic v7
TQID: https://experienceleague.adobe.com/rk1-Q8Ghg8L8jSqGNvTRYY0alwUry6l8lPv-GROTfFQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 346
ht-degree: 36%

---

# Introducción a perfiles y públicos{#gs-profiles-and-audiences}

Los perfiles son contactos almacenados en la base de datos de Campaign, como clientes, suscriptores de un servicio o clientes potenciales. Existen muchos mecanismos para adquirir perfiles y desarrollar esta base de datos: recopilación en línea a través de formularios web, importación manual o automática de archivos de texto, replicación con bases de datos de compañías u otros sistemas de información. Con Adobe Campaign, puede incorporar el historial de marketing, la información de compra, las preferencias, los datos CRM y cualquier dato PI relevante en una vista consolidada para analizar y actuar en consecuencia. Los perfiles contienen toda la información necesaria para la segmentación, el cumplimiento y el seguimiento de personas.

Un perfil es un registro de la tabla **nmsRecipient** o una tabla externa que almacena todos los atributos del perfil, como el nombre, los apellidos, la dirección de correo electrónico, un ID de cookie, el ID de cliente, el identificador móvil u otra información relacionada con un canal determinado. Otras tablas vinculadas a la tabla de destinatarios contienen datos relacionados con el perfil, como la tabla de &quot;logs&quot; de envío que contiene registros de todas las entregas realizadas a los destinatarios. Obtenga más información acerca de los perfiles integrados y las tablas de destinatarios en [esta sección](../dev/datamodel.md#ootb-profiles).

![](assets/recipients-in-explorer.png)

En Adobe Campaign, **los destinatarios** son los perfiles predeterminados a los que se dirigen los envíos (correos electrónicos, SMS, etc.).

Los datos de destinatario almacenados en la base de datos permiten filtrar el destinatario que recibirá cualquier envío dado y añadir datos de personalización en el contenido de los envíos. Existen otros tipos de perfiles en la base de datos. Están diseñados para usos diferentes. Por ejemplo se crean perfiles semilla para probar los envíos antes de enviarlos al público objetivo final.

Para rellenar Adobe Campaign con datos de perfil, puede:

* [importar archivos de datos](../start/import.md) desde un origen de datos externo como un sistema CRM o un archivo plano
* [crear formularios web](../dev/webapps.md) para permitir que los clientes introduzcan su propia información y creen su propio perfil
* [asignar a una base de datos externa](../connect/fda.md) donde se almacenan los perfiles
* introduzca los perfiles manualmente en la consola del cliente, como se muestra a continuación:

![](assets/create-profile.png)

Una vez importadas, puede crear audiencias para enviar los mensajes. Aprenda a crear audiencias [en esta sección](create-audiences.md).