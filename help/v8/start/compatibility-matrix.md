---
title: Matriz de compatibilidad de Campaign v8
description: Descubra los sistemas y las versiones compatibles con Campaign v8
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: 1857f0f40d554abededfaa0c1e3dec4b57ca23b7
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 100%

---

# Matriz de compatibilidad de Campaign v8 {#compat-matrix}

En este documento se indican todos los sistemas y componentes compatibles con la última versión de la consola del cliente de **Adobe Campaign v8**. A menos que se indique lo contrario, se admiten todas las versiones secundarias. Los productos y las versiones que no forman parte de esta lista no son compatibles con Adobe Campaign.

Cuando las versiones específicas de estos sistemas y herramientas de terceros llegan al final de su vida útil (EOL), Adobe Campaign ya no es compatible con ellas y se eliminan de esta matriz de compatibilidad. Para evitar problemas, compruebe que tiene una versión compatible de cualquier sistema enumerado en la matriz de compatibilidad.

>[!NOTE]
>
>El servidor de Adobe Campaign Server y la consola del cliente de Campaign deben tener la misma versión. [Obtenga información sobre cómo comprobar su versión](upgrades.md#version).

## Consola del cliente {#ClientConsoleoperatingsystems}

Se requieren los siguientes sistemas operativos y exploradores para utilizar la consola del cliente de Campaign. [Más información](connect.md).

### Sistemas operativos {#op-systems}

* **Microsoft Windows Server** 2019, 2016
* **Microsoft Windows** 11, 10

>[!NOTE]
>La versión de 32 bits de la consola del cliente ha quedado obsoleta desde la versión 8.5. A partir de la versión 8.6, la consola de cliente solo estará disponible en 64 bits. Para obtener más información sobre cómo actualizar su sistema operativo, consulte esta [nota técnica](../../technotes/upgrades/console.md).

### Explorador web {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, última versión. Descárguelo desde el [sitio de Microsoft Developer](http://www.adobe.com/go/acc-ms-webview2-runtime-download_es){target="_blank"}.

## Conectores CRM {#CRMconnectors}

A continuación se enumeran los sistemas de gestión de relaciones con el cliente (CRM) compatibles con Adobe Campaign. Obtenga más información sobre los conectores CRM en [esta página](../connect/crm.md).

* **** Versión 49 de la API de conector de Salesforce
* Conector de **Microsoft Dynamics**, API web: Dynamics 365 local y en línea

## Acceso de datos federado (FDA){#FederatedDataAccessFDA}

A continuación, se enumeran las bases de datos externas compatibles con el módulo de acceso de datos federado (FDA) de Adobe Campaign. Obtenga más información sobre FDA en [esta página](../connect/fda.md).

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**, a partir de la versión 8.5 de Campaign
* **[!DNL Databricks]**, a partir de la versión 8.7 de Campaign
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## SDK móvil {#MobileSDK}

Para enviar [notificaciones push](../send/push.md) con Campaign, utilice el SDK móvil de Adobe Experience Platform configurando la extensión de Adobe Campaign Classic en la interfaz de usuario de recopilación de datos.

Las versiones compatibles con iOS y Android se detallan en la [documentación de Adobe Developer](https://developer.adobe.com/client-sdks/home/){target="_blank"}.

## Interfaz de usuario web {#web-ui}

Los siguientes exploradores son compatibles con la interfaz de usuario web de Campaign. Obtenga más información sobre la IU web de Campaign [en esta página](campaign-ui.md#ac-web-ui).

* **Microsoft Edge**, **Google Chrome**, **Safari** (versiones más recientes)

## Acceso web {#web-access}

Los siguientes exploradores son compatibles con Campaign for Web Access. Obtenga más información sobre Campaign Web Access [en esta página](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versiones más recientes)

## Recursos adicionales {#support}

* [Actualizaciones de la versión de Campaign](upgrades.md)
* [Compruebe su versión de Campaign](upgrades.md#version)
* [Instalación de la consola del cliente de Campaign](connect.md)
* [Versiones del Panel de control](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=es){target="_blank"}

Para recibir información sobre las nuevas versiones de la solución Experience Cloud, suscríbase para recibir la [actualización de producto prioritaria de Adobe](https://www.adobe.com/es/subscription/priority-product-update.html){target="_blank"}.