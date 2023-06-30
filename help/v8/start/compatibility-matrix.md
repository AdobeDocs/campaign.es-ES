---
title: Matriz de compatibilidad de Campaign v8
description: Descubra los sistemas y las versiones compatibles con Campaign v8
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 89%

---

# Matriz de compatibilidad de Campaign v8

Este documento enumera todos los sistemas y componentes compatibles con la última versión de **Adobe Campaign v8**. A menos que se indique lo contrario, se admiten todas las versiones secundarias. Los productos y las versiones que no forman parte de esta lista no son compatibles con Adobe Campaign.

Cuando las versiones específicas de estos sistemas y herramientas de terceros llegan al final de su vida útil (EOL), Adobe Campaign ya no es compatible con ellas y se eliminan de esta matriz de compatibilidad. Para evitar problemas, compruebe que tiene una versión compatible de cualquier sistema enumerado en la matriz de compatibilidad.

>[!NOTE]
>
>Adobe Campaign Server y Client Console deben tener la misma versión. [Obtenga información sobre cómo comprobar su versión](#version).

## Consola del cliente{#ClientConsoleoperatingsystems}

Se requieren los siguientes sistemas operativos y exploradores para utilizar la consola del cliente de Campaign. [Más información](connect.md).

### Sistemas operativos{#op-systems}

* **Microsoft Windows Server** 2019, 2016, 2012
* **Microsoft Windows** 11, 10, 8

>[!NOTE]
>
>Tenga en cuenta que la versión de 32 bits de la consola del cliente está en desuso a partir de la versión 8.5. A partir de la versión 8.6, la consola de cliente solo estará disponible en 64 bits. Para obtener más información sobre cómo actualizar el sistema operativo, consulte esta [nota técnica](../../technotes/upgrades/console.md).

### Explorador web{#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, última versión. Descárguelo desde el [sitio de Microsoft Developer](http://www.adobe.com/go/acc-ms-webview2-runtime-download_es){target="_blank"}.

## Conectores CRM{#CRMconnectors}

A continuación, se enumeran los sistemas de administración de la relación con los clientes (CRM) compatibles con Adobe Campaign. [Más información](../connect/crm.md).

* **** Versión 49 de la API de conector de Salesforce
* Conector de **Microsoft Dynamics**, API web: Dynamics 365 local y en línea

## Acceso de datos federado (FDA){#FederatedDataAccessFDA}

A continuación, se enumeran las bases de datos externas compatibles con el módulo de acceso de datos federado (FDA) de Adobe Campaign. [Más información](../connect/fda.md).

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**, a partir de la versión 8.5 de Campaign
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## SDK móvil{#MobileSDK}

Para enviar [notificaciones push](../send/push.md) con Campaign, utilice el SDK móvil de Adobe Experience Platform configurando la extensión de Adobe Campaign Classic en la interfaz de usuario de recopilación de datos.


## Acceso web{#web-access}

Los siguientes exploradores son compatibles con Campaign para [Web Access](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versiones más recientes)

## Comprobación de la versión y compilación de Campaign{#version}

Utilice el menú **Ayuda > Acerca de...** para comprobar su versión.

![](assets/ac-version.png)

Puede acceder a la siguiente información:

* El **version** número de la consola del cliente y del servidor de aplicaciones. En el ejemplo anterior, la versión es 8.1.5 tanto para la consola del cliente como para el servidor de aplicaciones.
* El número SHA, entre paréntesis.
* Un vínculo para ponerse en contacto con el Servicio de atención al cliente de Adobe.
* Vínculos a la Política de privacidad de Adobe, a las Condiciones de uso y a la Política de cookies.
