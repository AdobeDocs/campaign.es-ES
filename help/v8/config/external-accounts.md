---
title: Cuentas externas de Campaign
description: Cuentas externas de Campaign
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 42241364c1a23ae75d8f0aaf18a2cb1c04ce5b0c
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 14%

---


# Configuración de las cuentas externas {#config-external-accounts}

Adobe Campaign viene con un conjunto de cuentas externas predefinidas. Para configurar conexiones con sistemas externos, puede crear nuevas cuentas externas.

Los procesos técnicos utilizan las cuentas externas como flujos de trabajo técnicos o flujos de trabajo de campaña. Por ejemplo, al configurar una transferencia de archivos en un flujo de trabajo o un intercambio de datos con cualquier otra aplicación (Adobe Target, Experience Manager, etc.), debe seleccionar una cuenta externa.

Puede acceder a cuentas externas desde Adobe Campaign **[!UICONTROL Explorer]**: vaya a **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* Como usuario de Cloud Services administrados, Adobe configura las cuentas externas para la instancia y no deben modificarse.
>
>* En el contexto de una implementación [Enterprise (FDAC) deployment](../architecture/enterprise-deployment.md), una cuenta externa específica de **[!UICONTROL Full FDA]** (FDAC) administra la conexión entre la base de datos local de Campaign y la base de datos en la nube ([!DNL Snowflake]).
>

## Cuentas externas específicas de la campaña {#ac-external-accounts}

Adobe Campaign utiliza las siguientes cuentas técnicas para habilitar y ejecutar procesos específicos.

### Correos rechazados {#bounce-mails-external-account}

>[!NOTE]
>
>La autenticación OAuth 2.0 de Microsoft Exchange Online para la capacidad POP3 está disponible a partir de la versión 8.3 de Campaign. Para comprobar su versión, consulte [esta sección](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).
>

La cuenta externa **Rebote de correos electrónicos** especifica la cuenta POP3 externa que se utilizará para conectar con el servicio de correo electrónico. Todos los servidores configurados para el acceso POP3 pueden utilizarse para recibir el correo electrónico devuelto.

Obtenga más información acerca de los correos electrónicos entrantes en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html){target="_blank"}.

![](assets/bounce_external_1.png)

Para configurar la cuenta externa **[!UICONTROL Bounce mails (defaultPopAccount)]**:

* **[!UICONTROL Server]**: URL del servidor POP3.

* **[!UICONTROL Port]** - número de puerto de conexión POP3. El puerto predeterminado es 110.

* **[!UICONTROL Account]** - Nombre del usuario.

* **[!UICONTROL Password]** - Contraseña de cuenta de usuario.

* **[!UICONTROL Encryption]** - Tipo de cifrado elegido entre **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** o **[!UICONTROL POP3S]**.

  La cuenta externa **Rebote de correos electrónicos** especifica la cuenta POP3 externa que se utilizará para conectar con el servicio de correo electrónico. Todos los servidores configurados para el acceso POP3 pueden utilizarse para recibir el correo electrónico devuelto.

* **[!UICONTROL Function]**: correo electrónico entrante o enrutador de SOAP

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Antes de configurar la cuenta externa POP3 con Microsoft OAuth 2.0, primero debe registrar la aplicación en Azure Portal. Para obtener más información, consulte esta [página](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.
>

Para configurar un POP3 externo mediante Microsoft OAuth 2.0, marque la opción **[!UICONTROL Microsoft OAuth 2.0]** y rellene los campos siguientes:

* **[!UICONTROL Azure tenant]** - ID de Azure (o ID de directorio (inquilino)) se encuentra en la lista desplegable **Essentials** de la descripción general de la aplicación en el portal de Azure.

* **[!UICONTROL Azure Client ID]** - ID de cliente (o ID de aplicación (cliente)) se encuentra en la lista desplegable **Essentials** de la descripción general de la aplicación en el portal de Azure.

* **[!UICONTROL Azure Client secret]**: el id. de secreto de cliente se encuentra en la columna **Secretos de cliente** del menú **Certificados y secretos** de su aplicación en el portal de Azure.

* **[!UICONTROL Azure Redirect URL]**: la dirección URL de redireccionamiento se encuentra en el menú **Autenticación** de su aplicación en el portal de Azure. Debe finalizar con la siguiente sintaxis `nl/jsp/oauth.jsp`, p. ej. `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

  Después de escribir las diferentes credenciales, puede hacer clic en **[!UICONTROL Setup the connection]** para finalizar la configuración de la cuenta externa.

### Enrutamiento {#routing}

La cuenta externa **[!UICONTROL Routing]** permite configurar cada canal disponible en Adobe Campaign según los paquetes instalados.

Obtenga más información acerca de la administración de cuentas externas y la ejecución de envíos en [esta sección](../architecture/architecture.md#split).

### Instancia de ejecución {#execution-instance}

En el contexto de los mensajes transaccionales, las instancias de ejecución se vinculan a la instancia de control y las conectan. Las plantillas de mensajes transaccionales se implementan en la instancia de ejecución. Obtenga más información acerca de la arquitectura del Centro de mensajes en [esta página](../architecture/architecture.md#transac-msg-archi).

## Acceso a cuentas externas de sistemas externos {#external-syst-external-accounts}

* **Base de datos externa (FDA)** - La cuenta externa de tipo **Base de datos externa** se usa para conectarse a una base de datos externa a través del acceso de datos federado (FDA). Obtenga más información acerca de la opción de acceso de datos federado (FDA) en [esta sección](../connect/fda.md).

  Las bases de datos externas compatibles con Adobe Campaign v8 se enumeran en la [Matriz de compatibilidad](../start/compatibility-matrix.md)

* **X (anteriormente conocido como Twitter)**: La cuenta externa de tipo **Twitter** se usa para conectar Campaign a su cuenta X y publicar mensajes en su nombre. Obtenga más información acerca de la integración X en [esta sección](../connect/ac-tw.md).

## Cuentas externas de Adobe Solution Integration {#adobe-integration-external-accounts}

* **Adobe Experience Cloud**: la cuenta externa **[!UICONTROL Adobe Experience Cloud]** se usa para implementar el servicio Adobe Identity Management (IMS) y conectarse a Adobe Campaign. Obtenga más información acerca del servicio Adobe Identity Management (IMS) en [esta sección](../start/connect.md#logon-to-ac).

* **Web Analytics**: la cuenta externa **[!UICONTROL Web Analytics (Adobe Analytics)]** se usa para configurar la transferencia de datos de Adobe Analytics a Adobe Campaign. Obtenga más información acerca de la integración de Adobe Campaign con Adobe Analytics en [esta página](../connect/ac-aa.md).

* **Adobe Experience Manager**: la cuenta externa **[!UICONTROL AEM]** le permite administrar el contenido de las entregas de los correos electrónicos y los formularios directamente en Adobe Experience Manager. Obtenga más información acerca de la integración de Adobe Campaign con Adobe Analytics en [esta página](../connect/ac-aem.md).


## Cuentas externas del conector CRM {#crm-external-accounts}

* **Microsoft Dynamics CRM**: la cuenta externa **[!UICONTROL Microsoft Dynamics CRM]** le permite importar y exportar datos de Microsoft Dynamics en Adobe Campaign. Obtenga más información acerca de la integración de Adobe Campaign con Microsoft Dynamics CRM en [esta página](../connect/ac-ms-dyn.md).

* **Salesforce.com**: la cuenta externa **[!UICONTROL Salesforce CRM]** le permite importar y exportar datos de Salesforce en Adobe Campaign. Obtenga más información acerca de la integración de Adobe Campaign con Salesforce.com CRM en [esta página](../connect/ac-sfdc.md).

## Transferir datos a cuentas externas {#transfer-data-external-accounts}

Estas cuentas externas se pueden usar para importar o exportar datos a Adobe Campaign mediante una actividad de flujo de trabajo **[!UICONTROL Transfer file]**. Obtenga más información acerca de **Transferencia de archivos** en los flujos de trabajo de [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html){target="_blank"}.

* **FTP y SFTP**: la cuenta externa **FTP** permite configurar y probar el acceso a un servidor fuera de Adobe Campaign. Para configurar conexiones con sistemas externos como servidores SFTP o FTP 898 utilizados para transferencias de archivos, puede crear cuentas externas propias.

  Para ello, especifique en esta cuenta externa la dirección y las credenciales utilizadas para establecer la conexión con el servidor SFTP o FTP.

  >[!NOTE]
  >
  >A partir de la versión 8.5, ahora puede autenticarse de forma segura con una clave privada al configurar su cuenta externa SFTP. [Más información sobre la administración de claves](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html){target="_blank"}.

* **Amazon Simple Storage Service (S3)**: el conector **AWS S3** se puede usar para importar o exportar datos a Adobe Campaign mediante una actividad de flujo de trabajo **[!UICONTROL Transfer file]**. Al configurar esta nueva cuenta externa, debe proporcionar los siguientes detalles:

   * **[!UICONTROL AWS S3 Account Server]**: dirección URL del servidor, rellenada de la siguiente manera:   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**: Aprenda a encontrar su ID de clave de acceso de AWS en [Documentación de Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: aprenda a encontrar su clave de acceso secreta a AWS en [Documentación de Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: Obtenga más información sobre las regiones de AWS en [Documentación de Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * La casilla de verificación **[!UICONTROL Use server side encryption]** le permite almacenar el archivo en modo codificado S3. Aprenda a encontrar el ID de clave de acceso y la clave de acceso secreta en [Documentación de Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Almacenamiento de blob de Azure**: la cuenta externa de **Azure** se puede usar para importar o exportar datos a Adobe Campaign mediante una actividad de flujo de trabajo de **[!UICONTROL Transfer file]**. Para configurar la cuenta externa de **Azure** para que funcione con Adobe Campaign, debe proporcionar los siguientes detalles:

   * **[!UICONTROL Server]**: URL del servidor de Azure Blob Storage.

   * **[!UICONTROL Encryption]**: tipo de cifrado entre **[!UICONTROL None]** o **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Aprenda a encontrar su **[!UICONTROL Access key]** en [documentación de Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
