---
title: Conexión a la versión 8 de Campaign
description: Aprenda a conectarse a Adobe Campaign, versión 8, y a instalar la consola en su equipo para disfrutar de un acceso más sencillo.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: ht
source-wordcount: '1006'
ht-degree: 100%

---

# Conexión a la versión 8 de Adobe Campaign{#gs-ac-connect}

Para comenzar a trabajar con Campaign, debe instalar y configurar la consola del cliente.

La consola del cliente es una aplicación nativa que se comunica con el servidor de aplicaciones de Adobe Campaign a través de protocolos de internet estándar, como SOAP y HTTP. La consola del cliente de Campaign centraliza todas las funcionalidades y configuraciones y requiere un ancho de banda mínimo, ya que depende de una caché local. Diseñada para facilitar su implementación, la consola de cliente de Campaign se puede implementar desde un explorador de internet, se puede actualizar automáticamente y no requiere ninguna configuración de red específica porque solo genera tráfico HTTP(S).

Antes de empezar, debe hacer lo siguiente:

* Comprobar la compatibilidad del sistema y las herramientas con Adobe Campaign en la [matriz de compatibilidad](compatibility-matrix.md)
* Obtener la URL del servidor de Campaign
* Crear su Adobe ID o conseguir sus credenciales de usuario de su compañía
* Instalar el tiempo de ejecución de Microsoft Edge WebView2 en su sistema. [Más información](#webview)

## Instalación de la consola de cliente{#download-ac-console}

### Tiempo de ejecución de Microsoft Edge WebView2 {#webview}

A partir de la versión de compilación 8.4 de Campaign Classic, se requiere la instalación del tiempo de ejecución de Microsoft Edge WebView 2 para cualquier instalación de la consola del cliente.

WebView se instala de forma predeterminada como parte del sistema operativo Windows 11. Si no está presente en el sistema, el programa de instalación de la consola del cliente de Campaign le pedirá que lo descargue desde el [sitio web del desarrollador de Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_es){target="_blank"}. Tenga en cuenta que el vínculo de descarga no funciona en el explorador internet Explorer 11, ya que Microsoft ha dejado de ofrecerle soporte. Asegúrese de utilizar un explorador diferente para acceder al vínculo.

### Descarga de la consola{#install-ac-console}

Cuando utilice Campaign por primera vez, debe descargar la consola del cliente e instalarla.

Hay dos opciones disponibles para descargar la consola del cliente:

1. Como administrador de Campaign, conéctese a la [Distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/es/campaign.html){target="_blank"}.

1. Como usuario final, el administrador de Campaign implementa automáticamente la consola del cliente y la pone a su disposición a través de una dirección URL dedicada.

Una vez descargado el programa de instalación de la consola del cliente, instálelo en el equipo local.

Tenga en cuenta que no puede cambiar el idioma de la consola del cliente una vez que está instalada.

## Creación de la conexión{#create-your-connection}

Una vez instalada la consola del cliente, siga los pasos que se indican a continuación para crear la conexión con el servidor de aplicaciones:

1. Inicie la consola y examine el vínculo en la esquina derecha para acceder a la pantalla de configuración de la conexión.

1. Haga clic en **[!UICONTROL Add > Connection]** e introduzca la etiqueta y la dirección URL del servidor de aplicaciones de Adobe Campaign.

1. Especifique una conexión con el servidor de aplicaciones de Adobe Campaign mediante una dirección URL. Utilice un DNS o un alias del equipo, o su dirección IP.

   Por ejemplo, puede usar la dirección URL de tipo `https://<machine>.<domain>.com`.

1. Marque la opción **[!UICONTROL Connect with an Adobe ID]**.

1. Haga clic en **[!UICONTROL Ok]** para guardar su configuración.

Puede añadir tantas conexiones como sea necesario para conectarse a los entornos de prueba, fase y producción, por ejemplo.

>[!NOTE]
>
>El botón **[!UICONTROL Add]** le permite crear **[!UICONTROL folders]** para organizar todas las conexiones. Basta con arrastrar y colocar cada conexión en una carpeta.

## Inicio de sesión en Adobe Campaign {#logon-to-ac}

Los usuarios de Campaign se conectan a la consola de Adobe Campaign mediante su Adobe ID a través del sistema de administración de identidades (IMS) de Adobe. Pueden utilizar el mismo ID en todas las soluciones de Adobe. Cada conexión se guarda cuando se utiliza Adobe Campaign con otras soluciones. Obtenga más información sobre Adobe IMS en [esta página](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"}.

Para iniciar sesión en una instancia, siga los pasos que se indican a continuación:

1. Inicie la consola y examine el vínculo en la esquina derecha para acceder a la pantalla de configuración de la conexión.

   ![](assets/connectToCampaign.png)

1. Seleccione la instancia de Campaign en la que debe iniciar sesión.

1. Haga clic en **[!UICONTROL Ok]**.

A continuación, puede iniciar sesión en Campaign con su Adobe ID.

![](assets/adobeID.png)

>[!NOTE]
>
>Como Microsoft Edge WebView2 no guarda las credenciales de proxy, la consola puede solicitarle que se autentique dos veces en la primera conexión.

## Actualización de la consola de cliente{#upgrade-ac-console}

Cuando el sistema se actualice a una versión más reciente, deberá actualizar la consola de cliente a esa misma versión. Es una práctica recomendada y, en algunas versiones, esta actualización es obligatoria. En ese caso, consulte las [Notas de la versión](release-notes.md).

Como usuario de Managed Cloud Services, Adobe implementa la consola de cliente por usted. Cuando se conecte al entorno actualizado, se le pedirá que descargue la versión más reciente de la consola del cliente en una ventana emergente. Debe aceptar esta actualización y actualizar la consola de cliente según se le solicite.

>[!CAUTION]
>
>Adobe recomienda dejar la opción **[!UICONTROL No longer ask this question]** sin seleccionar para asegurarse de que recibe un aviso cuando haya disponible una nueva versión de la consola. Si se selecciona esta opción, el usuario no está informado de que se requiere una actualización de la consola.
>



## Concesión del acceso a los usuarios{#grant-access}

Adobe Campaign le permite definir y administrar los derechos asignados a los distintos operadores.

Como administrador de Campaign, es responsable de crear los operadores y compartir sus credenciales con los usuarios.

Obtenga más información sobre los usuarios y cómo definir sus permisos en [esta sección](gs-permissions.md).


## Acceso a Campaign con un explorador web {#connect-web-ac}

### Interfaz de usuario web {#connect-web-ui}

A partir de Campaign v8.6, tendrá acceso a la nueva **interfaz de usuario web de Campaign**, disponible a través del entorno central de Adobe Experience Cloud. Experience Cloud es la familia integrada de aplicaciones, productos y servicios de marketing digital de Adobe. Desde su intuitiva interfaz, puede acceder rápidamente a sus aplicaciones, funciones de productos y servicios en la nube.

>[!AVAILABILITY]
>
>La interfaz de usuario web de Campaign solo está disponible para los usuarios que se conectan a Adobe Campaign con su Adobe ID. Obtenga más información sobre el [sistema de administración de identidades (IMS) de Adobe](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"}.
>

Obtenga información sobre cómo conectarse a Adobe Experience Cloud y acceder a la interfaz web de Adobe Campaign [en esta página](campaign-ui.md#ac-web-ui).

Obtenga más información en la [documentación de la interfaz de usuario web de Adobe Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

### Acceso web {#web-access}

Se puede acceder a determinadas partes de la aplicación a través de un explorador web mediante una interfaz de usuario de HTML: creación de informes, aprobación de envíos, monitorización de instancias y mucho más.

El acceso web proporciona una interfaz similar a la consola , pero con un conjunto reducido de funcionalidades.

Por ejemplo, para un operador determinado, aparece una campaña con las siguientes opciones en la consola:

![](assets/campaign-from-console.png)

Mientras que con el acceso web, las opciones permiten principalmente la visualización de lo siguiente:

![](assets/campaign-from-web.png)

El acceso web también se utiliza en el proceso de validación: los operadores pueden hacer clic en el correo electrónico de solicitud de aprobación y conectarse a Campaign a través de su explorador web para validar o rechazar un contenido o presupuesto de entrega.

Para acceder a su instancia de Campaign desde la web, la URL es la siguiente: `https://<your adobe campaign server>:<port number>/view/home`.
