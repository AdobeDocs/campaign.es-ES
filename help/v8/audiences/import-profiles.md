---
title: Importación de perfiles en Campaign
description: Obtenga información sobre cómo importar contactos en Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 59046a11c3e057cf41c322f190a9d8aef310c356
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 45%

---

# Importación de perfiles de un archivo{#create-profiles}

Para rellenar la base de datos de Campaign, puede [añadir perfiles manualmente](create-profiles.md) o importar perfiles como se detalla a continuación. También puede utilizar archivos importados para actualizar los datos de contacto.

## Importación de perfiles con un flujo de trabajo {#import-profiles-with-a-wf}

Los flujos de trabajo pueden ser una forma útil de automatizar algunos de los procesos de importación. Tanto si se importan datos desde un archivo local como desde un SFTP, puede utilizar flujos de trabajo para estandarizar los procedimientos de gestión de datos.

### Uso de datos de una lista: Leer lista {#data-from-read-list}

Prepare y estructure los datos en un archivo para importarlos con un flujo de trabajo. [Más información](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html).

### Carga de datos desde un archivo {#data-from-a-file}

Los datos procesados en un flujo de trabajo se pueden extraer de un archivo estructurado para que se puedan importar en Adobe Campaign. [Más información](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html).

Una vez recopilados los datos, puede utilizarlos en sus flujos de trabajo, por ejemplo para enriquecer una entrega o actualizar la base de datos. Para obtener más información, consulte [esta sección](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html).

## Importaciones únicas{#import-jobs}

Adobe Campaign proporciona una capacidad de importación genérica que le permite, por ejemplo, extraer una lista de clientes o posibles clientes que luego formarán parte de una población objetivo o suministrar datos de archivos externos a la base de datos.

Las importaciones genéricas se administran desde la variable **[!UICONTROL Profiles and Targets > Jobs]** de la página principal de Adobe Campaign.

![](assets/new-import-job.png)

Los pasos para realizar una importación genérica se detallan en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=es){target=&quot;_blank&quot;}.
