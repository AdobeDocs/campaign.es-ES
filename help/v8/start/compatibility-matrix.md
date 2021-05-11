---
solution: Campaign
product: Adobe Campaign
title: Matriz de compatibilidad de Campaign v8
description: Aprenda los sistemas y las versiones compatibles con Campaign v8
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
translation-type: tm+mt
source-git-commit: 3fe4156149e9ff8724dd1ff5fc17b538e6055ef8
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 32%

---

# Matriz de compatibilidad de Campaign v8

Este documento enumera todos los sistemas y componentes compatibles con la última versión de **Adobe Campaign v8**. Los productos y las versiones que no forman parte de esta lista no son compatibles con Adobe Campaign.

>[!CAUTION]
>
>* A menos que se indique lo contrario, se admiten todas las versiones menores.
>* A medida que las versiones específicas de estos sistemas y herramientas de terceros llegan al final de su vida útil (EOL), Adobe Campaign ya no es compatible con ellas y se eliminan de esta matriz de compatibilidad. Para evitar problemas, compruebe que se encuentra en una versión compatible de cualquier sistema enumerado en la matriz de compatibilidad.


## Sistemas compatibles

### Conectores CRM{#CRMconnectors}

* **** Versión 49 de la API de SalesforceConnector
* **Conector de Microsoft** Dynamics, API web: Dynamics 365 On-Premise y en línea

### Acceso de datos federado (FDA){#FederatedDataAccessFDA}

* **Microsoft Azure Synapse Analytics**
* **Amazon Redshift**
* **[!DNL Snowflake]**
* **Oracle** 19c, 18c, 12c, 11G
* **PostgreSQL** 12.x, 11.x, 10.x, 9.6.x, 9.5.x, 9.4.x
* **Microsoft SQL Server** 2019, 2017, 2016, 2014, 2012 SP1 y SP2
* **MySQL** 5.7
* **Teradata** 16.20, 16, 15.10, 15.0
* **Netezza** 7.2
* **sybase IQ** 16, ASE 15.7
* **SAP** HANAversion 1 SPS 12
* **Hadoop a través de HiveSQL**
   * HortonWorks HDP 2.4.X, 2.5.x, 2.6.x
   * HDInsight 3.4 (HDP 2.4), 3.5 (HDP 2.5), 3.6 (HDP 2.6
   * Cloudera CDH6.x

### Consola del cliente{#ClientConsoleoperatingsystems}

:advertencia: Se requieren los siguientes sistemas operativos y exploradores para utilizar la Consola de cliente de Campaign.

**Sistemas operativos**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (recomendado para instancias japonesas)

**Navegador**

<table>
<tbody>
<tr>
<td>
<p>Microsoft Internet Explorer</p>
</td>
<td>
<p>11</p>
</td>
</tr>
</tbody>
</table>

### Mobile SDK{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 con la versión 1.0.27 del SDK móvil.
* **Apple iOS** 9 - 14 con la versión 1.0.26 del SDK móvil, compatible con las versiones de 32 y 64 bits.

### Navegadores admitidos {#Browsers}

Los siguientes exploradores son compatibles con Campaign for Web Access.

* **Microsoft Edge**,  **Mozilla Firefox**,  **Google Chrome**,  **Safari**  (versiones más recientes)

* **Internet Explorer** 11

## Cómo comprobar la versión de Campaign

El menú **Help > About...** le permite acceder a la siguiente información:

* el número de versión de la consola del cliente de Campaign y del servidor de aplicaciones
* el número de registro para la consola del cliente de Campaign y el servidor de aplicaciones
* un vínculo para ponerse en contacto con el Servicio de atención al cliente de Adobe
* vínculos a la Política de privacidad de Adobe, a las Condiciones de uso y a la Política de cookies
