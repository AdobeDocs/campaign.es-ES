---
title: Cuentas externas de Campaign
description: Cuentas externas de Campaign
feature: Application Settings
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 24%

---

# Configuración de las cuentas externas

Adobe Campaign viene con un conjunto de cuentas externas predefinidas. Para configurar conexiones con sistemas externos, puede crear nuevas cuentas externas.

Los procesos técnicos utilizan las cuentas externas como flujos de trabajo técnicos o flujos de trabajo de campaña. Por ejemplo, al configurar una transferencia de archivos en un flujo de trabajo o un intercambio de datos con cualquier otra aplicación (Adobe Target, Experience Manager, etc.), debe seleccionar una cuenta externa.

Puede acceder a cuentas externas desde Adobe Campaign **[!UICONTROL Explorer]**: buscar **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>En el contexto de un [Implementación empresarial (FFDA)](../architecture/enterprise-deployment.md), un **[!UICONTROL Full FDA]** (ffda) la cuenta externa administra la conexión entre la base de datos local de Campaign y la base de datos de Cloud ([!DNL Snowflake]).
></br>Como usuario de Cloud Services administrados, esta cuenta externa se configura para su instancia por Adobe. No debe modificarse.

## Cuentas externas específicas de la campaña

Adobe Campaign utiliza las siguientes cuentas técnicas para habilitar y ejecutar procesos específicos.

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, Adobe configura todas las cuentas externas específicas de Campaign para usted.

### Correos devueltos {#bounce-mails-external-account}

>[!NOTE]
>
>La autenticación de Microsoft Exchange Online OAuth 2.0 para la funcionalidad POP3 está disponible a partir de Campaign v8.3. Para comprobar su versión, consulte [esta sección](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

La cuenta externa **Rebote de correos electrónicos** especifica la cuenta POP3 externa que se utilizará para conectar con el servicio de correo electrónico. Todos los servidores configurados para el acceso POP3 pueden utilizarse para recibir el correo electrónico devuelto.

![](../assets/do-not-localize/book.png) Obtenga más información sobre los correos electrónicos entrantes en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;}

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

   Correo electrónico entrante o enrutador SOAP

![](assets/bounce_external_2.png)

>[!IMPORTANT]
>
>Antes de configurar la cuenta externa POP3 usando Microsoft OAuth 2.0, primero debe registrar la aplicación en el portal de Azure. Para obtener más información, consulte esta [página](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

Para configurar una externa POP3 utilizando Microsoft OAuth 2.0, marque la casilla **[!UICONTROL Microsoft OAuth 2.0]** y rellene los campos siguientes:

* **[!UICONTROL Azure tenant]**

   El ID de Azure (o el ID de directorio (inquilino) se pueden encontrar en el **Elementos esenciales** lista desplegable de la información general de su aplicación en el portal de Azure.

* **[!UICONTROL Azure Client ID]**

   El ID de cliente (o el ID de aplicación (cliente) se pueden encontrar en la variable **Elementos esenciales** lista desplegable de la información general de su aplicación en el portal de Azure.

* **[!UICONTROL Azure Client secret]**:

   El ID de secreto de cliente se puede encontrar en la variable **Secretos del cliente** de **Certificados y secretos** de su aplicación en el portal de Azure.

* **[!UICONTROL Azure Redirect URL]**:

   La dirección URL de redireccionamiento se encuentra en el **Autenticación** de su aplicación en el portal de Azure. Debe terminar con la siguiente sintaxis `nl/jsp/oauth.jsp`, p. ej. `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

Después de introducir las diferentes credenciales, puede hacer clic en **[!UICONTROL Setup the connection]** para finalizar la configuración de la cuenta externa.

### Enrutamiento {#routing}

La cuenta externa **[!UICONTROL Routing]** permite configurar cada canal disponible en Adobe Campaign según los paquetes instalados.

>[!CAUTION]
>
>La variable **[!UICONTROL Internal email delivery routing]** Cuenta externa (defaultEmailBulk) **no debe** estar habilitado en Adobe Campaign v8.

### Instancia de ejecución {#execution-instance}

En el contexto de los mensajes transaccionales, las instancias de ejecución están vinculadas a la instancia de control y las conectan. Las plantillas de mensajes transaccionales se implementan en la instancia de ejecución.

![](../assets/do-not-localize/glass.png) Obtenga más información sobre la arquitectura del Centro de mensajes en [esta página](../architecture/architecture.md#transac-msg-archi).

## Acceso a cuentas externas de sistemas externos

* **Base de datos externa (FDA)**

   Utilice la variable **Base de datos externa** escriba cuenta externa para conectarse a una base de datos externa a través de FDA.

   Las bases de datos externas compatibles con Adobe Campaign v8 se enumeran en la sección [Matriz de compatibilidad](../start/compatibility-matrix.md)

   ![](../assets/do-not-localize/glass.png) Obtenga más información sobre la opción Acceso de datos federado (FDA) en [esta sección](../connect/fda.md).

## Adobe Solución Integración Cuentas externas

* **Adobe Experience Cloud**

   La variable **[!UICONTROL Adobe Experience Cloud]** se utiliza la cuenta externa de implementación de Adobe IMS para conectarse a la consola de Adobe Campaign mediante un Adobe ID.

   ![](../assets/do-not-localize/glass.png) Obtenga más información sobre el servicio Identity Management de Adobe (IMS) en [esta sección](../start/connect.md#connect-ims).

* **Web Analytics**

   Utilice la variable **[!UICONTROL Web Analytics (Adobe Analytics)]** cuenta externa para configurar la transferencia de datos de Adobe Analytics a Adobe Campaign.

   ![](../assets/do-not-localize/glass.png) Obtenga más información sobre la integración de Adobe Campaign con Adobe Analytics en [esta página](../connect/ac-aa.md).

   ![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, [Adobe de contacto](../start/campaign-faq.md#support) para integrar Adobe Analytics con Campaign.

   * **Adobe Experience Manager**
   La cuenta externa **[!UICONTROL AEM]** permite administrar el contenido de los envíos de correos electrónicos y los formularios directamente en Adobe Experience Manager.

   ![](../assets/do-not-localize/glass.png) Obtenga más información sobre la integración de Adobe Campaign con Adobe Analytics en [esta página](../connect/ac-aem.md).

   ![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, [Adobe de contacto](../start/campaign-faq.md#support) para integrar Adobe Experience Manager con Adobe Campaign.


## Cuentas externas del conector CRM

* **Microsoft Dynamics CRM**

   La cuenta externa **[!UICONTROL Microsoft Dynamics CRM]** permite importar y exportar datos de Microsoft Dynamics en Adobe Campaign.

   ![](../assets/do-not-localize/glass.png) Obtenga más información sobre la integración de Adobe Campaign con Microsoft Dynamics CRM en [esta página](../connect/ac-ms-dyn.md).

* **Salesforce.com**

   La cuenta externa **[!UICONTROL Salesforce CRM]** permite importar y exportar datos de Salesforce a Adobe Campaign.

   ![](../assets/do-not-localize/glass.png) Obtenga más información sobre la integración de Adobe Campaign con Salesforce.com CRM en [esta página](../connect/ac-sfdc.md).

## Transferir cuentas externas de datos

Estas cuentas externas se pueden usar para importar o exportar datos a Adobe Campaign mediante un **[!UICONTROL Transfer file]** actividad de flujo de trabajo.

![](../assets/do-not-localize/book.png) Obtenga más información sobre la transferencia de archivos en flujos de trabajo en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html){target=&quot;_blank&quot;}

* **FTP y SFTP**

   La variable **FTP** cuenta externa permite configurar y probar el acceso a un servidor fuera de Adobe Campaign. Para configurar conexiones con sistemas externos como SFTP o servidores FTP 898 utilizados para transferencias de archivos, puede crear sus propias cuentas externas.
Para ello, especifique en esta cuenta externa la dirección y las credenciales utilizadas para establecer la conexión con el servidor SFTP o FTP.

* **Amazon Simple Storage Service (S3)**

   La variable **AWS S3** El conector se puede utilizar para importar o exportar datos a Adobe Campaign mediante un **[!UICONTROL Transfer file]** actividad de flujo de trabajo. Al configurar esta nueva cuenta externa, debe proporcionar los siguientes detalles:

   * **[!UICONTROL AWS S3 Account Server]**: URL del servidor, rellenada de la siguiente manera:   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**: Obtenga información sobre cómo encontrar su ID de clave de acceso de AWS en [Documentación de Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) .

   * **[!UICONTROL Secret access key to AWS]**: Obtenga información sobre cómo encontrar la clave de acceso secreta a AWS en [Documentación de Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

   * **[!UICONTROL AWS Region]**: Obtenga más información sobre las regiones de AWS en [Documentación de Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

   * La casilla de verificación **[!UICONTROL Use server side encryption]** permite almacenar el archivo en modo codificado S3. Obtenga información sobre cómo encontrar el ID de clave de acceso y la clave de acceso secreta en [Documentación de Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Almacenamiento de Azure Blob**

   La variable **Azure** la cuenta externa se puede utilizar para importar o exportar datos a Adobe Campaign mediante un **[!UICONTROL Transfer file]** actividad de flujo de trabajo. Para configurar la variable **Azure** cuenta externa para trabajar con Adobe Campaign, debe proporcionar los siguientes detalles:

   * **[!UICONTROL Server]**: URL del servidor de almacenamiento del blob de Azure.

   * **[!UICONTROL Encryption]**: Tipo de cifrado entre **[!UICONTROL None]** o **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Aprenda a encontrar su **[!UICONTROL Access key]** en [Documentación de Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).
