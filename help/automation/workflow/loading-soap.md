---
product: campaign
title: Carga (SOAP)
description: Carga (SOAP)
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 21c42a36-9a50-49b8-8a07-b041ba8b2026
TQID: 'https://experienceleague.adobe.com/CBO5ddwOwsFclqdXq-ahz6ZMg0fXVc4L8vIruKz17j4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 100%
---
# Carga (SOAP){#loading-soap}



>[!CAUTION]
>
>La actividad **Loading (SOAP)** solo está disponible si tiene instalado el módulo **FDA (Federated Data Access)**. Compruebe el acuerdo de licencia.

La actividad **Load (SOAP)** se utiliza además de la actividad de **data loading (RDBMS)** cuando no es posible recopilar datos directamente mediante el FDA en una base de datos externa.

La operación es la siguiente:

1. Seleccione entre utilizar un ejemplo XML o un WSDL.

   El siguiente ejemplo proviene de un flujo de trabajo técnico del módulo Centro de mensajes.

   ![](assets/load_soap_002.png)

1. Para un ejemplo XML, seleccione un archivo de muestra. El archivo se analiza para establecer un ejemplo del resultado.

   Para un WSDL, introduzca la URL de acceso coincidente y, a continuación, genere el código esquemático. El servicio y la llamada seleccionados se actualizan y se muestran automáticamente.

   ![](assets/soap_load_003.png)

1. Seleccione **[!UICONTROL Click here to view and edit analysis results]** para especificar cada columna identificada.

   ![](assets/soap_load_001.png)

   Si desea actualizar el ejemplo, seleccione **[!UICONTROL Re-analyze the example]**.

1. Puede utilizar el número de línea como identificador o especificar que la llamada SOAP devuelva varios elementos.
1. Introduzca los siguientes scripts de pestañas según su función:

   * **[!UICONTROL Initialization]**: establece una conexión SOAP.
   * **[!UICONTROL Iteration]**: realiza la llamada al servicio SOAP. El retorno de esta función debe ser un objeto XML compatible con la descripción del ejemplo o el WSDL.

     Adobe Campaign llama al código de esta pestaña hasta que devuelva un objeto XML nulo.

   * **[!UICONTROL Finalization]**: cierra la conexión o libera otros recursos creados durante el procesamiento.
