---
title: Cuentas externas de Campaign
description: Cuentas externas de Campaign
feature: Application Settings
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 18%

---


# Configuración de las cuentas externas

Adobe Campaign viene con un conjunto de cuentas externas predefinidas. Para configurar conexiones con sistemas externos, puede crear nuevas cuentas externas.

Los procesos técnicos utilizan las cuentas externas como flujos de trabajo técnicos o flujos de trabajo de campaña. Por ejemplo, al configurar una transferencia de archivos en un flujo de trabajo o un intercambio de datos con cualquier otra aplicación (Adobe Target, Experience Manager, etc.), debe seleccionar una cuenta externa.

Puede acceder a cuentas externas desde Adobe Campaign **[!UICONTROL Explorer]**: navegue hasta **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* Como usuario de Managed Cloud Service, las cuentas externas se configuran para su instancia por Adobe y no deben modificarse.
>
>* En el contexto de un [Implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), un específico **[!UICONTROL Full FDA]** (ffda) una cuenta externa administra la conexión entre la base de datos local de Campaign y la base de datos en la nube ([!DNL Snowflake]).
>

## Cuentas externas específicas de la campaña

Adobe Campaign utiliza las siguientes cuentas técnicas para habilitar y ejecutar procesos específicos.

### Correos devueltos {#bounce-mails-external-account}

>[!NOTE]
>
>La autenticación OAuth 2.0 de Microsoft Exchange Online para la capacidad POP3 está disponible a partir de la versión 8.3 de Campaign. Para comprobar su versión, consulte [esta sección](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).
>

La cuenta externa **Rebote de correos electrónicos** especifica la cuenta POP3 externa que se utilizará para conectar con el servicio de correo electrónico. Todos los servidores configurados para el acceso POP3 pueden utilizarse para recibir el correo electrónico devuelto.

Obtenga más información sobre los correos electrónicos entrantes en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html).

![](assets/bounce_external_1.png)

Para configurar la cuenta externa **[!UICONTROL Bounce mails (defaultPopAccount)]**:

* **[!UICONTROL Server]** - URL del servidor POP3.

* **[!UICONTROL Port]** - Número de puerto de conexión POP3. El puerto predeterminado es 110.

* **[!UICONTROL Account]** -  Nombre del usuario.

* **[!UICONTROL Password]** - Contraseña de la cuenta de usuario.

* **[!UICONTROL Encryption]** - Tipo de cifrado elegido entre **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** o **[!UICONTROL POP3S]**.

  La cuenta externa **Rebote de correos electrónicos** especifica la cuenta POP3 externa que se utilizará para conectar con el servicio de correo electrónico. Todos los servidores configurados para el acceso POP3 pueden utilizarse para recibir el correo electrónico devuelto.

* **[!UICONTROL Function]** - Correo electrónico entrante o enrutador SOAP

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Antes de configurar la cuenta externa POP3 con Microsoft OAuth 2.0, primero debe registrar la aplicación en Azure Portal. Para obtener más información, consulte esta [página](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.
>

Para configurar un POP3 externo con Microsoft OAuth 2.0, marque la **[!UICONTROL Microsoft OAuth 2.0]** y rellene los campos siguientes:

* **[!UICONTROL Azure tenant]** - ID de Azure (o ID de directorio (inquilino)) se puede encontrar en la variable **Essentials** menú desplegable de información general de la aplicación en el portal de Azure.

* **[!UICONTROL Azure Client ID]** : ID de cliente (o ID de aplicación (cliente)) se puede encontrar en la variable **Essentials** menú desplegable de información general de la aplicación en el portal de Azure.

* **[!UICONTROL Azure Client secret]** - El ID secreto de cliente se puede encontrar en la **Secretos de cliente** de la columna **Certificados y secretos** menú de la aplicación en el portal de Azure.

* **[!UICONTROL Azure Redirect URL]** - URL de redireccionamiento se puede encontrar en la **Autenticación** menú de la aplicación en el portal de Azure. Debe finalizar con la siguiente sintaxis `nl/jsp/oauth.jsp`, p. ej. `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

  Después de introducir las diferentes credenciales, puede hacer clic en **[!UICONTROL Setup the connection]** para finalizar la configuración de la cuenta externa.

### Enrutamiento {#routing}

La cuenta externa **[!UICONTROL Routing]** permite configurar cada canal disponible en Adobe Campaign según los paquetes instalados.

### Instancia de ejecución {#execution-instance}

En el contexto de los mensajes transaccionales, las instancias de ejecución se vinculan a la instancia de control y las conectan. Las plantillas de mensajes transaccionales se implementan en la instancia de ejecución. Obtenga más información acerca de la arquitectura del Centro de mensajes en [esta página](../architecture/architecture.md#transac-msg-archi).

## Acceso a cuentas externas de sistemas externos

* **Base de datos externa (FDA)** - El **Base de datos externa** La cuenta externa de tipo se utiliza para conectarse a una base de datos externa a través del acceso de datos federado (FDA). Obtenga más información acerca de la opción de acceso de datos federado (FDA) en [esta sección](../connect/fda.md).

  Las bases de datos externas compatibles con Adobe Campaign v8 se enumeran en la [Matriz de compatibilidad](../start/compatibility-matrix.md)

* **Twitter** - El **Twitter** El tipo de cuenta externa se utiliza para conectar Campaign a la cuenta de twitter y para publicar mensajes en su nombre. Obtenga más información sobre la integración de Twitteres en [esta sección](../connect/ac-tw.md).

## Adobe Integración de soluciones cuentas externas

* **Adobe Experience Cloud** - El **[!UICONTROL Adobe Experience Cloud]** La cuenta externa de se utiliza para implementar el servicio Identity Management de Adobe (IMS) y conectarse a Adobe Campaign. Obtenga más información acerca del servicio Identity Management de Adobe (IMS) en [esta sección](../start/connect.md#logon-to-ac).

* **Análisis web** - El **[!UICONTROL Web Analytics (Adobe Analytics)]** La cuenta externa de se utiliza para configurar la transferencia de datos de Adobe Analytics a Adobe Campaign. Obtenga más información sobre la integración de Adobe Campaign con Adobe Analytics en [esta página](../connect/ac-aa.md).

* **Adobe Experience Manager** - El **[!UICONTROL AEM]** Una cuenta externa de permite administrar el contenido de los envíos de correos electrónicos y los formularios directamente en Adobe Experience Manager. Obtenga más información sobre la integración de Adobe Campaign con Adobe Analytics en [esta página](../connect/ac-aem.md).


## Cuentas externas del conector CRM

* **Microsoft Dynamics CRM** - El **[!UICONTROL Microsoft Dynamics CRM]** Una cuenta externa de permite importar y exportar datos de Microsoft Dynamics en Adobe Campaign. Obtenga más información acerca de la integración de Adobe Campaign con Microsoft Dynamics CRM en [esta página](../connect/ac-ms-dyn.md).

* **Salesforce.com** - El **[!UICONTROL Salesforce CRM]** Una cuenta externa de permite importar y exportar datos de Salesforce a Adobe Campaign. Obtenga más información acerca de la integración de Adobe Campaign con Salesforce.com CRM en [esta página](../connect/ac-sfdc.md).

## Transferir datos a cuentas externas

Estas cuentas externas se pueden utilizar para importar o exportar datos a Adobe Campaign mediante una **[!UICONTROL Transfer file]** actividad de flujo de trabajo. Más información sobre **Transferencia de archivos** en flujos de trabajo en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html).

* **FTP y SFTP** - El **FTP** una cuenta externa de permite configurar y probar el acceso a un servidor fuera de Adobe Campaign. Para configurar conexiones con sistemas externos como servidores SFTP o FTP 898 utilizados para transferencias de archivos, puede crear cuentas externas propias.

  Para ello, especifique en esta cuenta externa la dirección y las credenciales utilizadas para establecer la conexión con el servidor SFTP o FTP.

  >[!NOTE]
  >
  >A partir de la versión 8.5, ahora puede autenticarse de forma segura con una clave privada al configurar su cuenta externa SFTP. [Más información sobre la administración de claves](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html)

* **Amazon Simple Storage Service (S3)** - El **AWS S3** El conector se puede utilizar para importar o exportar datos a Adobe Campaign mediante una **[!UICONTROL Transfer file]** actividad de flujo de trabajo. Al configurar esta nueva cuenta externa, debe proporcionar los siguientes detalles:

   * **[!UICONTROL AWS S3 Account Server]**: URL del servidor, rellenada de la siguiente manera:   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**: Obtenga información sobre cómo encontrar el ID de clave de acceso de AWS en [Documentación de Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: Obtenga información sobre cómo encontrar la clave de acceso secreta a AWS en [Documentación de Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: Obtenga más información sobre las regiones de AWS en [Documentación de Amazon](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * La casilla de verificación **[!UICONTROL Use server side encryption]** permite almacenar el archivo en modo codificado S3. Obtenga información sobre cómo encontrar el ID de clave de acceso y la clave de acceso secreta en [Documentación de Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Almacenamiento de Azure Blob** - El **Azure** una cuenta externa de se puede utilizar para importar o exportar datos a Adobe Campaign mediante una **[!UICONTROL Transfer file]** actividad de flujo de trabajo. Para configurar la variable **Azure** para trabajar con Adobe Campaign, debe proporcionar los siguientes detalles:

   * **[!UICONTROL Server]**: URL del servidor de Azure Blob Storage.

   * **[!UICONTROL Encryption]**: tipo de cifrado entre **[!UICONTROL None]** o **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Aprenda a encontrar su **[!UICONTROL Access key]** in [Documentación de Microsoft](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
