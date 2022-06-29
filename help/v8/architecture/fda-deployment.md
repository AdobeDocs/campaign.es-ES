---
title: Introducción a la implementación del Snowflake FDA de Campaign
description: Introducción a la implementación del Snowflake FDA de Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 5c1ced7972295e79418ac7ff14a6f0888e5ed39a
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign] FDA [!DNL Snowflake] implementación{#gs-fda-snowflake}

En un [!DNL Snowflake] Implementación de FDA (predeterminada), [!DNL Adobe Campaign] v8 está conectado a [!DNL Snowflake] para acceder a los datos a través de [Acceso de datos federado](../connect/fda.md) capacidad: puede acceder a los datos y la información externos almacenados en su [!DNL Snowflake] base de datos sin cambiar la estructura de los datos de Adobe Campaign.

## Ventajas{#fda-benefits}

Este modelo de implementación ofrece las siguientes ventajas:

* **Almacenamiento y performance**
Puede mover los datos históricos a [!DNL Snowflake] y luego reducir las dependencias al límite de Adobe Campaign ID. Esta arquitectura también reduce su dependencia a los límites de almacenamiento y performance de PostgreSQL. A medida que se almacenan menos datos en la base de datos de Campaign, el rendimiento es mejor y las tareas de mantenimiento se realizan más rápido.

* **Extensión del modelo de datos y administración de datos**
Puede crear tablas en [!DNL Snowflake] y vincularlos a Adobe Campaign, por ejemplo para utilizar datos archivados durante períodos de retención o ejecutar procesos de segmentación con un rendimiento excepcional.

   Esta arquitectura también le permite utilizar las funcionalidades del flujo de trabajo de administración de datos en [!DNL Snowflake]. Solo los agregados y las tablas temporales se mueven a Campaign para fines de personalización y envío.


## Arquitectura{#fda-archi}

Con este modelo de implementación, los usuarios de Adobe Campaign pueden ampliar sus datos a [!DNL Snowflake] y aproveche los beneficios de una plataforma de datos única e integrada para obtener información de datos de campañas de marketing potentes en tiempo real. Proporciona a los usuarios la capacidad de desbloquear el valor profundo de sus datos ofreciendo una plataforma única, unificada y fácil de usar para el análisis de datos. La plataforma de datos en la nube no requiere administración, ya que se escala infinitamente para admitir cualquier volumen de datos de marketing de Adobe Campaign.

La comunicación general entre servidores y procesos se realiza según el esquema siguiente:

![](assets/fda-architecture.png)

PostgreSQL es la base de datos principal y Snowflake es la base de datos secundaria. Puede ampliar el modelo de datos y almacenar los datos en el Snowflake. Posteriormente, puede ejecutar ETL, segmentación e informes sobre un gran conjunto de datos con un rendimiento excepcional.
