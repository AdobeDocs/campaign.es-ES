---
title: Conexión a Campaign v8
description: Aprenda a conectarse a Adobe Campaign versión 8 y a instalar la consola en su equipo para disfrutar de un acceso más sencillo.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 11%

---

# Conectar con Adobe Campaign v8{#gs-ac-connect}

Para comenzar a trabajar con Campaign, debe instalar y configurar la consola del cliente.

La consola del cliente es una aplicación nativa que se comunica con el servidor de aplicaciones de Adobe Campaign a través de protocolos de Internet estándar, como SOAP y HTTP. La consola del cliente de Campaign centraliza todas las funcionalidades y configuraciones y requiere un ancho de banda mínimo, ya que depende de una caché local. Diseñada para facilitar la implementación, la consola del cliente de Campaign se puede implementar desde un explorador de Internet, actualizarse automáticamente y no requiere ninguna configuración de red específica, ya que solo genera tráfico HTTP(S).

Antes de empezar, debe hacer lo siguiente:

* Compruebe la compatibilidad del sistema y las herramientas con Adobe Campaign en la [Matriz de compatibilidad](compatibility-matrix.md)
* Obtener la URL del servidor de Campaign
* Cree su Adobe ID o consiga sus credenciales de usuario en su empresa
* Instale el tiempo de ejecución de Microsoft Edge Webview2 en su sistema. [Más información](#webview)

## Instalación de la consola de cliente{#download-ac-console}

### Tiempo de ejecución de Microsoft Edge Webview2 {#webview}

A partir de la versión de compilación de Campaign Classic 8.4, se requiere la instalación del tiempo de ejecución de Microsoft Edge Webview 2 para cualquier instalación de la consola del cliente.

Web View se instala de forma predeterminada como parte del sistema operativo Windows 11. Si aún no está presente en el sistema, el programa de instalación de la consola del cliente de Campaign le pedirá que lo descargue desde [Sitio web para desarrolladores de Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_es){target="_blank"}. Tenga en cuenta que el vínculo de descarga no funciona en el explorador Internet Explorer 11, ya que Microsoft ha dejado de admitir. Asegúrese de utilizar un explorador diferente para acceder al vínculo.

### Descargar la consola{#install-ac-console}

Cuando utilice Campaign por primera vez, debe descargar la consola del cliente e instalarla.

Hay dos opciones disponibles para descargar la consola del cliente:

1. Como administrador de Campaign, conéctese al Adobe [Distribución de software](https://experience.adobe.com/#/downloads/content/software-distribution/es/campaign.html){target="_blank"}.

1. Como usuario final, el administrador de Campaign implementa Client Console por usted y la pone a disposición a través de una dirección URL dedicada.

Una vez descargado el programa de instalación de Client Console, instálelo en el equipo local.

Tenga en cuenta que no puede cambiar el idioma de la consola del cliente una vez que está instalada.

## Cree su conexión{#create-your-connection}

Una vez instalada la consola del cliente, siga los pasos a continuación para crear la conexión con el servidor de aplicaciones:

1. Inicie la consola y examine el vínculo en la esquina derecha para acceder a la pantalla de configuración de la conexión.

1. Clic **[!UICONTROL Add > Connection]** e introduzca la etiqueta y la dirección URL del servidor de aplicaciones de Adobe Campaign.

1. Especifique una conexión con el servidor de aplicaciones de Adobe Campaign mediante una dirección URL. Utilice un DNS o un alias del equipo, o su dirección IP.

   Por ejemplo, puede utilizar la variable [`https://<machine>.<domain>.com`](https://myserver.adobe.com) escriba la dirección URL.

1. Marque la opción **[!UICONTROL Connect with an Adobe ID]**.

1. Clic **[!UICONTROL Ok]** para guardar la configuración.

Puede añadir tantas conexiones como sea necesario para conectarse a los entornos de prueba, fase y producción, por ejemplo.

>[!NOTE]
>
>El botón **[!UICONTROL Add]** permite crear **[!UICONTROL folders]** para organizar todas las conexiones. Basta con arrastrar y colocar cada conexión en una carpeta.

## Iniciar sesión en Adobe Campaign {#logon-to-ac}

Los usuarios de Campaign se conectan a la consola de Adobe Campaign con su Adobe ID a través del Sistema Identity Management de Adobe (IMS). Pueden utilizar el mismo ID para todas las soluciones de Adobe. La conexión se guarda al utilizar Adobe Campaign con otras soluciones. Obtenga más información acerca de Adobe IMS en [esta página](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"}.

Para iniciar sesión en una instancia, siga los pasos a continuación:

1. Inicie la consola y examine el vínculo en la esquina derecha para acceder a la pantalla de configuración de la conexión.

   ![](assets/connectToCampaign.png)

1. Seleccione la instancia de Campaign en la que debe iniciar sesión.

1. Haga clic en **[!UICONTROL Ok]**.

A continuación, puede iniciar sesión en Campaign con su Adobe ID.

![](assets/adobeID.png)

>[!NOTE]
>
>Como Microsoft Edge Webview2 no guarda las credenciales de proxy, la consola puede solicitarle que se autentique dos veces la primera vez que se conecte.

## Actualización de la consola de cliente{#upgrade-ac-console}

Cuando el sistema se actualice a una versión más reciente, deberá actualizar la consola de cliente a esa misma versión. Esta es una práctica recomendada y, para algunas versiones, esta actualización es obligatoria. En ese caso, se menciona en el [Notas de versión](release-notes.md).

Como usuario de Cloud Services administrados, Adobe implementa la consola de cliente por usted. Cuando se conecte al entorno actualizado, se le pedirá que descargue la versión más reciente de la consola del cliente en una ventana emergente. Debe aceptar esta actualización y actualizar la consola de cliente según se le solicite.

>[!CAUTION]
>
>El Adobe recomienda dejar la opción **[!UICONTROL No longer ask this question]** no seleccionada para asegurarse de que se le avisa cuando hay una nueva versión de la consola disponible. Si se selecciona esta opción, no se informa al usuario de que se requiere una actualización de la consola.


## Concesión de acceso a los usuarios{#grant-access}

Adobe Campaign le permite definir y administrar los derechos asignados a los distintos operadores.

Como administrador de Campaign, es responsable de crear los operadores y compartir sus credenciales con los usuarios.

Obtenga más información sobre los usuarios y cómo definir sus permisos en [esta sección](gs-permissions.md).


## Acceso web{#web-access}

Se puede acceder a ciertas partes de la aplicación a través de un explorador web mediante una interfaz de usuario de HTML: creación de informes, aprobación de envíos, monitorización de instancias, etc.

El acceso web proporciona una interfaz similar a la consola pero con un conjunto reducido de funcionalidades.

Por ejemplo, para un operador determinado, una campaña se mostrará con las siguientes opciones en la consola:

![](assets/campaign-from-console.png)

Mientras que con el acceso web, las opciones permiten principalmente la visualización de:

![](assets/campaign-from-web.png)

El acceso web también se utiliza en el proceso de validación: los operadores pueden hacer clic en el correo electrónico de solicitud de aprobación y conectarse a Campaign a través de su explorador web para validar o rechazar un contenido o presupuesto de entrega.

Para acceder a la instancia de Campaign desde la web, la URL es:  `https://<your adobe campaign server>:<port number>/view/home`.
