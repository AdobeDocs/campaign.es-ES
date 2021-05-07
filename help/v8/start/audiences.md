---
solution: Campaign
product: Adobe Campaign
title: Introducción a las audiencias
description: Introducción a las audiencias
feature: Audiencias
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
translation-type: tm+mt
source-git-commit: 81a6d365554d87b020d47be6fd6a896f8ad33d57
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 40%

---

# Introducción a las audiencias{#gs-ac-audiences}

Los perfiles se pueden agrupar en listas o recopilar consultando la base de datos.

## Trabajar con perfiles{#gs-ac-profiles}

Los perfiles están centralizados en la base de datos de la nube. Existen muchos mecanismos para adquirir perfiles y crear esta base de datos: recopilación en línea a través de formularios web, importación manual o automática de archivos de texto, replicación con bases de datos de fabricantes, u otros sistemas de información. Con Adobe Campaign, puede incorporar el historial de marketing, la información de compra, las preferencias, los datos CRM y cualquier dato PI relevante en una vista consolidada para analizar y actuar en consecuencia.

&quot;**Perfil**&quot; significa un registro de información que representa a un cliente, a un cliente potencial, a un suscriptor del boletín informativo, etc.
Un registro de la tabla **nmsRecipient** o una tabla externa contiene un ID de cookie, ID de cliente, identificador móvil u otra información relacionada con un canal determinado. Obtenga más información sobre los perfiles integrados y las tablas de destinatarios en [esta sección](../dev/datamodel.md#ootb-profiles).

En Adobe Campaign, los destinatarios son los perfiles seleccionados por defecto para enviarles contenido (correos electrónicos, SMS, etc.). Los datos de destinatario almacenados en la base de datos permiten filtrar el destinatario que recibirá cualquier entrega dada y añadir datos de personalización en el contenido de la entrega. Existen otros tipos de perfiles en la base de datos. Están diseñados para usos diferentes. Por ejemplo, se crean perfiles semilla para probar el contenido antes de enviarlo al público objetivo final.

:arrow_forward: [Comprender qué es un perfil en video](https://video.tv.adobe.com/v/35611?quality=12)

:arrow_upper_right: Aprenda a administrar perfiles en [esta guía](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html).

## Privacidad y consentimiento

Adobe Campaign es una potente herramienta para recopilar y procesar cantidades extremadamente grandes de datos, incluida información personal e información confidencial. Adobe Campaign le permite recopilar datos, incluida la información personal y confidencial. Por lo tanto, es esencial que reciba y supervise el consentimiento de sus destinatarios.

:arrow_upper_right: Aprenda a administrar la privacidad y el consentimiento en [esta guía](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html).


## Crear listas

Una lista es un conjunto estático de perfiles que puede centrarse en acciones de envío o actualizarse durante operaciones de importación o durante la ejecución del flujo de trabajo. Por ejemplo, una población extraída de la base de datos mediante una consulta puede proporcionar una lista.

:arrow_upper_right: Aprenda a crear y administrar listas en [esta sección](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html).

## Consultar la base de datos

Utilice la actividad **Query** en un flujo de trabajo para consultar la base de datos, segmentar los datos y crear audiencias complejas.

:arrow_upper_right: Obtenga más información sobre las consultas de Campaign en [esta guía](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html).

:arrow_upper_right: Todas las actividades de segmentación se enumeran en [esta página](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)

## Creación de una audiencia en un flujo de trabajo

El objetivo se puede crear mediante una combinación de consultas en una secuencia gráfica de un flujo de trabajo. Puede crear audiencias segmentadas según sus necesidades. Para mostrar el editor de flujo de trabajo, haga clic en la pestaña **[!UICONTROL Targeting and workflows]** del panel de campañas.

:arrow_upper_right: Aprenda a crear una audiencia en un flujo de trabajo de campaña en [esta página]https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)


## Perfiles activos{#active-profiles}

Según el contrato, cada una de las instancias de Campaign se aprovisiona con una cantidad específica de perfiles activos que se contabilizan a efectos de facturación. Consulte su contrato más reciente para obtener una referencia sobre la cantidad de perfiles activos adquiridos.

Por &quot;perfil&quot; se entiende un registro de información (por ejemplo: un registro de la [tabla de destinatarios](../dev/datamodel.md) o una tabla externa que contenga un ID de cookie, ID de cliente, identificador móvil u otra información relacionada con un canal determinado) que represente a un cliente final, a un cliente potencial o a un posible cliente. Los perfiles se consideran activos si se han identificado o comunicado en los últimos 12 meses a través de cualquier canal.

Puede monitorizar el número de perfiles activos utilizados en las instancias directamente desde Campaign Panel de control de Campaign.

:arrow_upper_right: Para obtener más información, consulte la [documentación del Panel de control de Campaign](https://docs.adobe.com/content/help/es/control-panel/using/performance-monitoring/active-profiles-monitoring.html).


**Temas relacionados**

:arrow_upper_right: [Diseñe y ejecute un flujo de trabajo específico de la campaña](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

:arrow_upper_right: [Obtenga información sobre cómo seleccionar la audiencia de una campaña](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

:arrow_upper_right: [Introducción a los flujos de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
