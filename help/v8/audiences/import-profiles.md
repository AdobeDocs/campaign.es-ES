---
title: Importación de perfiles en Campaign
description: Obtenga información sobre cómo importar contactos en Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 9c5c5e825294bd39742ecbd07b98a90b4555c138
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 34%

---

# Importar perfiles de un archivo{#create-profiles}

Para rellenar la base de datos de Campaign, puede [añadir perfiles manualmente](create-profiles.md) o importar perfiles como se detalla a continuación. También puede utilizar archivos importados para actualizar los datos de contacto.

## Importación de perfiles con un flujo de trabajo {#import-profiles-with-a-wf}

Los flujos de trabajo pueden ser una forma útil de automatizar algunos de los procesos de importación. Tanto si se importan datos desde un archivo local como desde un SFTP, puede utilizar flujos de trabajo para estandarizar los procedimientos de gestión de datos.

### Uso de datos de una lista: Leer lista {#data-from-read-list}

Prepare y estructure los datos en un archivo para importarlos con un flujo de trabajo.

Para obtener más información sobre el uso de la actividad de la lista de lectura en un flujo de trabajo, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/read-list.html){target=&quot;_blank&quot;}.

### Carga de datos desde un archivo {#data-from-a-file}

Los datos procesados en un flujo de trabajo se pueden extraer de un archivo estructurado para que se puedan importar en Adobe Campaign.

Puede encontrar una descripción de la actividad de datos de carga en la [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/data-loading--file-.html){target=&quot;_blank&quot;}.

Una vez recopilados los datos, puede utilizarlos en sus flujos de trabajo, por ejemplo para enriquecer una entrega o actualizar la base de datos. Para obtener más información, consulte [Documentación de Campaign Classic v7]https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/how-to-use-workflow-data.htmll){target=&quot;_blank&quot;}.

## Importaciones únicas{#import-jobs}

Adobe Campaign proporciona una capacidad de importación genérica que le permite, por ejemplo, extraer una lista de clientes o posibles clientes que luego formarán parte de una población objetivo o suministrar datos de archivos externos a la base de datos.

Las importaciones genéricas se administran desde la variable **[!UICONTROL Profiles and Targets > Jobs]** de la página principal de Adobe Campaign.

![](assets/new-import-job.png)

Los pasos para realizar una importación genérica se detallan en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=es){target=&quot;_blank&quot;}.
