---
title: Matriz de compatibilidad de Campaign v8
description: Descubra los sistemas y las versiones compatibles con Campaign v8
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 100%

---

# Matriz de compatibilidad de Campaign v8

Este documento enumera todos los sistemas y componentes compatibles con la última versión de **Adobe Campaign v8**. A menos que se indique lo contrario, se admiten todas las versiones secundarias. Los productos y las versiones que no forman parte de esta lista no son compatibles con Adobe Campaign.

Cuando las versiones específicas de estos sistemas y herramientas de terceros llegan al final de su vida útil (EOL), Adobe Campaign ya no es compatible con ellas y se eliminan de esta matriz de compatibilidad. Para evitar problemas, compruebe que tiene una versión compatible de cualquier sistema enumerado en la matriz de compatibilidad.

>[!NOTE]
>
>Adobe Campaign Server y Client Console deben tener la misma versión. [Obtenga información sobre cómo comprobar su versión](#version).

## Consola del cliente{#ClientConsoleoperatingsystems}

Se requieren los siguientes sistemas operativos y exploradores para utilizar la consola del cliente de Campaign. [Más información](connect.md).

### Sistemas operativos

* **Microsoft Windows Server** 2019, 2016, 2012
* **Microsoft Windows** 11 (a partir de la versión 8.3 de Campaign), 10, 8

>[!NOTE]
>
>Microsoft Windows 10 es recomendado para instancias japonesas.

### Explorador

**Microsoft Edge**

### Tiempo de ejecución de Microsoft WebView2

<table>
<tbody>
<tr>
<td>
<p>Tiempo de ejecución de Microsoft Edge WebView2
</p>
</td>
<td>
<p>Última versión</p>
</td>
<td>
<p><a href="http://www.adobe.com/go/acc-ms-webview2-runtime-download_es">Descargar del sitio web de Microsoft Developer</a></p>
</td>
</tr>
</tbody>
</table>

## Conectores CRM{#CRMconnectors}

A continuación, se enumeran los sistemas de administración de la relación con los clientes (CRM) compatibles con Adobe Campaign. [Más información](../connect/crm.md).

* **** Versión 49 de la API de conector de Salesforce
* Conector de **Microsoft Dynamics**, API web: Dynamics 365 local y en línea

## Acceso de datos federado (FDA){#FederatedDataAccessFDA}

A continuación, se enumeran las bases de datos externas compatibles con el módulo de acceso de datos federado (FDA) de Adobe Campaign. [Más información](../connect/fda.md).

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## SDK móvil{#MobileSDK}

Puede utilizar Campaign para enviar [notificaciones push](../send/push.md) a los sistemas operativos que se enumeran a continuación mediante el SDK móvil asociado.

* **Android** 12 (a partir de la versión 8.3 de Campaign), 9.0, 8.x, 7.x, con la compilación 1.1.1 del SDK de Android de Campaign.
* **iOS de Apple** 9 - 16 con la compilación 1.0.26 del iOS SDK de Campaign, compatible con las versiones de 32 y 64 bits. iOS 16 es compatible a partir de la versión 8.3 de Campaign.

## Acceso web

Los siguientes exploradores son compatibles con Campaign para [Web Access](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versiones más recientes)

## Comprobación de la versión y compilación de Campaign{#version}

Utilice el menú **Ayuda > Acerca de...** para comprobar su versión.

![](assets/ac-version.png)

Puede acceder a la siguiente información:

* El **número de versión** de la consola del cliente y del servidor de aplicaciones. En el ejemplo anterior, la versión es 8.1.5 tanto para la consola del cliente como para el servidor de aplicaciones.
* El número SHA, entre paréntesis.
* Un vínculo para ponerse en contacto con el Servicio de atención al cliente de Adobe.
* Vínculos a la Política de privacidad de Adobe, a las Condiciones de uso y a la Política de cookies.
