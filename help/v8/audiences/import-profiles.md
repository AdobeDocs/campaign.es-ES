---
title: Importación de perfiles en Campaign
description: Obtenga información sobre cómo importar contactos en Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
TQID: https://experienceleague.adobe.com/qoVtBCkTTk2DKaR605exVaJvjQ7kjKRoRg-9fJqdoo4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 287
ht-degree: 42%

---

# Importación de perfiles de un archivo{#create-profiles}

Para rellenar la base de datos de Campaign, puede [agregar perfiles manualmente](create-profiles.md) o importar perfiles como se detalla a continuación. También puede utilizar archivos importados para actualizar los datos de contacto.

## Importación de perfiles con un flujo de trabajo {#import-profiles-with-a-wf}

Los flujos de trabajo pueden ser una forma útil de automatizar algunos de los procesos de importación. Tanto si se importan datos desde un archivo local como desde un SFTP, puede utilizar flujos de trabajo para estandarizar los procedimientos de gestión de datos.

### Uso de datos de una lista: Leer lista {#data-from-read-list}

Prepare y estructurar los datos en un archivo para importarlos con un flujo de trabajo. [Más información](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html?lang=es){target="_blank"}.

### Carga de datos desde un archivo {#data-from-a-file}

Los datos procesados en un flujo de trabajo se pueden extraer de un archivo estructurado para que se puedan importar en Adobe Campaign. [Más información](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html?lang=es){target="_blank"}.

Una vez recopilados los datos, puede utilizarlos en sus flujos de trabajo, por ejemplo para enriquecer una entrega o actualizar la base de datos. Para obtener más información, consulte [esta sección](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html?lang=es){target="_blank"}.

## Importaciones de una sola vez{#import-jobs}

Adobe Campaign proporciona una capacidad de importación genérica que le permite, por ejemplo, extraer una lista de clientes o clientes potenciales que luego formarán parte de una población de destinatarios o suministrar datos de archivos externos a su base de datos.

Las importaciones genéricas se administran desde el menú **[!UICONTROL Profiles and Targets > Jobs]** de la página principal de Adobe Campaign.

![](assets/new-import-job.png)

Los pasos para realizar una importación genérica se detallan en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=es){target="_blank"}.
