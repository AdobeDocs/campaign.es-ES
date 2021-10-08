---
title: Introducción a las audiencias
description: Introducción a las audiencias
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 780a29dab99ad2bda554134ca95c435b9e76b494
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 34%

---

# Introducción a las audiencias{#gs-ac-audiences}

## Trabajar con perfiles{#gs-ac-profiles}

Los perfiles son contactos almacenados en la base de datos de Campaign, incluidos clientes, suscriptores y posibles clientes. Existen muchos mecanismos para adquirir perfiles y crear esta base de datos: recopilación en línea a través de formularios web, importación manual o automática de archivos de texto, replicación con bases de datos de fabricantes, u otros sistemas de información. Con Adobe Campaign, puede incorporar el historial de marketing, la información de compra, las preferencias, los datos CRM y cualquier dato PI relevante en una vista consolidada para analizar y actuar en consecuencia. Los perfiles contienen toda la información necesaria para la segmentación, calificación y seguimiento de personas.

Un perfil es un registro de la tabla **nmsRecipient** o una tabla externa que almacena todos los atributos de perfil, como el nombre, los apellidos, la dirección de correo electrónico, un ID de cookie, el ID de cliente, el identificador móvil u otra información relacionada con un canal determinado. Otras tablas vinculadas a la tabla de destinatarios contienen datos relacionados con el perfil, por ejemplo, la tabla de registros de envío que contiene registros de todas las entregas realizadas a los destinatarios. Obtenga más información sobre los perfiles integrados y las tablas de destinatarios en [esta sección](../dev/datamodel.md#ootb-profiles).

En Adobe Campaign, **recipients** son los perfiles predeterminados dirigidos a los envíos (correos electrónicos, SMS, etc.). Los datos de destinatario almacenados en la base de datos permiten filtrar el destinatario que recibirá cualquier entrega dada y añadir datos de personalización en el contenido de la entrega. Existen otros tipos de perfiles en la base de datos. Están diseñados para usos diferentes. Por ejemplo, se crean perfiles semilla para probar el contenido antes de enviarlo al público objetivo final.

Los perfiles se pueden agrupar en listas o recopilar consultando la base de datos.


Para rellenar Campaign con datos de perfil, puede:

* [importar ](import.md) archivos de datos desde una fuente de datos externa, como un sistema CRM
* [crear ](../dev/webapps.md) formularios web para permitir a los clientes introducir su propia información y crear su propio perfil
* [asignar a una base de ](../connect/fda.md) datos externa donde se almacenan los perfiles
* introduzca perfiles manualmente mediante la consola de cliente, como se muestra a continuación:

![](assets/create-profile.png)


![](../assets/do-not-localize/book.png) Aprenda a administrar perfiles en la documentación de  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html){target=&quot;_blank&quot;}.


## Privacidad y consentimiento

Adobe Campaign es una potente herramienta para recopilar y procesar un gran volumen de datos, que incluye información personal y datos confidenciales. Adobe Campaign le permite recopilar datos, incluida la información personal y confidencial. Por lo tanto, es esencial que reciba y supervise el consentimiento de sus destinatarios.

![](../assets/do-not-localize/book.png) Aprenda a administrar la privacidad y el consentimiento en la documentación de  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target=&quot;_blank&quot;}.

## Crear listas

Una lista es un conjunto estático de perfiles que puede centrarse en acciones de envío o actualizarse durante operaciones de importación o durante la ejecución del flujo de trabajo. Por ejemplo, una población extraída de la base de datos mediante una consulta puede proporcionar una lista.

![](../assets/do-not-localize/book.png) Aprenda a crear y administrar listas en la documentación de  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html){target=&quot;_blank&quot;}.

## Consultar la base de datos

Utilice la actividad **Query** en un flujo de trabajo para consultar la base de datos, segmentar los datos y crear audiencias complejas.

![](../assets/do-not-localize/book.png) Obtenga más información sobre las consultas de Campaign en la documentación de  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html){target=&quot;_blank&quot;}.

![](../assets/do-not-localize/book.png) Todas las actividades de segmentación se enumeran en la documentación de  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html){target=&quot;_blank&quot;}.

## Creación de una audiencia en un flujo de trabajo

El objetivo se puede crear mediante una combinación de consultas en una secuencia gráfica de un flujo de trabajo. Puede crear audiencias segmentadas según sus necesidades. Para mostrar el editor de flujo de trabajo, haga clic en la pestaña **[!UICONTROL Targeting and workflows]** del panel de campañas.

![](../assets/do-not-localize/book.png) Aprenda a crear una audiencia en un flujo de trabajo de campaña en la documentación de  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}.


## Perfiles activos{#active-profiles}

Según el contrato, cada una de las instancias de Campaign se aprovisiona con una cantidad específica de perfiles activos que se contabilizan a efectos de facturación. Consulte su contrato más reciente para obtener una referencia sobre la cantidad de perfiles activos adquiridos.

**** Profilama un registro de información (por ejemplo: un registro de la  [tabla ](../dev/datamodel.md) Destinatario o una tabla externa que contenga un ID de cookie, ID de cliente, identificador móvil u otra información relacionada con un canal determinado) que represente a un cliente final, a un cliente potencial o a un contacto. Los perfiles se consideran activos si se han identificado o comunicado en los últimos 12 meses a través de cualquier canal.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

**Temas relacionados** en la documentación de Campaign Classic v7:

* [Diseñe y ejecute un flujo de trabajo específico de la campaña](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html){target=&quot;_blank&quot;}

* [Obtenga información sobre cómo seleccionar la audiencia de una campaña](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html){target=&quot;_blank&quot;}

* [Introducción a los flujos de trabajo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html){target=&quot;_blank&quot;}
