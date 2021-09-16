---
title: Conexión a Campaign v8
description: Obtenga información sobre cómo conectarse a Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 14%

---

# Conexión a Adobe Campaign v8{#gs-ac-connect}

La consola del cliente de Campaign es un cliente enriquecido que le permite conectarse a sus servidores de aplicaciones de Campaign.

Antes de empezar, debe:

* Compruebe la compatibilidad del sistema y las herramientas con Adobe Campaign en la [Matriz de compatibilidad](compatibility-matrix.md)
* Obtener la URL del servidor de Campaign
* Cree su Adobe ID u obtenga sus credenciales de usuario de su empresa

## Descargar e instalar la consola de cliente

Al utilizar Campaign por primera vez, o si necesita actualizar a una versión más reciente, debe descargar la consola de cliente e instalarla.

Hay dos opciones disponibles:

1. Como administrador de Campaign, conéctese al Adobe [Distribución de software](https://experience.adobe.com/#/downloads/content/software-distribution/es/campaign.html) y descargue el programa de instalación de la Consola de cliente. A continuación, puede instalarlo en el equipo local.

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

1. Marque la opción **[!UICONTROL Connect with an Adobe ID]**.

1. Haga clic en **[!UICONTROL Ok]** para guardar la configuración.

Puede agregar tantas conexiones como sea necesario para conectarse a los entornos de prueba, fase y producción, por ejemplo.

>[!NOTE]
>
>El botón **[!UICONTROL Add]** permite crear **[!UICONTROL folders]** para organizar todas las conexiones. Basta con arrastrar y colocar cada conexión en una carpeta.

## Iniciar sesión en Adobe Campaign

Para iniciar sesión en una instancia existente, siga los pasos a continuación:

1. Inicie la Consola desde el menú Windows **[!UICONTROL Start]**, en el grupo de programas **Adobe Campaign**.

1. Haga clic en el vínculo en la esquina superior derecha de los campos de credenciales para acceder a la ventana de configuración de conexión.

   ![](assets/connectToCampaign.png)

1. Seleccione la instancia de Campaign a la que debe iniciar sesión.

1. Haga clic en **[!UICONTROL Ok]**.

1. A continuación, puede iniciar sesión en Campaign con [su Adobe ID](#connect-ims).

   ![](assets/adobeID.png)

## Conceder acceso a los usuarios

Adobe Campaign le permite definir y administrar los derechos asignados a los distintos operadores. Se trata de un conjunto de derechos y restricciones que autorizan o niegan:

* Acceso a determinadas funciones (a través de los derechos asignados),
* Acceso a ciertos elementos,
* Cree, modifique o elimine elementos (envío, contactos, campañas, grupos, etc.).

Obtenga más información sobre los usuarios y cómo definir sus permisos en [esta sección](permissions.md).

Como administrador de Campaign, usted es el responsable de crear los operadores y compartir sus credenciales con los usuarios.

## Conectarse a Campaign con su Adobe ID{#connect-ims}

Los usuarios de Campaign se conectan a la consola de Adobe Campaign mediante su Adobe ID, a través del sistema Identity Management de Adobe (IMS). Pueden usar el mismo ID en todas las soluciones de Adobe. La conexión se guarda al usar Adobe Campaign con otras soluciones.

Obtenga más información sobre IMS de Adobe en [esta página](https://helpx.adobe.com/es/enterprise/using/identity.html).

## Acceso web{#web-access}

Se puede acceder a ciertas partes de la aplicación a través de un explorador web mediante una interfaz de usuario HTML: informes, aprobación de envíos, supervisión de instancias, etc.

El acceso web proporciona una interfaz similar a la consola pero con un conjunto reducido de funcionalidades.

Por ejemplo, para un operador determinado, una campaña se mostrará con las siguientes opciones en la consola:

![](assets/campaign-from-console.png)

Mientras que con el acceso web, las opciones permiten principalmente la visualización de:

![](assets/campaign-from-web.png)

El acceso web también se utiliza en el proceso de validación: Los operadores pueden hacer clic en el correo electrónico de solicitud de aprobación y conectarse a Campaign a través de su explorador web para validar o rechazar un contenido o presupuesto de envío.

Para acceder a la instancia de Campaign desde la web, la dirección URL es:  `https://<your adobe campaign server>:<port number>/view/home`.
