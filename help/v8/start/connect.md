---
solution: Campaign v8
product: Adobe Campaign
title: Obtenga información sobre cómo conectarse a Campaign v8
description: Conexión a Campaign v8
feature: Audiencias
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 4ae0c968bd68d76d7ceffb91023d5426d6a810ea
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 11%

---

# Conectarse a Adobe Campaign v8{#gs-ac-connect}

La consola del cliente de Campaign es un cliente enriquecido que le permite conectarse a sus servidores de aplicaciones de Campaign.

Antes de empezar, debe:

* Compruebe la compatibilidad del sistema y las herramientas con Adobe Campaign en la [Matriz de compatibilidad](compatibility-matrix.md)
* Obtener la URL del servidor de Campaign
* Obtención de credenciales de usuario

## Descargar e instalar la consola de cliente

Al utilizar Campaign por primera vez, o si necesita actualizar a una versión más reciente, debe descargar la consola de cliente e instalarla.

Hay dos opciones disponibles:

1. Como administrador de Campaign, conéctese al Adobe [Distribución de software](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html) y descargue el programa de instalación de la Consola de cliente. A continuación, puede instalarlo en el equipo local.

1. Como usuario final, Adobe puede implementar la consola: una vez que se actualice la consola, se le pedirá que descargue la última versión de la consola de cliente en una ventana emergente.

>[!CAUTION]
>
>Adobe recomienda dejar la opción **[!UICONTROL No longer ask this question]** sin seleccionar para asegurarse de que todos los usuarios estén alertados cuando haya una nueva versión de la Consola disponible.  Si se selecciona esta opción, no se informará al usuario de las nuevas versiones disponibles.

## Crear la conexión

Una vez que la consola de cliente se haya instalado, siga los pasos a continuación para crear la conexión con el servidor de aplicaciones:

1. Inicie la Consola desde el menú Windows **[!UICONTROL Start]**, en el grupo de programas **Adobe Campaign**.

1. Haga clic en el vínculo en la esquina superior derecha de los campos de credenciales para acceder a la ventana de configuración de conexión.

1. Haga clic en **[!UICONTROL Add > Connection]** e introduzca la etiqueta y la dirección URL del servidor de aplicaciones de Adobe Campaign.

1. Especifique una conexión con el servidor de aplicaciones de Adobe Campaign a través de una URL. Utilice un DNS o un alias del equipo o su dirección IP.

   Por ejemplo, puede utilizar la dirección URL de tipo [`https://<machine>.<domain>.com`](https://myserver.adobe.com) .

1. Si Adobe Identity Management System (IMS) está configurado para su organización, marque la opción **[!UICONTROL Connect with an Adobe ID]** .

1. Haga clic en **[!UICONTROL Ok]** para guardar la configuración.

Puede agregar tantas conexiones como sea necesario para conectarse a los entornos de prueba, fase y producción, por ejemplo.

>[!NOTE]
>
>El botón **[!UICONTROL Add]** permite crear **[!UICONTROL folders]** para organizar todas las conexiones. Basta con arrastrar y colocar cada conexión en una carpeta.

## Iniciar sesión en Adobe Campaign

Para iniciar sesión en una instancia existente, siga los pasos a continuación:

1. Inicie la Consola desde el menú Windows **[!UICONTROL Start]**, en el grupo de programas **Adobe Campaign**.

1. Haga clic en el vínculo en la esquina superior derecha de los campos de credenciales para acceder a la ventana de configuración de conexión.

1. Seleccione la instancia de Campaign a la que debe iniciar sesión.

1. Haga clic en **[!UICONTROL Ok]**.

1. Introduzca sus credenciales de inicio de sesión de usuario y haga clic en **[!UICONTROL LOG IN]**.

   ![](assets/sign-in-v8.png)

Según la configuración, las credenciales pueden ser:

* proporcionado por el administrador de Campaign que le concedió acceso
* su Adobe ID

## Conceder acceso a los usuarios

Adobe Campaign le permite definir y administrar los derechos asignados a los distintos operadores. Se trata de un conjunto de derechos y restricciones que autorizan o niegan:

* Acceso a determinadas funciones (a través de los derechos asignados),
* Acceso a ciertos elementos,
* Cree, modifique o elimine elementos (envío, contactos, campañas, grupos, etc.).

Obtenga más información sobre los usuarios y cómo definir sus permisos en [esta sección](permissions.md).

Como administrador de Campaign, usted es el responsable de crear los operadores y compartir sus credenciales con los usuarios.

## Conéctese a Campaign con su Adobe ID{#connect-ims}

Los usuarios de Campaign pueden conectarse a la consola de Adobe Campaign mediante su Adobe ID, a través del sistema Identity Management de Adobe (IMS). Esta implementación ofrece las siguientes ventajas:

* Se puede utilizar la misma ID para todas las soluciones de Experience Cloud.
* Cada conexión se memoriza cuando se utiliza Adobe Campaign con diferentes integraciones.
* Política de administración de contraseñas más sólida.
* Uso de cuentas de ID federadas (proveedor de ID externo).

[!DNL :speech_balloon:] Como usuario de Cloud Services administrados,  [póngase en contacto con ](campaign-faq.md#support) Adobe para implementar IMS de Adobe con Campaign.

## Conectarse a Campaign con su inicio de sesión LDAP

Adobe Campaign se puede configurar para que el usuario acceda a la plataforma mediante su autenticación LDAP.

[!DNL :speech_balloon:] Como usuario de Cloud Services administrados,  [póngase en contacto con ](campaign-faq.md#support) Adobe para configurar la integración LDAP con Campaign.


## Acceso web{#web-access}

Se puede acceder a ciertas partes de la aplicación a través de un explorador web simple mediante una interfaz de usuario HTML: Panel de campañas, informes de cubos, supervisión de instancias, etc.

[!DNL :arrow_upper_right:] Obtenga más información sobre el acceso web en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#console-and-web-access)

El acceso web también se utiliza en el proceso de validación: Los operadores pueden hacer clic en el correo electrónico de solicitud de aprobación y conectarse a Campaign a través de su explorador web para validar o rechazar un contenido o presupuesto de envío.

[!DNL :arrow_upper_right:] Obtenga información sobre cómo configurar y administrar aprobaciones en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)
