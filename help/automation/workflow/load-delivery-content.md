---
product: campaign
title: Carga de contenido de entrega
description: Carga de contenido de entrega
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 08febcbc-1703-4d36-89e1-32c903618084
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 100%

---

# Carga de contenido de entrega{#loading-delivery-content}

Si el contenido de la entrega está disponible en un archivo HTML ubicado en los servidores Amazon S3, FTP o SFTP, se puede cargar fácilmente este contenido en las entregas de Adobe Campaign.

Para ello:

1. Si aún no se ha definido una conexión entre Adobe Campaign y el servidor (S)FTP que aloje los archivos de contenido, cree una nueva cuenta externa de S3, FTP o SFTP en **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**. Especifique en esta cuenta externa la dirección y las credenciales utilizadas para establecer la conexión con el servidor S3 o (S)FTP.

   A continuación, se muestra un ejemplo de una cuenta externa S3:

   ![](assets/delivery_loadcontent_filetransfertexamples3.png)

1. Cree un nuevo flujo de trabajo, por ejemplo, desde **[!UICONTROL Profiles and Targets]** > **[!UICONTROL Jobs]** > **[!UICONTROL Targeting workflows]**.
1. Añada una actividad **[!UICONTROL File transfer]** al flujo de trabajo y configúrela especificando:

   * La cuenta externa que se utiliza para conectar con el servidor S3 o (S)FTP.
   * La ruta del archivo en el servidor S3 o (S)FTP.

   ![](assets/delivery_loadcontent_filetransfertexample.png)

1. Añada una actividad **[!UICONTROL Delivery]** y conéctela a la transición saliente de la actividad **[!UICONTROL File transfer]**. Configúrela como se indica a continuación:

   * Delivery: Según las necesidades, puede ser una entrega específica que ya se ha creado en el sistema o uno nuevo en función de una plantilla existente.
   * Recipients: En este ejemplo, se considera que el objetivo está especificado en el propio envío.
   * Content: Incluso si el contenido se importa en la actividad anterior, seleccione **[!UICONTROL Specified in the delivery]**. Ya que el contenido se importa directamente desde un archivo ubicado en un servidor remoto, no tiene identificador cuando el flujo de trabajo lo procesa y no se puede identificar como procedente del evento entrante.
   * Acción a realizar: seleccione **[!UICONTROL Save]** para guardar la entrega y poder acceder a ella desde **[!UICONTROL Campaign management]** > **[!UICONTROL Deliveries]** cuando se ejecute el flujo de trabajo.

   ![](assets/delivery_loadcontent_activityexample.png)

1. En la pestaña **[!UICONTROL Script]** de la actividad **[!UICONTROL Delivery]**, añada el siguiente comando para cargar el contenido del archivo importado en la entrega:

   ```
   delivery.content.html.source=loadFile(vars.filename)
   ```

   ![](assets/delivery_loadcontent_script.png)

1. Guarde y ejecute el flujo de trabajo. Se crea un nuevo envío con el contenido cargado en **[!UICONTROL Campaign management]** > **[!UICONTROL Deliveries]**.

