---
product: Adobe Campaign
title: Matriz de compatibilidad de Campaign v8
description: Descubra los sistemas y las versiones compatibles con Campaign v8
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 619edce939b39430832fd950ece734f817f9dce3
workflow-type: ht
source-wordcount: '277'
ht-degree: 100%

---

# Matriz de compatibilidad de Campaign v8

Este documento enumera todos los sistemas y componentes compatibles con la última versión de **Adobe Campaign v8**. Los productos y las versiones que no forman parte de esta lista no son compatibles con Adobe Campaign.

>[!CAUTION]
>
>* A menos que se indique lo contrario, se admiten todas las versiones menores.
>* Cuando las versiones específicas de estos sistemas y herramientas de terceros llegan al final de su vida útil (EOL), Adobe Campaign ya no es compatible con ellas y se eliminan de esta matriz de compatibilidad. Para evitar problemas, compruebe que tiene una versión compatible de cualquier sistema enumerado en la matriz de compatibilidad.


## Sistemas compatibles

### Consola del cliente{#ClientConsoleoperatingsystems}

:warning: Se requieren los siguientes sistemas operativos y exploradores para utilizar la consola del cliente de Campaign.

**Sistemas operativos**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (recomendado para instancias japonesas))

**Explorador**

**Microsoft Internet Explorer** 11

### Conectores CRM{#CRMconnectors}

* **** Versión 49 de la API de conector Salesforce
* **Conector de Microsoft** Dynamics, API web: Dynamics 365 On-Premise y en línea

### Acceso de datos federado (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

### SDK móvil{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 con la compilación 1.1.1. de Campaign Android SDK.
* **Apple iOS** 9 - 14 con la compilación 1.0.26 de Campaign iOS SDK, compatible con las versiones de 32 y 64 bits.

### Navegadores admitidos {#Browsers}

Los siguientes exploradores son compatibles con Campaign para Web Access.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (versiones más recientes)

* **Internet Explorer** 11

## Comprobación de la versión de Campaign y la compilación

Utilice el menú **Ayuda > Acerca de...** para comprobar su versión.

![](assets/ac-version.png)

Puede acceder a la siguiente información:

* El **número de versión** de la consola del cliente y del servidor de aplicaciones. En el ejemplo anterior, la versión es 8.1.5 tanto para la consola del cliente como para el servidor de aplicaciones.
* El número SHA, entre paréntesis.
* Un vínculo para ponerse en contacto con el Servicio de atención al cliente de Adobe.
* Vínculos a la Política de privacidad de Adobe, a las Condiciones de uso y a la Política de cookies.
