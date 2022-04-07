---
title: Trabajar con audiencias en Campaign
description: Trabajar con audiencias en Campaign
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: b5fb8825734bce2ec62485208b468757b461005f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 27%

---

# Trabajar con audiencias en Campaign{#gs-ac-audiences}

Los perfiles son contactos almacenados en la base de datos de Campaign.

En Adobe Campaign, **recipients** son los perfiles predeterminados dirigidos a los envíos (correos electrónicos, SMS, etc.). Los datos de destinatario almacenados en la base de datos permiten filtrar el destinatario que recibirá cualquier entrega dada y añadir datos de personalización en el contenido de la entrega. Existen otros tipos de perfiles en la base de datos. Están diseñados para usos diferentes. Por ejemplo, se crean perfiles semilla para probar el contenido antes de enviarlo al público objetivo final.

Obtenga información sobre cómo importar, actualizar y administrar perfiles y audiencias [en esta sección](../audiences/gs-audiences.md).

## Crear listas{#create-lists}

Una lista es un conjunto estático de contactos que se puede definir como objetivo en acciones de envío o actualizar durante una importación u otra acción de flujo de trabajo. Por ejemplo, una población extraída de la base de datos mediante una consulta se puede almacenar como una lista.

![](../assets/do-not-localize/glass.png) Obtenga información sobre cómo crear y administrar listas en [esta página](../audiences/create-audiences.md).

## Filtrar la base de datos{#filter-the-database}

La configuración del filtro permite seleccionar datos de una lista **[!UICONTROL dynamically]**: cuando se modifican los datos, se actualizan los datos filtrados. Puede crear sus propios filtros o utilizar los filtros integrados para definir una audiencia de destino.

![](../assets/do-not-localize/glass.png) Obtenga información sobre cómo crear y administrar filtros en [esta página](../audiences/create-filters.md).

## Creación de una audiencia en un flujo de trabajo

El objetivo se puede crear mediante una combinación de consultas en una secuencia gráfica de un flujo de trabajo. Puede crear audiencias segmentadas según sus necesidades. Para mostrar el editor de flujo de trabajo, haga clic en la pestaña **[!UICONTROL Targeting and workflows]** del panel de campañas.

![](../assets/do-not-localize/book.png) Obtenga información sobre cómo crear una audiencia en un flujo de trabajo de campaña en [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}.


## Perfiles activos{#active-profiles}

Según el contrato, cada una de las instancias de Campaign se aprovisiona con un número específico de perfiles activos que se contabilizan a efectos de facturación. Consulte su contrato más reciente para obtener una referencia sobre la cantidad de perfiles activos adquiridos.

**Perfil** un registro de información (por ejemplo: un registro de la variable [Tabla de destinatarios](../dev/datamodel.md) o una tabla externa que contenga un ID de cookie, ID de cliente, ID móvil u otra información relevante para un canal en particular) que represente a un cliente final, a un cliente potencial o a un posible cliente. Los perfiles se consideran activos si se han identificado o comunicado en los últimos 12 meses a través de cualquier canal.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->


## Privacidad y consentimiento

Adobe Campaign es una potente herramienta para recopilar y procesar un gran volumen de datos, que incluye información personal y datos confidenciales. Adobe Campaign le permite recopilar datos, incluida la información personal y confidencial. Por lo tanto, es esencial que reciba y supervise el consentimiento de sus destinatarios.

![](../assets/do-not-localize/book.png) Obtenga información sobre cómo administrar la privacidad y el consentimiento en [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=es){target=&quot;_blank&quot;}.


**Temas relacionados** en la documentación de Campaign Classic v7:

* [Diseñar y ejecutar un flujo de trabajo específico de una campaña](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html){target=&quot;_blank&quot;}

* [Obtenga información sobre cómo seleccionar la audiencia de una campaña](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html){target=&quot;_blank&quot;}

* [Introducción a los flujos de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html){target=&quot;_blank&quot;}
