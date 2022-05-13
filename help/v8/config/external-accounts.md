---
title: Campaign external accounts
description: Campaign external accounts
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 9457652f62810eb401c4010acd9b5da42d88d796
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 24%

---

# Configure your external accounts

Adobe Campaign viene con un conjunto de cuentas externas predefinidas. In order to set up connections with external systems, you can create new external accounts.

Los procesos técnicos utilizan las cuentas externas como flujos de trabajo técnicos o flujos de trabajo de campaña. For example, when setting up a file transfer in a workflow or a data exchange with any other application (Adobe Target, Experience Manager, etc.), you need to select an external account.

**[!UICONTROL Explorer]****[!UICONTROL Administration]**`>`**[!UICONTROL Platform]**`>`**[!UICONTROL External accounts]**

![](assets/external-accounts.png)


>[!CAUTION]
>
>[](../architecture/enterprise-deployment.md)**[!UICONTROL Full FDA]**[!DNL Snowflake]
></br>As a Managed Cloud Services user, this external account is configured for your instance by Adobe. It must not be modified.

## Campaign-specific external accounts

The following technical accounts are used by Adobe Campaign to enable and execute specific processes.

![](../assets/do-not-localize/speech.png)

### Correos devueltos {#bounce-mails-external-account}

>[!NOTE]
>
>[](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

La cuenta externa **Rebote de correos electrónicos** especifica la cuenta POP3 externa que se utilizará para conectar con el servicio de correo electrónico. Todos los servidores configurados para el acceso POP3 pueden utilizarse para recibir el correo electrónico devuelto.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html)

![](assets/bounce_external_1.png)

Para configurar la cuenta externa **[!UICONTROL Bounce mails (defaultPopAccount)]**:

* **[!UICONTROL Server]**

   URL del servidor POP3.

* **[!UICONTROL Port]**

   Número de puerto de conexión POP3. El puerto predeterminado es 110.

* **[!UICONTROL Account]**

   Nombre del usuario.

* **[!UICONTROL Password]**

   Contraseña de la cuenta de usuario.

* **[!UICONTROL Encryption]**

   Tipo de cifrado elegido entre **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** o **[!UICONTROL POP3S]**.
La cuenta externa **Rebote de correos electrónicos** especifica la cuenta POP3 externa que se utilizará para conectar con el servicio de correo electrónico. Todos los servidores configurados para el acceso POP3 pueden utilizarse para recibir el correo electrónico devuelto.

* **[!UICONTROL Function]**

   Inbound email or SOAP router

![](assets/bounce_external_2.png)

>[!IMPORTANT]
>
>Before configuring your POP3 external account using Microsoft OAuth 2.0, you first need to register your application in the Azure portal. Para obtener más información, consulte esta [página](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

**[!UICONTROL Microsoft OAuth 2.0]**

* **[!UICONTROL Azure tenant]**

   ****

* **[!UICONTROL Azure Client ID]**

   ****

* **[!UICONTROL Azure Client secret]**:

   ********

* **[!UICONTROL Azure Redirect URL]**:

   **** `nl/jsp/oauth.jsp``https://redirect.adobe.net/nl/jsp/oauth.jsp`

**[!UICONTROL Setup the connection]**

### Enrutamiento {#routing}

La cuenta externa **[!UICONTROL Routing]** permite configurar cada canal disponible en Adobe Campaign según los paquetes instalados.

>[!CAUTION]
>
>**[!UICONTROL Internal email delivery routing]******

### Instancia de ejecución {#execution-instance}

In the context of transactional messaging, the execution instances is linked to the control instance and connect them. Transactional message templates are deployed to the execution instance.

![](../assets/do-not-localize/glass.png)[](../architecture/architecture.md#transac-msg-archi)

## Access to External Systems external accounts

* ****

   ****

   [](../start/compatibility-matrix.md)

   ![](../assets/do-not-localize/glass.png)[](../connect/fda.md)

## Adobe Solution Integration external accounts

* ****

   **[!UICONTROL Adobe Experience Cloud]**

   ![](../assets/do-not-localize/glass.png)[](../start/connect.md#connect-ims)

* **Web Analytics**

   **[!UICONTROL Web Analytics (Adobe Analytics)]**

   ![](../assets/do-not-localize/glass.png)[](../connect/ac-aa.md)

   ![](../assets/do-not-localize/speech.png)[](../start/campaign-faq.md#support)

   * **Adobe Experience Manager**
   La cuenta externa **[!UICONTROL AEM]** permite administrar el contenido de los envíos de correos electrónicos y los formularios directamente en Adobe Experience Manager.

   ![](../assets/do-not-localize/glass.png)[](../connect/ac-aem.md)

   ![](../assets/do-not-localize/speech.png)[](../start/campaign-faq.md#support)


## CRM Connector External accounts

* ****

   La cuenta externa **[!UICONTROL Microsoft Dynamics CRM]** permite importar y exportar datos de Microsoft Dynamics en Adobe Campaign.

   ![](../assets/do-not-localize/glass.png)[](../connect/ac-ms-dyn.md)

* **Salesforce.com**

   La cuenta externa **[!UICONTROL Salesforce CRM]** permite importar y exportar datos de Salesforce a Adobe Campaign.

   ![](../assets/do-not-localize/glass.png)[](../connect/ac-sfdc.md)

## Transfer Data external accounts

**[!UICONTROL Transfer file]**

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html)

* ****

   **** To set up connections with external systems such as SFTP or FTP servers 898 used for file transfers, you can create your own external accounts.
To do so, specify in this external account the address and credentials used to establish the connection to the SFTP or FTP server.

* ****

   ******[!UICONTROL Transfer file]** Al configurar esta nueva cuenta externa, debe proporcionar los siguientes detalles:

   * **[!UICONTROL AWS S3 Account Server]**```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**[](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys)

   * **[!UICONTROL Secret access key to AWS]**[](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/)

   * **[!UICONTROL AWS Region]**[](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)

   * La casilla de verificación **[!UICONTROL Use server side encryption]** permite almacenar el archivo en modo codificado S3. [](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys)

* ****

   ******[!UICONTROL Transfer file]** ****

   * **[!UICONTROL Server]**

   * **[!UICONTROL Encryption]****[!UICONTROL None]****[!UICONTROL SSL]**

   * **[!UICONTROL Access key]****[!UICONTROL Access key]**[](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal)
