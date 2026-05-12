---
title: Introducción a la implementación de FDA de Campaign
description: Introducción a la implementación de FDA de Campaign
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
TQID: https://experienceleague.adobe.com/PfXTlEYfwkN9YRDIx44TdtZLjNZJkHqN73sJGxA0c-E
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: ee3dfd63-9a21-4961-9f24-ea3385284a21
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 329
ht-degree: 0%

---

# Implementación de FDA [!DNL Campaign]{#gs-fda}

En su implementación de FDA de Campaign (predeterminada), [!DNL Adobe Campaign] v8 se puede conectar a [!DNL Snowflake] para acceder a los datos a través de la capacidad [Acceso de datos federado](../connect/fda.md): a continuación, podrá acceder a los datos externos y a la información almacenada en su base de datos [!DNL Snowflake] y procesarlos sin cambiar la estructura de los datos de Adobe Campaign.

>[!NOTE]
>
>En este modelo de implementación, la base de datos secundaria [!DNL Snowflake] solo está disponible bajo solicitud. Para que se actualice la implementación con [!DNL Snowflake], póngase en contacto con el administrador de transición de Adobe.
>

## Ventajas{#fda-benefits}

Este modelo de implementación ofrece las siguientes ventajas:

* **Rendimiento y almacenamiento**
Puede mover los datos históricos a [!DNL Snowflake] y, a continuación, reducir las dependencias al límite de Adobe Campaign ID. Esta arquitectura también reduce su dependencia de los límites de almacenamiento y rendimiento de PostgreSQL. A medida que se almacenan menos datos en la base de datos de Campaign, el rendimiento es mejor y las tareas de mantenimiento se realizan más rápido.

* **Administración y extensión del modelo de datos**
Puede crear tablas en [!DNL Snowflake] y vincularlas a Adobe Campaign, por ejemplo, para utilizar datos archivados durante períodos de retención o ejecutar procesos de segmentación con un rendimiento sobresaliente.

  Esta arquitectura también le permite usar las capacidades del flujo de trabajo de administración de datos en [!DNL Snowflake]. Solo los agregados y las tablas temporales se mueven a Campaign con fines de personalización y envío.


## Arquitectura{#fda-archi}

Con este modelo de implementación, los usuarios de Adobe Campaign pueden extender sus datos a [!DNL Snowflake] y aprovechar las ventajas de una sola plataforma de datos integrada para obtener información valiosa de los datos de las campañas de marketing en tiempo real. Proporciona a los usuarios la capacidad de desbloquear valores profundos de sus datos al ofrecer una plataforma única, unificada y fácil de usar para el análisis de datos. La plataforma de datos en la nube no requiere administración, ya que se escala infinitamente para admitir cualquier volumen de datos de marketing de Adobe Campaign.

La comunicación general entre servidores y procesos se realiza según el siguiente esquema:

![](assets/fda-architecture.png)

PostgreSQL es la base de datos principal y Snowflake se puede utilizar como base de datos secundaria. Puede ampliar el modelo de datos y almacenar los datos en Snowflake. Posteriormente, puede ejecutar ETL, segmentación e informes en un conjunto de datos grande con un rendimiento sobresaliente.
