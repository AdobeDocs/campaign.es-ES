---
title: Descripción de los componentes y procesos de Campaign
description: Descripción de los componentes y procesos de Campaign
feature: Overview, Architecture, Configuration
role: User
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: e4f6c70ecdcf7414b5f49a43933cfd1c967a0905
workflow-type: ht
source-wordcount: '637'
ht-degree: 100%

---

# Descripción de los componentes y procesos de Campaign {#components-and-processes}

Adobe Campaign es una solución de marketing en canales múltiples que automatiza las campañas por correo electrónico, en móviles, redes sociales y sin conexión. Adobe Campaign ofrece un lugar central para acceder a los datos y perfiles de los clientes. Utilice Adobe Campaign para orquestar experiencias coherentes para sus clientes, diseñar, ejecutar y personalizar su marketing a través de canales, a la vez que mejora las experiencias de los clientes en cada dispositivo y punto de contacto. Con Adobe Campaign, puede administrar varias fuentes de datos, definir los segmentos de público y planificar y ejecutar campañas en canales múltiples y con varios pasos a través de una interfaz de flujo de trabajo visual de tipo arrastrar y soltar.

Obtenga más información sobre las funcionalidades clave de Campaign [en esta página](../start/get-started.md).

## Componentes de Campaign {#ac-components}

A continuación se describen los componentes y la arquitectura global de Adobe Campaign.

![](assets/do-not-localize//ac-components.png)

### Capa de presentación{#presentation-layer}

Puede acceder a Adobe Campaign a través de un cliente enriquecido, un cliente ligero o una integración de API.

* Cliente enriquecido

  El cliente enriquecido de Campaign es una aplicación nativa que se comunica con el servidor de aplicaciones de Adobe Campaign a través de protocolos de internet estándar, como SOAP y HTTP. [Obtenga más información sobre la consola del cliente de Campaign](../start/connect.md).

* Cliente ligero

  Las funciones de acceso web de Adobe Campaign le permiten acceder a un subconjunto de funciones de Campaign con un explorador web mediante una interfaz de usuario HTML. Utilice esta interfaz web para acceder a informes, controlar y validar mensajes, acceder a paneles de monitorización y mucho más.  [Obtenga más información sobre el acceso web de Campaign](../start/connect.md).

* Aplicaciones externas con API

  En determinados casos, se puede llamar al sistema desde aplicaciones externas utilizando las API de servicios web expuestas mediante el protocolo SOAP. [Obtenga más información sobre las API de Campaign](../dev/api.md).

### Capa de persistencia{#persistance-layer}

Las bases de datos de Campaign se utilizan como capas de persistencia y contienen casi toda la información y los datos que administra Adobe Campaign. Esto incluye datos funcionales, como perfiles, suscripciones, contenido; datos técnicos, como trabajos y registros de envío, registros de seguimiento, y datos de trabajo (compras, posibles clientes).

La fiabilidad de la base de datos es de suma importancia porque la mayoría de los componentes de Adobe Campaign requieren acceder a la base de datos para poder realizar sus tareas (excepto al módulo de redirección).

### Capa de aplicación lógica{#logical-app-layer}

La capa de aplicación lógica de Campaign se puede configurar fácilmente para satisfacer necesidades comerciales complejas. Puede utilizar Campaign como plataforma única con diferentes aplicaciones que se combinan para crear una arquitectura abierta y escalable. Cada instancia de Campaign es una colección de procesos en la capa de aplicación, algunos de los cuales se comparten y otros son exclusivos.

## Campaign Managed Cloud Services{#ac-managed-services}

La versión 8 de Adobe Campaign se implementa como “As a Managed Service”. Todos los componentes de Adobe Campaign, incluida la interfaz de usuario, el motor de administración de la ejecución y las bases de datos de Campaign, están totalmente alojadas en Adobe, incluida la ejecución de correo electrónico, las páginas espejo, el servidor de seguimiento y los componentes web externos, como la cancelación de suscripción de la página/centro de preferencias y las páginas de aterrizaje.

## Procesos de Campaign

El servidor web de Campaign controla el acceso a los procesos web de Campaign. JavaScript es el lenguaje del lado del servidor que se utiliza para las funciones y personalizaciones principales del producto. Tomcat es el motor back-end y está integrado en el producto Campaign como parte del proceso web. JavaScript se utiliza, por ejemplo, en páginas JSP o JSSP para procesar contenido dinámico.

![](assets/do-not-localize/ac-processes.png)

La consola del cliente de Campaign se conecta al servidor web mediante SOAP XML a través de HTTP. El servidor web proporciona la capa de seguridad, pasa las solicitudes a la capa de aplicación mediante JavaScript y los procesos internos de Campaign acceden a la base de datos mediante SQL.

<!--The overall communication between Campaign processes are described in the following standalone deployment diagram: all Campaign components are installed in the same machine.

![](assets/do-not-localize//ac-standalone.png) -->

El usuario se conecta al servidor de aplicaciones de Campaign mediante el protocolo HTTP. Todos los datos y la información se administran en la base de datos de Campaign. Si un desarrollador de Campaign realiza cualquier cambio en la configuración, se captura en la base de datos. Si un experto en marketing crea una nueva campaña, toda la información y los datos relacionados con esta nueva campaña también se administran en la base de datos. Cuando un experto en marketing ejecuta una campaña, los envíos de correo electrónico se realizan a los perfiles desde el servidor de Campaign a través del servidor SMTP. A medida que los perfiles interactúan con los envíos de correo electrónico, como, por ejemplo, abrir el correo electrónico, esos datos de seguimiento se envían de nuevo al servidor de seguimiento.

[Obtenga más información sobre los procesos de Campaign](../architecture/general-architecture.md#dev-env).
