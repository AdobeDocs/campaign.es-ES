---
title: Conexión a Campaign v8
description: Aprenda a conectarse a la versión 8 de Campaign
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 13%

---

# Conexión a Adobe Campaign v8{#gs-ac-connect}

La consola del cliente de Campaign es un cliente enriquecido que le permite conectarse a sus servidores de aplicaciones de Campaign.

Antes de empezar, debe:

* Compruebe la compatibilidad del sistema y las herramientas con Adobe Campaign en la [Matriz de compatibilidad](compatibility-matrix.md)
* Obtener la URL del servidor de Campaign
* Cree su Adobe ID u obtenga sus credenciales de usuario de su empresa
* Instale el tiempo de ejecución de Microsoft Edge Webview2 en su sistema (desde la versión de compilación de Campaign Classic 8.4). [Más información](#webview)

## Instalación del tiempo de ejecución de Microsoft Edge Webview2 {#webview}

A partir de la versión de compilación de Campaign Classic 8.4, se requiere la instalación del tiempo de ejecución de Microsoft Edge Webview 2 para cualquier instalación de consola.

La vista web se instala de forma predeterminada como parte del sistema operativo Windows 11. Si aún no está presente en el sistema, el instalador de la consola de Campaign le pedirá que lo descargue de [Sitio web del desarrollador de Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_es). Tenga en cuenta que el vínculo de descarga no funciona en el explorador Internet Explorer 11, ya que Microsoft ha dejado de ofrecer soporte técnico. Asegúrese de utilizar un explorador diferente para acceder al vínculo.

## Descargar e instalar la consola de cliente{#download-ac-console}

Al utilizar Campaign por primera vez, o si necesita actualizar a una versión más reciente, debe descargar la consola de cliente e instalarla.

Hay dos opciones disponibles:

1. Como administrador de Campaign, conéctese a Adobe [Distribución de software](https://experience.adobe.com/#/downloads/content/software-distribution/es/campaign.html) y descargue el programa de instalación de la consola de cliente. A continuación, puede instalarlo en el equipo local.

1. Como usuario final, Adobe puede implementar la consola: una vez que se actualice la consola, se le pedirá que descargue la última versión de la consola de cliente en una ventana emergente.

>[!CAUTION]
>
>Adobe recomienda dejar la opción **[!UICONTROL No longer ask this question]** no está seleccionado para asegurarse de que todos los usuarios reciben una alerta cuando hay una nueva versión de la Consola disponible.  Si se selecciona esta opción, no se informará al usuario de las nuevas versiones disponibles.

## Crear la conexión{#create-your-connection}

Una vez que la consola de cliente se haya instalado, siga los pasos a continuación para crear la conexión con el servidor de aplicaciones:

1. Iniciar la consola desde Windows **[!UICONTROL Start]** en el **Adobe Campaign** grupo de programas.

1. Haga clic en el vínculo en la esquina superior derecha de los campos de credenciales para acceder a la ventana de configuración de conexión.

1. Haga clic en **[!UICONTROL Add > Connection]** e introduzca la etiqueta y la URL del servidor de aplicaciones de Adobe Campaign.

1. Especifique una conexión con el servidor de aplicaciones de Adobe Campaign a través de una URL. Utilice un DNS o un alias del equipo o su dirección IP.

   Por ejemplo, puede usar la variable [`https://<machine>.<domain>.com`](https://myserver.adobe.com) escriba URL.

1. Marque la opción **[!UICONTROL Connect with an Adobe ID]**.

1. Haga clic en **[!UICONTROL Ok]** para guardar la configuración.

Puede agregar tantas conexiones como sea necesario para conectarse a los entornos de prueba, fase y producción, por ejemplo.

>[!NOTE]
>
>El botón **[!UICONTROL Add]** permite crear **[!UICONTROL folders]** para organizar todas las conexiones. Basta con arrastrar y colocar cada conexión en una carpeta.

## Iniciar sesión en Adobe Campaign {#logon-to-ac}

Para iniciar sesión en una instancia existente, siga los pasos a continuación:

1. Iniciar la consola desde Windows **[!UICONTROL Start]** en el **Adobe Campaign** grupo de programas.

1. Haga clic en el vínculo en la esquina superior derecha de los campos de credenciales para acceder a la ventana de configuración de conexión.

   ![](assets/connectToCampaign.png)

1. Seleccione la instancia de Campaign a la que debe iniciar sesión.

1. Haga clic en **[!UICONTROL Ok]**.

1. A continuación, puede iniciar sesión en Campaign con [su Adobe ID](#connect-ims).

   ![](assets/adobeID.png)

>[!NOTE]
>
>Para las versiones de compilación 8.4 de campaign classic, la consola del cliente de Adobe Campaign puede solicitar credenciales de proxy dos veces durante la autenticación de proxy. Esto se debe a que Microsoft Edge Webview2 no guarda las credenciales de proxy en el almacén de caché/contraseña a diferencia de Internet Explorer.

## Conceder acceso a los usuarios{#grant-access}

Adobe Campaign le permite definir y administrar los derechos asignados a los distintos operadores. Se trata de un conjunto de derechos y restricciones que autorizan o niegan:

* Acceso a determinadas funciones (a través de los derechos asignados),
* Acceso a ciertos elementos,
* Cree, modifique o elimine elementos (envío, contactos, campañas, grupos, etc.).

Obtenga más información sobre los usuarios y cómo definir sus permisos en [esta sección](permissions.md).

Como administrador de Campaign, usted es el responsable de crear los operadores y compartir sus credenciales con los usuarios.

## Conectarse a Campaign con su Adobe ID{#connect-ims}

Los usuarios de Campaign se conectan a la consola de Adobe Campaign mediante su Adobe ID, a través del sistema Identity Management de Adobe (IMS). Pueden usar el mismo ID en todas las soluciones de Adobe. La conexión se guarda al usar Adobe Campaign con otras soluciones.

Obtenga más información sobre Adobe IMS en [esta página](https://helpx.adobe.com/es/enterprise/using/identity.html).

## Acceso web{#web-access}

Se puede acceder a ciertas partes de la aplicación a través de un explorador web mediante una interfaz de usuario de HTML: informes, aprobación de envíos, supervisión de instancias, etc.

El acceso web proporciona una interfaz similar a la consola pero con un conjunto reducido de funcionalidades.

Por ejemplo, para un operador determinado, una campaña se mostrará con las siguientes opciones en la consola:

![](assets/campaign-from-console.png)

Mientras que con el acceso web, las opciones permiten principalmente la visualización de:

![](assets/campaign-from-web.png)

El acceso web también se utiliza en el proceso de validación: Los operadores pueden hacer clic en el correo electrónico de solicitud de aprobación y conectarse a Campaign a través de su explorador web para validar o rechazar un contenido o presupuesto de envío.

Para acceder a la instancia de Campaign desde la web, la dirección URL es:  `https://<your adobe campaign server>:<port number>/view/home`.
