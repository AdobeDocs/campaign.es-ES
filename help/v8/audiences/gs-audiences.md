---
title: Introducción a perfiles y audiencias en Campaign
description: Aprenda a crear y administrar perfiles y audiencias en Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 36%

---

# Introducción a perfiles y audiencias en Campaign{#gs-profiles-and-audiences}

Los perfiles son contactos almacenados en la base de datos de Campaign, como clientes, suscriptores a un servicio o posibles clientes. Existen muchos mecanismos para adquirir perfiles y desarrollar esta base de datos: recopilación en línea a través de formularios web, importación manual o automática de archivos de texto, replicación con bases de datos de compañías u otros sistemas de información. Con Adobe Campaign, puede incorporar el historial de marketing, la información de compra, las preferencias, los datos CRM y cualquier dato PI relevante en una vista consolidada para analizar y actuar en consecuencia. Los perfiles contienen toda la información necesaria para la segmentación, calificación y seguimiento de personas.

Un perfil es un registro de la variable **nmsRecipient** o una tabla externa que almacena todos los atributos de perfil, como el nombre, los apellidos, la dirección de correo electrónico, un ID de cookie, el ID de cliente, el identificador móvil u otra información relacionada con un canal determinado. Otras tablas vinculadas a la tabla de destinatarios contienen datos relacionados con el perfil, por ejemplo, la tabla de registros de envío que contiene registros de todas las entregas realizadas a los destinatarios. Obtenga más información sobre los perfiles integrados y las tablas de destinatarios en [esta sección](../dev/datamodel.md#ootb-profiles).

En Adobe Campaign, **recipients** son los perfiles predeterminados dirigidos a los envíos (correos electrónicos, SMS, etc.). Los datos de destinatario almacenados en la base de datos permiten filtrar el destinatario que recibirá cualquier entrega dada y añadir datos de personalización en el contenido de la entrega. Existen otros tipos de perfiles en la base de datos. Están diseñados para usos diferentes. Por ejemplo, se crean perfiles semilla para probar el contenido antes de enviarlo al público objetivo final.


Para rellenar Adobe Campaign con datos de perfil, puede:

* [importar archivos de datos](../start/import.md) desde una fuente de datos externa como un sistema CRM
* [crear formularios web](../dev/webapps.md) para permitir a los clientes introducir su propia información y crear su propio perfil
* [asignar a una base de datos externa](../connect/fda.md) donde se almacenan los perfiles
* introduzca perfiles manualmente en la consola de cliente, como se muestra a continuación:

![](assets/create-profile.png)

<!--You can also select your message audience in an external file: recipients are stored not in the database, but in files. These are known as “external” deliveries. These contacts can be imported or not in Adobe Campaign. [Learn more](external-profiles.md).-->
