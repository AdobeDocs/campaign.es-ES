---
title: Cuentas externas de Campaign
description: Cuentas externas de Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 31%

---

# Configuración de las cuentas externas

Adobe Campaign viene con un conjunto de cuentas externas predefinidas. Para configurar conexiones con sistemas externos, puede crear nuevas cuentas externas.

Los procesos técnicos utilizan las cuentas externas como flujos de trabajo técnicos o flujos de trabajo de campaña. Por ejemplo, al configurar una transferencia de archivos en un flujo de trabajo o un intercambio de datos con cualquier otra aplicación (Adobe Target, Experience Manager, etc.), debe seleccionar una cuenta externa.

Puede acceder a cuentas externas desde Adobe Campaign **[!UICONTROL Explorer]**: buscar **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>Un **[!UICONTROL Full FDA]** (ffda) la cuenta externa administra la conexión entre la base de datos local de Campaign y la base de datos de Cloud ([!DNL Snowflake]).
>
>Como usuario de Cloud Services administrados, esta cuenta externa se configura para su instancia por Adobe. No debe modificarse.


## Cuentas externas específicas de la campaña

Adobe Campaign utiliza las siguientes cuentas técnicas para habilitar y ejecutar procesos específicos.

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, Adobe configura todas las cuentas externas específicas de Campaign para usted.

* **Correos devueltos (POP3)**

   La cuenta externa **Rebote de correos electrónicos** especifica la cuenta POP3 externa que se utilizará para conectar con el servicio de correo electrónico. Todos los servidores configurados para el acceso POP3 pueden utilizarse para recibir el correo electrónico devuelto.

   ![](../assets/do-not-localize/book.png) Obtenga más información sobre los correos electrónicos entrantes en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;}

* **Enrutamiento**

   La cuenta externa **[!UICONTROL Routing]** permite configurar cada canal disponible en Adobe Campaign según los paquetes instalados.

   >[!CAUTION]
   >
   >La variable **[!UICONTROL Internal email delivery routing]** Cuenta externa (defaultEmailBulk) **no debe** estar habilitado en Adobe Campaign v8.

* **Instancia de ejecución**

   En el contexto de los mensajes transaccionales, las instancias de ejecución están vinculadas a la instancia de control y las conectan. Las plantillas de mensajes transaccionales se implementan en la instancia de ejecución.

   ![](../assets/do-not-localize/glass.png) Obtenga más información sobre la arquitectura del Centro de mensajes en [esta página](../dev/architecture.md#transac-msg-archi).

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

   ![](../assets/do-not-localize/glass.png) Obtenga más información sobre la integración de Adobe Campaign con Microsoft Dynamics CRM en [esta página](../connect/crm.md).

   Con el tipo de implementación **[!UICONTROL Web API]** y la autenticación **[!UICONTROL Password credentials]**, debe proporcionar los siguientes detalles:

   * **[!UICONTROL Account]**: Cuenta utilizada para iniciar sesión en Microsoft CRM.

   * **[!UICONTROL Server]**: URL del servidor Microsoft CRM.

   * **[!UICONTROL Client identifier]**: El ID del cliente se puede encontrar desde el portal de administración de Microsoft Azure en el **[!UICONTROL Update your code]** categoría, **[!UICONTROL Client ID]** campo .

   * **[!UICONTROL CRM version]**: Versión de la CRM entre **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** o **[!UICONTROL Dynamics CRM 2016]**.
   Con el tipo de implementación **[!UICONTROL Web API]** y la autenticación **[!UICONTROL Certificate]**, debe proporcionar los siguientes detalles:

   * **[!UICONTROL Server]**: URL del servidor Microsoft CRM.

   * **[!UICONTROL Private Key (Base64 encoded)]**: Clave privada codificada en Base64

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**: El ID del cliente se puede encontrar desde el portal de administración de Microsoft Azure en el **[!UICONTROL Update your code]** categoría, **[!UICONTROL Client ID]** campo .

   * **[!UICONTROL CRM version]**: Versión de la CRM entre **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** o **[!UICONTROL Dynamics CRM 2016]**.


* **Salesforce.com**

   La cuenta externa **[!UICONTROL Salesforce CRM]** permite importar y exportar datos de Salesforce a Adobe Campaign.

   Para configurar la cuenta externa de Salesforce CRM para que funcione con Adobe Campaign, proporcione los siguientes detalles:

   * **[!UICONTROL Account]**: Cuenta utilizada para iniciar sesión en Salesforce CRM.

   * **[!UICONTROL Password]**: Contraseña utilizada para iniciar sesión en Salesforce CRM.

   * **[!UICONTROL Client identifier]**: Obtenga información sobre cómo encontrar el identificador de cliente en [esta página](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Security token]**: Obtenga información sobre cómo encontrar el token de seguridad en [esta página](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL API version]**: Seleccione la versión de la API. Para esta cuenta externa, debe configurar Salesforce CRM con el asistente para configuración.

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