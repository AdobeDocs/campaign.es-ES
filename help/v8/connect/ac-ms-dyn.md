---
title: Trabajo con Campaign y Microsoft Dynamics
description: Aprenda a trabajar con Campaign y Microsoft Dynamics
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 36%

---

# Trabajo con Campaign y Microsoft Dynamics 365{#crm-ms-dynamics}

Active los datos de CRM en la comunicación entre canales: Aprenda a pasar contactos de **Microsoft Dynamics 365** a Adobe Campaign y a compartir los datos de rendimiento de la campaña (envíos, aperturas, clics y devoluciones) de Adobe Campaign a Microsoft Dynamics 365.

Una vez completada la configuración, la sincronización de datos entre sistemas se realiza mediante una actividad de flujo de trabajo dedicada. [Más información](crm-data-sync.md).

>[!NOTE]
>
>Las versiones compatibles de Microsoft Dynamics se detallan en Campaign [Compatibility matrix](../start/compatibility-matrix.md).

Siga los pasos a continuación para configurar una cuenta externa dedicada para importar y exportar datos de Microsoft Dynamics 365 en Adobe Campaign.

Para cada sistema, estos pasos debe realizarlos un administrador.

>[!CAUTION]
> Los pasos de esta documentación le guiarán a través de la creación de integraciones/registros que impliquen la asignación de permisos o acceso de administrador. Es su responsabilidad asegurarse de que estos pasos cumplan con las políticas de su compañía antes de realizarlos, y realizarlos cuidadosamente.

## Configuración de Microsoft Dynamics 365 {#config-crm-microsoft}

Para conectar Microsoft Dynamics 365 y trabajar con Adobe Campaign mediante **API web**, inicie sesión en [Microsoft Azure Directory](https://portal.azure.com) con una credencial de **administrador global** y siga los pasos a continuación:

1. Obtenga su ID de aplicación (cliente) de Dynamics 365. [Más información](#get-client-id-microsoft)
1. Genere el identificador de clave de certificado de Microsoft Dynamics y el ID de clave. [Más información](#config-certificate-key-id)
1. Configure los permisos. [Más información](#config-permissions-microsoft)
1. Crear un usuario de aplicación. [Más información](#create-app-user-microsoft)
1. Codifique la clave privada. [Más información](#configure-acc-for-microsoftt)


### Obtener el ID de cliente de Dynamics 365 {#get-client-id-microsoft}

Para obtener el ID de aplicación (cliente), debe registrar una aplicación en Azure Active Directory.

1. Vaya a **Azure Active Directory > Registros de aplicación** y seleccione **Nuevo registro**.
1. Escriba un nombre único que pueda ayudar a identificar una instancia, como **adobecampaign`<instance identifier>`**.

Una vez guardado, el directorio de Microsoft Azure asigna una **ID de aplicación (cliente)** única a su aplicación. Necesitará este ID más adelante en la configuración de Dynamics 365 en Adobe Campaign.

Obtenga más información en [Documentación de Microsoft Dynamics 365](https://docs.microsoft.com/es-es/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target="_blank"}.

### Genere el identificador de clave de certificado de Microsoft Dynamics e ID de clave {#config-certificate-key-id}

Para obtener el **Identificador de clave de certificado (customKeyIdentifier)** y el **ID de clave (keyId)**, debe cargar un certificado. Los certificados se pueden utilizar como secretos para probar la identidad de la aplicación al solicitar un token. También se pueden denominar claves públicas.

Siga estos pasos:

1. Vaya a **Azure Active Directory > Registros de aplicación** y seleccione la aplicación que se creó anteriormente.
1. Seleccionar en **Certificados y secretos**.
1. En la ficha **Certificados**, haga clic en **Cargar certificado**
1. Cargue el certificado público.
1. Vaya al vínculo **Manifiesto** para obtener el **Identificador de clave de certificado (customKeyIdentifier)** y el **ID de clave (keyId)**.

El identificador de clave de certificado **customKeyIdentifier** y el **ID de clave (keyId)** son necesarios en Campaign para configurar la cuenta externa de CRM de Microsoft Dynamics 365 mediante el certificado **[!UICONTROL CRM O-Auth type]**.

+++ Cómo generar el certificado público

Para generar el certificado, puede utilizar openssl.

Por ejemplo:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>Puede cambiar el número de días, aquí `-days 365`, en el ejemplo de código para un periodo de validez de certificado más largo.

Luego debe codificar el certificado en base64. Para ello, puede utilizar la ayuda de un codificador Base64 o utilizar la línea de comandos `base64 -w0 private.key` para Linux.

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
1. Haga clic en el menú desplegable, seleccione **Usuarios de la aplicación** y haga clic en **Nuevo**.
1. Utilice el mismo nombre de usuario que el usuario creado en el directorio principal anterior.
1. Asigne el **ID de aplicación** para [la aplicación que creó anteriormente](#get-client-id-microsoft).
1. Haga clic en **Administrar funciones** y elija la función **Administrador del sistema** para el usuario.

## Configuración de Campaign {#configure-acc-for-microsoft}

### Creación de la conexión{#new-ms-dyn-external-account}

Primero, debe crear la cuenta externa de Microsoft Dynamics 365.

1. Examine el nodo **[!UICONTROL Administration > Platform > External accounts]** del explorador de Campaign y cree una cuenta externa.
1. Seleccione la cuenta externa **[!UICONTROL Microsoft Dynamics CRM]** en la sección **Tipo**.
1. Seleccione el método de autenticación en la lista desplegable **[!UICONTROL CRM O-Auth type]**.

   ![](assets/ms-dyn-external-account.png)

   1. Para configurar la cuenta externa de Microsoft Dynamics CRM para que se conecte con Adobe Campaign con **credenciales de contraseña**, proporcione los siguientes detalles:

      * **Servidor**: URL de su servidor Microsoft CRM. Para encontrar la URL del servidor de Microsoft CRM, acceda a su cuenta de Microsoft Dynamics CRM, haga clic en Dynamics 365 y seleccione la aplicación. A continuación, puede encontrar la URL del servidor en la barra de direcciones del explorador, por ejemplo: https://myserver.crm.dynamics.com/.
      * **Cuenta**: Cuenta utilizada para iniciar sesión en Microsoft CRM.
      * **Contraseña**: Cuenta utilizada para iniciar sesión en Microsoft CRM.
      * **Identificador de cliente**: ID de aplicación (cliente) que se puede encontrar desde el portal de administración de Microsoft Azure en la categoría Update your code, campo Client ID.
      * **CRM version**: Elija Dynamics CRM 365 CRM version.

   1. Para configurar la cuenta externa de Microsoft Dynamics CRM para que se conecte con Adobe Campaign con un **Certificado**, proporcione los siguientes detalles:

      * **Servidor**: URL de su servidor Microsoft CRM. Para encontrar la URL del servidor de Microsoft CRM, acceda a su cuenta de Microsoft Dynamics CRM, haga clic en Dynamics 365 y seleccione la aplicación. A continuación, puede encontrar la URL del servidor en la barra de direcciones del explorador, por ejemplo: https://myserver.crm.dynamics.com/.
      * **Clave privada**: copie/pegue la clave privada, codificada en base64 como se explica en [esta sección](#config-certificate-key-id).
      * **Id. de clave**: Clave disponible en la ficha **Manifiesto** de su aplicación, tal como se explica en [esta sección](#config-certificate-key-id).
      * **Identificador de clave personalizada**: identificador disponible en la ficha **Manifiesto** de su aplicación, tal como se explica en [esta sección](#config-certificate-key-id).
      * **Identificador de cliente**: ID de aplicación (cliente) que se puede encontrar desde el portal de administración de Microsoft Azure como se explica en [esta sección](#get-client-id-microsoft).
      * **CRM version**: Elija Dynamics CRM 365 CRM version.

1. Seleccione la opción **Enable** para activar la cuenta en Campaign.

>[!NOTE]
>
>Para aprobar la instalación, cierre la sesión y vuelva a iniciarla en la consola del cliente de Adobe Campaign.

### Seleccionar tablas para sincronizar{#ms-dyn-create-tables}

Ahora puede configurar tablas para sincronizar.

1. Haga clic en **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. Seleccione las tablas para sincronizar e iniciar el proceso.
1. Compruebe el esquema generado en Adobe Campaign en el nodo **[!UICONTROL Administration > Configuration > Data schemas]**.

>[!NOTE]
>
>Asegúrese de agregar a la lista de permitidos dos direcciones URL: la del servidor y `login.microsoftonline.com`. Para ello, póngase en contacto con su representante de Adobe.

## Sincronice las enumeraciones{#sfdc-enum-sync}

Una vez creado el esquema, puede sincronizar las enumeraciones automáticamente desde Dynamics 365 a Adobe Campaign.

1. Abra el asistente desde el vínculo **[!UICONTROL Synchronizing enumerations...]**.
1. Seleccione la enumeración de Adobe Campaign que coincida con la enumeración de Dynamics 365.
Puede reemplazar todos los valores de una enumeración de Adobe Campaign con los del CRM: para hacerlo, seleccione **[!UICONTROL Yes]** en la columna **[!UICONTROL Replace]**.
1. Haga clic en **[!UICONTROL Next]** y luego en **[!UICONTROL Start]** para comenzar a importar las enumeraciones.
1. Examine el nodo **[!UICONTROL Administration > Platform > Enumerations]** para comprobar los valores importados.

Adobe Campaign y Microsoft Dynamics 365 ya están conectados. Puede configurar la sincronización de datos entre los dos sistemas.

Para sincronizar datos entre los datos de Adobe Campaign y Microsoft CRM, cree un flujo de trabajo y utilice la actividad **[!UICONTROL CRM connector]**.

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
