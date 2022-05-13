---
title: Work with Campaign and Microsoft Dynamics
description: Learn how to work with Campaign and Microsoft Dynamics
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 38%

---

# Work with Campaign and Microsoft Dynamics 365{#crm-ms-dynamics}

****

Once configuration is done, data synchronization between systems is carried out via a dedicated workflow activity. [Más información](crm-data-sync.md).

>[!NOTE]
>
>[](../start/compatibility-matrix.md)

Follow the steps below to configure a dedicated external account to import and export Microsoft Dynamics 365 data into Adobe Campaign.

For each system, these steps need to be performed by an administrator.

>[!CAUTION]
> Steps in this documentation will guide you through creating integrations/registrations that involve assigning permissions and/or admin access. It is your responsibility to ensure these steps comply with your company policies before performing, and to perform them carefully.

## Configuración de Microsoft Dynamics 365 {#config-crm-microsoft}

****[](https://portal.azure.com)****

1. Get your Dynamics 365 Application (client) ID. [Más información](#get-client-id-microsoft)
1. Genere el identificador de clave de certificado de Microsoft Dynamics e ID de clave. [Más información](#config-certificate-key-id)
1. Configure los permisos. [Más información](#config-permissions-microsoft)
1. Crear un usuario de aplicación. [Más información](#create-app-user-microsoft)
1. Codifique la clave privada. [Más información](#configure-acc-for-microsoftt)


### Get Dynamics 365 Client ID {#get-client-id-microsoft}

To get the Application (client) ID, you need to register an App in Azure Active Directory.

1. ********
1. **`<instance identifier>`**

**** You will need this ID later on in configuring Dynamics 365 in Adobe Campaign.

[](https://docs.microsoft.com/es-es/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory)

### Genere el identificador de clave de certificado de Microsoft Dynamics e ID de clave {#config-certificate-key-id}

******** Certificates can be used as secrets to prove the application’s identity when requesting a token. Also can be referred to as public keys.

Siga estos pasos:

1. ****
1. ****
1. ********
1. Upload your public certificate.
1. ************

**********[!UICONTROL CRM O-Auth type]**

+++ How to generate the public certificate

To generate the certificate, you can use openssl.

Por ejemplo:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>Puede cambiar el número de días, aquí `-days 365`, en el ejemplo de código para un periodo de validez de certificado más largo.

You must then encode the certificate in base64. Para ello, puede utilizar la ayuda de un codificador Base64 o utilizar la línea de comandos `base64 -w0 private.key` para Linux.

+++

### Configure los permisos {#config-permissions-microsoft}

**Paso 1**: Configurar los **Permisos requeridos** para la aplicación que se creó.

1. Vaya a **Azure Active Directory > Registros de aplicación** y seleccione la aplicación que se creó anteriormente.
1. Haga clic en **Configuración** en la parte superior izquierda.
1. En **Permisos requeridos**, haga clic en **Añadir** y, luego, en **Seleccionar una API > Dynamics CRM en línea**.
1. A continuación, haga clic en **Seleccionar**, active la casilla **Acceder a Dynamics 365 como usuarios de la organización** y haga clic en **Seleccionar**.
1. A continuación, desde la aplicación, seleccione el **Manifiesto** en el menú **Administrar**.
1. En el editor **Manifiesto**, establezca la propiedad `allowPublicClient` de `null` en `true` y haga clic en **Guardar**.

**Paso 2**: Conceder consentimiento de administrador

1. Vaya a **Azure Active Directory > Aplicaciones empresariales**.
1. Seleccione la aplicación a la que desea conceder el consentimiento de administrador para todo el inquilino.
1. En el menú del panel izquierdo, seleccione **Permisos** en **Seguridad**.
1. Haga clic en **Conceder consentimiento de administrador**.

Para obtener más información, consulte [Documentación de Azure](https://docs.microsoft.com/es-es/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### Crear un usuario de aplicación {#create-app-user-microsoft}

>[!NOTE]
>
> Este paso es opcional con autenticación **[!UICONTROL Password credentials]**.

El usuario de la aplicación es el usuario que usará la aplicación registrada arriba. Cualquier cambio realizado en Microsoft Dynamics mediante la aplicación registrada anteriormente se realizará mediante este usuario.

**Paso 1**: Crear un usuario no interactivo en el directorio activo de Azure

1. Haga clic en **Azure Active Directory > Usuarios** y, luego, en **Nuevo usuario**.
1. Proporcione el nombre pertinente que desee utilizar; además, el nombre de usuario debe estar en formato de correo electrónico.
1. Elija **Administrador de Dynamics 365** en la **Función de directorio**.

**Paso 2**: Asignar una licencia adecuada al usuario creado

1. En [Microsoft Azure](https://portal.azure.com), haga clic en **Aplicación de administración**.
1. Vaya a **Usuarios > Usuarios activos** y haga clic en el usuario recién creado.
1. Haga clic en **Editar licencias de producto** y seleccione el **Plan de participación del cliente de Dynamics 365**.
1. Haga clic en **Cerrar**.

**Paso 3**: Crear un usuario de aplicación en Dynamics CRM

1. En [Microsoft Azure](https://portal.azure.com), vaya a **Configuración > Seguridad > Usuarios**.
1. ********
1. Utilice el mismo nombre de usuario que el usuario creado en el directorio principal anterior.
1. Asigne el **ID de aplicación** para [la aplicación que creó anteriormente](#get-client-id-microsoft).
1. Haga clic en **Administrar funciones** y elija la función **Administrador del sistema** para el usuario.

## Configuración de Campaign {#configure-acc-for-microsoft}

### Create the connection{#new-ms-dyn-external-account}

First, you must create the Microsoft Dynamics 365 external account.

1. **[!UICONTROL Administration > Platform > External accounts]**
1. **[!UICONTROL Microsoft Dynamics CRM]******
1. **[!UICONTROL CRM O-Auth type]**

   ![](assets/ms-dyn-external-account.png)

   1. ****

      * **** To find your Microsoft CRM Server URL, access your Microsoft Dynamics CRM account then click Dynamics 365 and select your app. You can then find your Server URL in the address bar of your browser, e.g. https://myserver.crm.dynamics.com/.
      * ****
      * ****
      * ****
      * ****
   1. ****

      * **** To find your Microsoft CRM Server URL, access your Microsoft Dynamics CRM account then click Dynamics 365 and select your app. You can then find your Server URL in the address bar of your browser, e.g. https://myserver.crm.dynamics.com/.
      * ****[](#config-certificate-key-id)
      * ********[](#config-certificate-key-id)
      * ********[](#config-certificate-key-id)
      * ****[](#get-client-id-microsoft)
      * ****


1. ****

>[!NOTE]
>
>To approve the setup, log off and back on to the Adobe Campaign console.

### Select tables to synchronize{#ms-dyn-create-tables}

You can now configure tables to synchronize.

1. **[!UICONTROL Microsoft CRM configuration wizard...]**
1. Select the tables to synchronize and start the process.
1. Compruebe el esquema generado en Adobe Campaign en el nodo **[!UICONTROL Administration > Configuration > Data schemas]**.

>[!NOTE]
>
>`login.microsoftonline.com` To perform this, contact your Adobe representative.

## Sincronice las enumeraciones{#sfdc-enum-sync}

Once the schema is created, you can synchronize enumerations automatically from Dynamics 365 to Adobe Campaign.

1. **[!UICONTROL Synchronizing enumerations...]**
1. Select the Adobe Campaign enumeration that matches the Dynamics 365 enumeration.
Puede reemplazar todos los valores de una enumeración de Adobe Campaign con los del CRM: para hacerlo, seleccione **[!UICONTROL Yes]** en la columna **[!UICONTROL Replace]**.
1. **[!UICONTROL Next]****[!UICONTROL Start]**
1. **[!UICONTROL Administration > Platform > Enumerations]**

Adobe Campaign and Microsoft Dynamics 365 are now connected. Puede configurar la sincronización de datos entre los dos sistemas.

**[!UICONTROL CRM connector]**

Obtenga más información acerca de la sincronización de datos [en esta página](crm-data-sync.md).

### Tipos de datos de campo admitidos {#ms-dyn-supported-types}

Para Microsoft Dynamics 365, los tipos de atributos admitidos o no admitidos se enumeran a continuación:


| Tipo de atributo | Admitido |
| --------------------------------------------------------------------------------- | --------- |
| Tipos básicos: booleano, datetime, decimal, flotante, doble, entero, bigint, cadena | Sí |
| Dinero (como doble) | Sí |
| memo, entityname, primarykey, uniqueidentifier (como cadenas) | Sí |
| Estado, lista de selección (almacenamos los valores posibles en listas desglosadas), estado (cadena) | Sí |
| propietario (como cadena) | Sí |
| Búsqueda (solo búsquedas de referencia de entidad única) | Sí |
| cliente | No |
| Acerca de | No |
| PartyList | No |
| ManagedProperty | No |
