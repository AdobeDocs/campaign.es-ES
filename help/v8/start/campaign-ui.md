---
title: Descubra el espacio de trabajo de Campaign
description: Descubra cómo examinar y utilizar el espacio de trabajo de Campaign
feature: Overview
role: Admin, Developer, User
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 32%

---

# Descubra la interfaz de usuario de Campaign

## Acceso a la interfaz de usuario de Campaign

El espacio de trabajo de Campaign está disponible a través de la [consola del cliente](../architecture/general-architecture.md).

Obtenga información sobre cómo instalar y configurar la consola del cliente de Campaign en [esta sección](../start/connect.md).

![](assets/home-page.png)

También puede utilizar un explorador web para acceder a Campaign. En este contexto, solo está disponible un subconjunto de funciones de Campaign. [Más información](#web-browser)

## Examinar la interfaz de usuario

Una vez que esté conectado a Campaign, acceda a la página principal. Examine los vínculos para acceder a las funciones. El conjunto de funciones disponibles en la interfaz de usuario depende de las opciones y los permisos.

Desde la sección central de la página principal, utilice vínculos para acceder a los materiales de ayuda de Campaign, la comunidad y el sitio web de asistencia.

Utilice las pestañas de la sección superior para examinar las funciones de las claves de Campaign:

![](assets/overview-home.png)

>[!NOTE]
>
>La lista de funcionalidades principales a las que puede acceder depende de sus permisos y de su implementación.

Para cada capacidad, puede acceder al conjunto de funciones clave en la **[!UICONTROL Browsing]** para obtener más información. La variable **[!UICONTROL More]** link permite acceder a todos los demás componentes.

Por ejemplo, al navegar hasta el **[!UICONTROL Profiles and targets]** , puede acceder a las listas de destinatarios, los servicios de suscripción, los flujos de trabajo de objetivos existentes y los accesos directos para crear todos estos componentes.

![](assets/overview-list.png)

Cuando selecciona un elemento en la pantalla, se carga en una nueva pestaña para que pueda examinar el contenido fácilmente.

![](assets/new-tab.png)

## Creación de un elemento {#create-an-element}

Utilizar los accesos directos en la variable **[!UICONTROL Create]** a la izquierda de la pantalla para añadir nuevos elementos. También puede usar la variable **[!UICONTROL Create]** situado encima de la lista para añadir nuevos elementos a la lista actual.

Por ejemplo, en la página de entrega, utilice el botón **[!UICONTROL Create]** para crear una nueva entrega.

![](assets/new-recipient.png)

## Usar un explorador web {#web-browser}

También puede acceder a un subconjunto de funciones de Campaign a través de un explorador web.

La interfaz de acceso web es similar a la interfaz de la consola. Desde un explorador, puede utilizar las mismas funciones de navegación y visualización que en la consola, pero solo puede realizar un conjunto reducido de acciones en las campañas. Por ejemplo, puede ver y cancelar campañas, pero no puede modificarlas.

![](../assets/do-not-localize/glass.png) [Obtenga más información sobre el acceso a la web de Campaign](../start/connect.md#web-access).

## Acceso al explorador de Campaign {#ac-explorer-ui}

Vaya al explorador de Campaign para acceder a todas las funcionalidades y configuraciones de Adobe Campaign.

![](assets/explorer.png)

Este espacio de trabajo le permite acceder al árbol del Explorador para examinar todas las funciones y opciones.

La sección izquierda muestra el árbol del explorador de Campaign y le permite examinar todos los componentes y la configuración de su instancia en función de sus permisos.

La sección superior muestra la lista de registros de la carpeta actual. Estas listas son totalmente personalizables. [Más información](customize-ui.md)

La sección inferior muestra los detalles del registro seleccionado.


## Idiomas

La interfaz de usuario de Campaign v8 está disponible en los siguientes idiomas:

* Inglés (RU)
* Inglés (EE. UU.)
* Francés
* Alemán
* Japonés

El idioma se selecciona durante el proceso de instalación.

>[!CAUTION]
>
>No se puede cambiar el idioma después de la creación de la instancia.

El idioma afecta a los formatos de fecha y hora.


Las principales diferencias entre el inglés de EE. UU. y el inglés de Reino Unido son:

<table> 
 <thead> 
  <tr> 
   <th> Formato<br /> </th> 
   <th> Inglés (EE. UU.)<br /> </th> 
   <th> Inglés (EN)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Fecha<br /> </td> 
   <td> La semana empieza el domingo<br /> </td> 
   <td> La semana empieza el lunes<br /> </td> 
  </tr> 
  <tr> 
   <td> Fecha corta<br /> </td> 
   <td> <p>%2M%2D/%4Y</p><p><strong>ex: 25/09/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>ex: 25/09/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> Fecha corta con hora<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>ex: 09/25/2018 10:47:25 PM</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>ex: 25/09/2018 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
