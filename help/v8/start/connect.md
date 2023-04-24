---
title: Conexión a Campaign v8
description: Aprenda a conectarse a Adobe Campaign versión 8 y a instalar la consola en su equipo para disfrutar de un acceso más sencillo.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 7f27dbdd0ff53cd7437f956ccfef3d792020893b
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 11%

---

# Conexión a Adobe Campaign v8{#gs-ac-connect}

Para comenzar a trabajar con Campaign, debe instalar y configurar la consola de cliente.

La consola de cliente es una aplicación nativa que se comunica con el servidor de aplicaciones de Adobe Campaign a través de protocolos de Internet estándar, como SOAP y HTTP. La consola del cliente de Campaign centraliza todas las capacidades y configuraciones, y requiere un ancho de banda mínimo, ya que depende de una caché local. Diseñada para una implementación sencilla, la consola del cliente de Campaign se puede implementar desde un explorador de Internet, se puede actualizar automáticamente y no requiere ninguna configuración de red específica, ya que solo genera tráfico HTTP(S).

Antes de empezar, debe:

* Compruebe la compatibilidad del sistema y las herramientas con Adobe Campaign en la [Matriz de compatibilidad](compatibility-matrix.md)
* Obtener la URL del servidor de Campaign
* Cree su Adobe ID o obtenga sus credenciales de usuario de su empresa
* Instale el tiempo de ejecución de Microsoft Edge Webview2 en su sistema. [Más información](#webview)

## Instalación de la consola de cliente{#download-ac-console}

### Tiempo de ejecución de Microsoft Edge Webview2 {#webview}

A partir de la versión de Campaign Classic 8.4, se requiere la instalación del tiempo de ejecución de Microsoft Edge Webview 2 para cualquier instalación de Client Console.

La vista web se instala de forma predeterminada como parte del sistema operativo Windows 11. Si aún no está presente en el sistema, el programa de instalación de la consola del cliente de Campaign le pedirá que lo descargue de [Sitio web del desarrollador de Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_es){target="_blank"}. Tenga en cuenta que el vínculo de descarga no funciona en el explorador Internet Explorer 11, ya que Microsoft ha dejado de ofrecer soporte técnico. Asegúrese de utilizar un explorador diferente para acceder al vínculo.

### Descargar la consola{#install-ac-console}

Al utilizar Campaign por primera vez, debe descargar la consola de cliente e instalarla.

Hay dos opciones disponibles para descargar la consola de cliente:

1. Como administrador de Campaign, conéctese a Adobe [Distribución de software](https://experience.adobe.com/#/downloads/content/software-distribution/es/campaign.html){target="_blank"}.

1. Como usuario final, el administrador de Campaign implementa Client Console por usted y lo hace disponible a través de una dirección URL dedicada.

Una vez descargado el programa de instalación de Client Console, instálelo en el equipo local.

Tenga en cuenta que no puede cambiar el idioma de la consola de cliente una vez que esté instalado.

## Crear la conexión{#create-your-connection}

Una vez instalada la consola de cliente, siga los pasos a continuación para crear la conexión con el servidor de aplicaciones:

1. Inicie la consola y busque el vínculo en la esquina derecha para acceder a la pantalla de configuración de conexión.

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

Los usuarios de Campaign se conectan a la consola de Adobe Campaign mediante su Adobe ID, a través del sistema Identity Management de Adobe (IMS). Pueden usar el mismo ID en todas las soluciones de Adobe. La conexión se guarda al usar Adobe Campaign con otras soluciones. Obtenga más información sobre Adobe IMS en [esta página](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"}.

Para iniciar sesión en una instancia, siga los pasos a continuación:

1. Inicie la consola y busque el vínculo en la esquina derecha para acceder a la pantalla de configuración de conexión.

   ![](assets/connectToCampaign.png)

1. Seleccione la instancia de Campaign a la que debe iniciar sesión.

1. Haga clic en **[!UICONTROL Ok]**.

A continuación, puede iniciar sesión en Campaign con su Adobe ID.

![](assets/adobeID.png)

>[!NOTE]
>
>Como Microsoft Edge Webview2 no guarda las credenciales del proxy, la consola puede pedirle que se autentique dos veces en la primera conexión.

## Actualizar la consola del cliente{#upgrade-ac-console}

Cuando el sistema se actualiza a una versión más reciente, debe actualizar la consola de cliente a esa misma versión. Se trata de una práctica recomendada y, en algunas versiones, esta actualización es obligatoria. En ese caso, se menciona en el [Notas de la versión](release-notes.md).

Como usuario de Cloud Services administrados, Adobe implementa Client Console por usted. Cuando se conecte al entorno actualizado, se le pedirá que descargue la última versión de la consola de cliente en una ventana emergente. Debe aceptar esta actualización y actualizar la consola de cliente según se solicite.

>[!CAUTION]
>
>Adobe recomienda dejar la opción **[!UICONTROL No longer ask this question]** no seleccionado para asegurarse de que recibe un aviso cuando hay una nueva versión de la consola disponible. Si se selecciona esta opción, no se informa al usuario de que se requiere una actualización de la consola.


## Conceder acceso a los usuarios{#grant-access}

Adobe Campaign le permite definir y administrar los derechos asignados a los distintos operadores.

Como administrador de Campaign, usted es el responsable de crear los operadores y compartir sus credenciales con los usuarios.

Obtenga más información sobre los usuarios y cómo definir sus permisos en [esta sección](gs-permissions.md).


## Acceso web{#web-access}

Se puede acceder a ciertas partes de la aplicación a través de un explorador web mediante una interfaz de usuario de HTML: informes, aprobación de envíos, supervisión de instancias, etc.

El acceso web proporciona una interfaz similar a la consola pero con un conjunto reducido de funcionalidades.

Por ejemplo, para un operador determinado, una campaña se mostrará con las siguientes opciones en la consola:

![](assets/campaign-from-console.png)

Mientras que con el acceso web, las opciones permiten principalmente la visualización de:

![](assets/campaign-from-web.png)

El acceso web también se utiliza en el proceso de validación: Los operadores pueden hacer clic en el correo electrónico de solicitud de aprobación y conectarse a Campaign a través de su explorador web para validar o rechazar un contenido o presupuesto de envío.

Para acceder a la instancia de Campaign desde la web, la dirección URL es:  `https://<your adobe campaign server>:<port number>/view/home`.
