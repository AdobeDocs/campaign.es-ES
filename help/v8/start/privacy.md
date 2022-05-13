---
title: Manage Privacy requests in Campaign
description: Learn how to manage privacy requests in Campaign
feature: Audiences
role: Data Engineer
level: Beginner
source-git-commit: 9457652f62810eb401c4010acd9b5da42d88d796
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 48%

---

# Manage Privacy requests in Campaign {#privacy}

<!--Adobe Campaign is a powerful tool for collecting and processing large volume of data, including personal information and sensitive data. It is therefore essential that you receive and monitor consent from your recipients.-->

>[!NOTE]
>
>[](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

Para ayudarle a facilitar su preparación para la privacidad, Adobe Campaign le permite gestionar solicitudes de acceso y eliminación.

![](../assets/do-not-localize/speech.png)********[](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html#right-access-forgotten)

Para realizar estas solicitudes, debe utilizar la integración de **Privacy Core Service**. A través de la integración del Servicio principal de privacidad: Las solicitudes de privacidad enviadas desde el Servicio principal de privacidad a todas las soluciones de Experience Cloud las gestiona Campaign de forma automática a través de un flujo de trabajo dedicado. [Más información](#create-privacy-request)

Adobe offers Data Controllers the tools to create and process Privacy requests for data stored in Campaign. However, it is your responsibility as a Data Controller to verify the identity of the Data Subject making the request, and to confirm that the data returned to the requester is about the Data Subject. [](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#personal-data)

## Define a namespace {#namespaces}

**** El área de nombres es la clave que se utiliza para identificar el sujeto de datos en la base de datos de Adobe Campaign.

>[!NOTE]
>
>[](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html)

Currently Adobe Campaign does not support importing namespaces from the Experience Platform Identity Namespace service. Therefore, once you have created a namespace on the Identity Namespace service, you must create manually the corresponding namespace in the Adobe Campaign interface. Para realizar esto, siga los pasos a continuación.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. [](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace)

1. [](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces)

   ```
   {
           "updateTime": 1632903236731,
           "code": "lumanamespace",
           "status": "ACTIVE",
           "description": "new namespace for Luma privacy requests",
           "id": 10998717,
           "createTime": 1632903236731,
           "idType": "Email",
           "namespaceType": "Custom",
           "name": "Luma Namespace",
           "custom": true
   }
   ```

1. **[!UICONTROL Administration]****[!UICONTROL Platform]****[!UICONTROL Namespaces]****[!UICONTROL New]**

   ![](assets/privacy-namespaces-new.png)

1. Introduzca un **[!UICONTROL Label]**.

1. Fill in the new namespace details to match the namespace that you created on the Identitiy Namespace service:

   * **[!UICONTROL AEC Namespace ID]**
   * **[!UICONTROL Internal name]**
   * **[!UICONTROL Reconciliation key]**

   ![](assets/privacy-namespaces-details.png)

   **[!UICONTROL Reconciliation key]**

1. <!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)-->

   >[!NOTE]
   >
   >    Si desea utilizar varias asignaciones de destino, cree un área de nombres por asignación de destino.

1. Guarde los cambios.

Ahora puede crear solicitudes de privacidad basadas en su nueva Área de nombres. If you use several namespaces, create one Privacy request per namespace for the same reconciliation value.

## Creación de una solicitud de privacidad {#create-privacy-request}

**** Adobe Campaign automatically handles the requests pushed from the Privacy Core Service through a dedicated workflow.

>[!CAUTION]
>
>For the Privacy requests to be processed, you must create on your Adobe Campaign instance a namespace matching the namespace that you created on the Experience Platform Identity Namespace service.

[](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es)

Each Privacy core service job is split into multiple Privacy requests in Adobe Campaign based on how many namespaces are being used, one request corresponding to one namespace.

Además, un trabajo se puede ejecutar en varias instancias. Por lo tanto, se crean varios archivos para un trabajo. Por ejemplo, si una solicitud tiene dos Áreas de nombres y se está ejecutando en tres instancias, se envía un total de seis archivos. Un archivo por Área de nombres e instancia.

El patrón para un nombre de archivo es: `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: Nombre de instancia de Campaign
* **NamespaceId**: ID de Área de nombres de servicio de identidad de la Área de nombres utilizada
* **Clave de reconciliación**: Clave de reconciliación codificada

>[!CAUTION]
>
>Para enviar una solicitud utilizando el tipo de área de nombres personalizada, aproveche el [método JSON](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=es#json){target=&quot;_blank&quot;} y añada el namespaceId a la solicitud, o use la [llamada a la API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html?lang=es#access-delete){target=&quot;_blank&quot;} para realizar la solicitud.
>
>Utilice únicamente la [interfaz de usuario de Privacidad](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=es#request-builder){target=&quot;_blank&quot;} para enviar solicitudes con el tipo de área de nombres estándar.

### Tables searched when processing requests {#list-of-tables}

Al realizar una solicitud de privacidad de eliminación o acceso, Adobe Campaign busca todos los datos del sujeto de datos en función de los datos **[!UICONTROL Reconciliation value]** en todas las tablas que tienen un vínculo a la tabla de destinatario (tipo propio).

Esta es la lista de tablas integradas que se tienen en cuenta al realizar solicitudes de privacidad:

* Destinatarios (destinatario)
* Registro de envíos de destinatario (broadLogRcp)
* Registro de seguimiento de destinatario (trackingLogRcp)
* Registro de envíos de evento archivado (broadLogEventHisto)
* Contenido de lista de destinatario (rcpGrpRel)
* Propuesta de oferta de visitante (propositionVisitor)
* Visitantes (visitante)
* Historial de suscripciones (subHisto)
* Suscripciones (suscripción)
* Propuesta de oferta de destinatario (propositionRcp)

Si ha creado tablas personalizadas que tienen un vínculo a la tabla de destinatario (tipo propio), también se tendrán en cuenta. Por ejemplo, si tiene una tabla de transacciones vinculada a la tabla de destinatarios y una tabla de detalles de transacciones vinculada a la tabla de transacciones, ambas se tendrán en cuenta.
<!--
>[!CAUTION]
>
>If you perform Privacy batch requests using profile deletion workflows, please take into consideration the following remarks:
>* Profile deletion via workflows do not process children tables.
>* You need to handle the deletion for all the children tables.
>* Adobe recommends that you create an ETL workflow that add the lines to delete in the Privacy Access table and let the **[!UICONTROL Delete privacy requests data]** workflow perform the deletion. We suggest to limit to 200 profiles per day to delete for performance reasons.-->

### Estados de solicitud de privacidad {#privacy-request-statuses}

Here are the different statuses for Privacy requests in Adobe Campaign:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: en curso, el flujo de trabajo aún no ha procesado la solicitud.
* **[!UICONTROL Processing]**/**[!UICONTROL Retry in progress]**: el flujo de trabajo está procesando la solicitud.
* **[!UICONTROL Delete pending]**: el flujo de trabajo ha identificado todos los datos de destinatario que se van a eliminar.
* **[!UICONTROL Delete in progress]**: el flujo de trabajo está procesando la eliminación.
* **[!UICONTROL Complete]**: el procesamiento de la solicitud ha finalizado sin error.
* **[!UICONTROL Error]**: el flujo de trabajo ha encontrado un error. El motivo se muestra en la lista de las solicitudes de privacidad de la **[!UICONTROL Request status]** columna. Por ejemplo, **[!UICONTROL Error data not found]** significa que en la base de datos no se han encontrado datos de destinatario que coincidan con los del sujeto de datos **[!UICONTROL Reconciliation value]** .

**Temas relacionados** en la documentación de Campaign Classic v7:

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html)

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html)

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html#privacy-management-regulations)

* [](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html)