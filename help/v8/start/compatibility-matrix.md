---
product: Adobe Campaign
title: Matriz de compatibilidad de Campaign v8
description: Descubra los sistemas y las versiones compatibles con Campaign v8
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: f7e2581899d965975c129cac530a7edc6a2d55dd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 75%

---

# Matriz de compatibilidad de Campaign v8

Este documento enumera todos los sistemas y componentes compatibles con la última versión de **Adobe Campaign v8**. Los productos y las versiones que no forman parte de esta lista no son compatibles con Adobe Campaign.

>[!CAUTION]
>
>* A menos que se indique lo contrario, se admiten todas las versiones menores.
>* Cuando las versiones específicas de estos sistemas y herramientas de terceros llegan al final de su vida útil (EOL), Adobe Campaign ya no es compatible con ellas y se eliminan de esta matriz de compatibilidad. Para evitar problemas, compruebe que tiene una versión compatible de cualquier sistema enumerado en la matriz de compatibilidad.


## Sistemas compatibles

### Consola del cliente{#ClientConsoleoperatingsystems}

:advertencia: Se requieren los siguientes sistemas operativos y exploradores para utilizar la Consola del cliente de Campaign.

**Sistemas operativos**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (recomendado para instancias japonesas))

**Navegador**

**Microsoft Internet Explorer** 11

### Conectores CRM{#CRMconnectors}

* **** Versión 49 de la API de conector Salesforce
* **Conector de Microsoft** Dynamics, API web: Dynamics 365 On-Premise y en línea

### Acceso de datos federado (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Snowflake]**

### SDK móvil{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 con la versión 1.0.27 del SDK móvil.
* **Apple iOS** 9 -14 con la versión 1.0.26 del SDK móvil, compatible con las versiones de 32 y 64 bits.

### Navegadores admitidos {#Browsers}

Los siguientes exploradores son compatibles con Campaign for Web Access.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versiones más recientes)

* **Internet Explorer** 11

## Comprobación de la versión de Campaign y generar

Utilice el menú **Help > About...** para comprobar su versión.

![](assets/ac-version.png)

Puede acceder a la siguiente información:

* El número **version** de la consola del cliente y del servidor de aplicaciones. En el ejemplo anterior, la versión es 8.1.5 tanto para la consola del cliente como para el servidor de aplicaciones.
* El número SHA, entre paréntesis.
* Un vínculo para ponerse en contacto con el Servicio de atención al cliente de Adobe.
* Vínculos a la Política de privacidad de Adobe, Condiciones de uso y Política de cookies.
