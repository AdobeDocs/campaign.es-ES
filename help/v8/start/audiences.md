---
title: Trabajo con audiencias en Campaign
description: Trabajo con audiencias en Campaign
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: ad96c126836981f861c246eafa2ec7d2c0e179dc
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 49%

---

# Trabajo con audiencias en Campaign{#gs-ac-audiences}

Los perfiles son contactos almacenados en la base de datos de Campaign.

En Adobe Campaign, **los destinatarios** son los perfiles predeterminados a los que se dirigen los envíos (correos electrónicos, SMS, etc.). Los datos de destinatario almacenados en la base de datos permiten filtrar el destinatario que recibirá cualquier envío dado y añadir datos de personalización en el contenido de los envíos. Existen otros tipos de perfiles en la base de datos. Están diseñados para usos diferentes. Por ejemplo se crean perfiles semilla para probar los envíos antes de enviarlos al público objetivo final.

Obtenga información sobre cómo importar, actualizar y administrar perfiles y audiencias [en esta sección](../audiences/gs-audiences.md).

## Creación de listas{#create-lists}

Una lista es un conjunto estático de contactos que puede centrarse en acciones de envío o actualizarse durante una importación u otra acción de flujo de trabajo. Por ejemplo, una población extraída de la base de datos mediante una consulta se puede almacenar como una lista.

Aprenda a crear y administrar listas en [esta página](../audiences/create-audiences.md).

## Filtrar la base de datos{#filter-the-database}

La configuración del filtro permite seleccionar datos de una lista **[!UICONTROL dynamically]**: cuando se modifican los datos, los datos filtrados se actualizan. Puede crear sus propios filtros o utilizar los filtros integrados para definir una audiencia objetivo.

Aprenda a crear y administrar filtros en [esta página](../audiences/create-filters.md).

## Creación de una audiencia en un flujo de trabajo

El objetivo se puede crear mediante una combinación de consultas en una secuencia gráfica de un flujo de trabajo. Puede crear audiencias que se segmentarán según sus necesidades. Para mostrar el editor de flujo de trabajo, haga clic en la pestaña **[!UICONTROL Targeting and workflows]** del panel de campañas.

Aprenda a crear una audiencia en un flujo de trabajo de campaña en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=es){target="_blank"}.


## Perfiles activos {#active-profiles}

Un perfil activo es un perfil con el que el cliente ha intentado comunicarse durante los últimos 12 meses a través de cualquier canal.

Según el contrato, cada una de las instancias de Campaign se aprovisiona con una cantidad específica de perfiles activos que se contabilizan a efectos de facturación. Consulte su contrato más reciente para obtener una referencia sobre la cantidad de perfiles activos adquiridos. Obtenga más información en [Descripción del producto de Adobe Campaign](https://helpx.adobe.com/es/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Puede monitorizar el número de perfiles activos en su instancia directamente desde el Panel de control de Campaign. Para obtener más información, consulte la [documentación del panel de control](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=es){target="_blank"}.


Son de aplicación las siguientes limitaciones y protecciones:

* Un perfil al que se destinan varios envíos se cuenta solo una vez.
* Los perfiles segmentados en el contexto del marketing social en X (Twitter) no se tienen en cuenta como perfiles activos.
* El recuento se basa en la clave principal del destinatario. Como consecuencia, si un perfil está presente en dos tablas de destinatarios diferentes, es posible que se contabilice dos veces como perfil activo.

## Privacidad y consentimiento{#privacy-and-consent}

Adobe Campaign es una potente herramienta para recopilar y procesar un gran volumen de datos, incluida información personal e información confidencial. Adobe Campaign le permite recopilar datos, incluida la información personal y confidencial. Por lo tanto, es esencial que reciba y supervise el consentimiento de sus destinatarios.

Obtenga información sobre cómo administrar la privacidad y el consentimiento en [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=es){target="_blank"}.

