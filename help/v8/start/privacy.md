---
title: Administrar solicitudes de privacidad en Campaign
description: Obtenga información sobre cómo administrar las solicitudes de privacidad en Campaign
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 0f81d318-dbfd-45c8-b391-b1d14d23e9c8
source-git-commit: 41a213eea434b3fc6ee8b3ea3c29d4364f9c9761
workflow-type: ht
source-wordcount: '1080'
ht-degree: 100%

---

# Administrar solicitudes de privacidad en Campaign {#privacy}

Según la naturaleza de su negocio y las jurisdicciones bajo las que actúa, sus operaciones de datos pueden estar sujetas a regulaciones legales de privacidad. Estas regulaciones, a menudo, otorgan a sus clientes el derecho de solicitar acceso a los datos que se recopilan de ellos, así como de solicitar la eliminación de esos datos almacenados. Estas solicitudes de datos personales de los clientes se denominan “solicitudes de privacidad” en toda la documentación.

Adobe ofrece las herramientas de los controladores de datos para crear y procesar solicitudes de privacidad de datos almacenados en Campaign. Por ello, es responsabilidad del controlador de datos verificar la identidad del sujeto de datos que realiza la solicitud y confirmar que la información devuelta al solicitante sea sobre el sujeto de datos. Obtenga más información sobre los datos personales y las distintas entidades que administran los datos en la [Documentación de la versión 7 de Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=es#personal-data){target=&quot;_blank&quot;}.


Para administrar la solicitud de privacidad en Campaign, primero debe [definir un área de nombres](#namespaces). A continuación, puede crear y administrar solicitudes de privacidad. Para ejecutar solicitudes de privacidad, utilice la integración **Privacy Service de Adobe**. Las solicitudes de privacidad enviadas desde Privacy Service a todas las soluciones de Adobe Experience Cloud las gestiona Campaign de forma automática a través de un flujo de trabajo dedicado. [Más información](#create-privacy-request)

![](../assets/do-not-localize/speech.png) Obtenga información sobre el **Derecho de acceso** y el **Derecho al olvido** (eliminar solicitud) en la [Documentación de la versión 7 de Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=es#right-access-forgotten){target=&quot;_blank&quot;}.


>[!NOTE]
>
>Esta capacidad está disponible a partir de la versión 8.3 de Campaign. Para comprobar su versión, consulte [esta sección](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

## Definir un área de nombres {#namespaces}

Antes de crear una solicitud de privacidad, debe **definir el área de nombres** que utilizará. El área de nombres es la clave que se usa para identificar el sujeto de datos en la base de datos.

>[!NOTE]
>
>Obtenga más información acerca de las áreas de nombres de identidad en [Documentación de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=es){target=&quot;_blank&quot;}.

Actualmente, Adobe Campaign no admite la importación de áreas de nombres desde el servicio de área de nombres de identidad de Experience Platform. Por lo tanto, una vez que haya creado un área de nombres en el servicio Área de nombres de identidad, debe crear manualmente el área de nombres correspondiente en la interfaz de Adobe Campaign. Para realizar esto, siga los pasos a continuación.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. Cree un área de nombres en el [Servicio de área de nombres de identidad](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace){target=&quot;_blank&quot;}.

1. Al [listar las áreas de nombres de identidad](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target=&quot;_blank&quot;} disponibles para su organización, obtiene los detalles siguientes del área de nombres, por ejemplo:

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

1. En Adobe Campaign, vaya a **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]** y seleccione **[!UICONTROL New]**.

   ![](assets/privacy-namespaces-new.png)

1. Introduzca un **[!UICONTROL Label]**.

1. Complete los nuevos detalles del área de nombres para que coincidan con el área de nombres que ha creado en el servicio Área de nombres de identidad:

   * el **[!UICONTROL AEC Namespace ID]** debe coincidir con el atributo &quot;id&quot;
   * el **[!UICONTROL Internal name]** debe coincidir con el atributo &quot;code&quot;
   * el **[!UICONTROL Reconciliation key]** debe coincidir con el atributo &quot;idType&quot;

   ![](assets/privacy-namespaces-details.png)

   El campo **[!UICONTROL Reconciliation key]** se utilizará para identificar el sujeto de datos en la base de datos de Adobe Campaign.

1. Selección de una asignación de destino <!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)--> para especificar cómo se reconciliará el área de nombres en Adobe Campaign.

   >[!NOTE]
   >
   >Si necesita utilizar varias asignaciones de destino, cree un área de nombres por asignación de destino.

1. Guarde los cambios.

Ahora puede crear solicitudes de privacidad basadas en su nueva Área de nombres. Si utiliza varias áreas de nombres, cree una solicitud de privacidad por cada área de nombres para el mismo valor de reconciliación.

## Creación de una solicitud de privacidad {#create-privacy-request}

La integración de **[!DNL Adobe Experience Platform Privacy Service]** le permite automatizar sus solicitudes de privacidad en un contexto de varias soluciones a través de una sola llamada de API JSON. Adobe Campaign gestiona automáticamente las solicitudes enviadas desde Privacy Service mediante un flujo de trabajo dedicado.

Consulte la documentación del [Privacy Service de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es){target=&quot;_blank&quot;} para obtener información sobre cómo crear solicitudes de privacidad desde el Servicio principal de privacidad.

Cada trabajo de **[!DNL Privacy Service]** se divide en varias solicitudes de privacidad en Adobe Campaign, en función de cuántas áreas de nombres se estén usando; una solicitud que corresponde a un área de nombres.

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

### Tablas buscadas al procesar solicitudes {#list-of-tables}

Al realizar una solicitud de privacidad de eliminación o acceso, Adobe Campaign busca todos los datos del sujeto de datos en función de los datos **[!UICONTROL Reconciliation value]** en todas las tablas que tienen un vínculo a la tabla de destinatario (tipo propio).

La lista de tablas integradas que se tienen en cuenta al ejecutar solicitudes de privacidad es la siguiente:

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

A continuación, se encuentran los distintos estados de las solicitudes de privacidad en Adobe Campaign y cómo interpretarlas:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: en curso, el flujo de trabajo aún no ha procesado la solicitud.
* **[!UICONTROL Processing]**/**[!UICONTROL Retry in progress]**: el flujo de trabajo está procesando la solicitud.
* **[!UICONTROL Delete pending]**: el flujo de trabajo ha identificado todos los datos de destinatario que se van a eliminar.
* **[!UICONTROL Delete in progress]**: el flujo de trabajo está procesando la eliminación.
* **[!UICONTROL Complete]**: el procesamiento de la solicitud ha finalizado sin error.
* **[!UICONTROL Error]**: el flujo de trabajo ha encontrado un error. El motivo se muestra en la lista de las solicitudes de privacidad de la **[!UICONTROL Request status]** columna. Por ejemplo, **[!UICONTROL Error data not found]** significa que en la base de datos no se han encontrado datos de destinatario que coincidan con los del sujeto de datos **[!UICONTROL Reconciliation value]** .

**Temas relacionados en la documentación de la versión 7 de Campaign Classic:**

* [Privacidad y consentimiento](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=es){target=&quot;_blank&quot;}

* [Introducción a Administración de privacidad](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=es){target=&quot;_blank&quot;}

* [Regulaciones sobre administración de la privacidad](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=es#privacy-management-regulations){target=&quot;_blank&quot;} (RGPD, CCPA, PDPA y LGPD)

* [Exclusión para la venta de información personal](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html?lang=es){target=&quot;_blank&quot;} (específico de la CCPA)
