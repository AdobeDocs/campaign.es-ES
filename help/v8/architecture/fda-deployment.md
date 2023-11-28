---
title: Introducción a la implementación de FDA de Campaign
description: Introducción a la implementación de FDA de Campaign
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 561e4b6d2c99e98e068132c80c2bebb756b60a44
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# [!DNL Campaign] Implementación de FDA{#gs-fda}

En su implementación FDA de Campaign (predeterminada), [!DNL Adobe Campaign] v8 se puede conectar a [!DNL Snowflake] para acceder a los datos mediante [Acceso de datos federado](../connect/fda.md) capacidad: a continuación, puede acceder a datos externos e información almacenada en su [!DNL Snowflake] base de datos sin cambiar la estructura de los datos de Adobe Campaign.

>[!NOTE]
>
>En este modelo de implementación, la variable [!DNL Snowflake] la base de datos secundaria solo está disponible bajo petición. Para actualizar la implementación con [!DNL Snowflake], póngase en contacto con el administrador de transición de Adobe.
>

## Ventajas{#fda-benefits}

Este modelo de implementación ofrece las siguientes ventajas:

* **Almacenamiento y rendimiento**
Puede mover los datos históricos a [!DNL Snowflake] y, a continuación, reduzca las dependencias al límite de Adobe Campaign ID. Esta arquitectura también reduce su dependencia de los límites de almacenamiento y rendimiento de PostgreSQL. A medida que se almacenan menos datos en la base de datos de Campaign, el rendimiento es mejor y las tareas de mantenimiento se realizan más rápido.

* **Administración y extensión del modelo de datos**
Puede crear tablas en [!DNL Snowflake] y vincularlos a Adobe Campaign, por ejemplo, para utilizar datos archivados durante períodos de retención o ejecutar procesos de segmentación con rendimientos excepcionales.

  Esta arquitectura también le permite utilizar las funcionalidades de flujo de trabajo de gestión de datos en [!DNL Snowflake]. Solo los agregados y las tablas temporales se mueven a Campaign con fines de personalización y envío.


## Arquitectura{#fda-archi}

Con este modelo de implementación, los usuarios de Adobe Campaign pueden ampliar sus datos a [!DNL Snowflake] y aproveche las ventajas de una plataforma de datos única e integrada para obtener información valiosa de los datos de las campañas de marketing en tiempo real. Proporciona a los usuarios la capacidad de desbloquear valores profundos de sus datos al ofrecer una plataforma única, unificada y fácil de usar para el análisis de datos. La plataforma de datos en la nube no requiere administración, ya que se escala infinitamente para admitir cualquier volumen de datos de marketing de Adobe Campaign.

La comunicación general entre servidores y procesos se realiza según el siguiente esquema:

![](assets/fda-architecture.png)

PostgreSQL es la base de datos principal y Snowflake se puede utilizar como base de datos secundaria. Puede ampliar el modelo de datos y almacenar los datos en Snowflake. Posteriormente, puede ejecutar ETL, segmentación e informes en un conjunto de datos grande con un rendimiento sobresaliente.
