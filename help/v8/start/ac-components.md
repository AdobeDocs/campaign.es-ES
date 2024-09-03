---
title: Comprender los componentes y procesos de Campaign
description: Comprender los componentes y procesos de Campaign
feature: Overview, Architecture, Configuration
role: User
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 6926d84576df1810b511ef1a9976593cb99585bb
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%

---

# Comprender los componentes y procesos de Campaign {#components-and-processes}

Adobe Campaign es una solución de marketing entre canales que automatiza las campañas por correo electrónico, móviles, sociales y sin conexión. Adobe Campaign proporciona un lugar central para acceder a los datos y perfiles de los clientes. Utilice Adobe Campaign para orquestar experiencias coherentes para sus clientes, diseñar, ejecutar y personalizar su marketing a través de canales, a la vez que mejora las experiencias de los clientes en cada dispositivo y punto de contacto. Con Adobe Campaign, puede administrar varias fuentes de datos, definir los segmentos de audiencia y planificar y ejecutar campañas en canales múltiples de varios pasos a través de una interfaz de flujo de trabajo visual de arrastrar y soltar.

Obtenga más información acerca de las funcionalidades de clave de Campaign en [esta página](../start/get-started.md).

## Componentes de Campaign {#ac-components}

A continuación se describen los componentes de Adobe Campaign y la arquitectura global.

![](assets/do-not-localize//ac-components.png)



### Capa de persistencia{#persistance-layer}

Las bases de datos de Campaign se utilizan como capas de persistencia y contienen casi toda la información y los datos que administra Adobe Campaign. Esto incluye datos funcionales, como perfiles, suscripciones, contenido; datos técnicos, como trabajos y registros de envío, registros de seguimiento y datos de trabajo (compras, posibles clientes).

La fiabilidad de la base de datos es de suma importancia porque la mayoría de los componentes de Adobe Campaign requieren acceso a la base de datos para realizar sus tareas (excepto el módulo de redirección).

### Capa de aplicación lógica{#logical-app-layer}

La capa de aplicación lógica de Campaign se puede configurar fácilmente para satisfacer necesidades comerciales complejas. Puede utilizar Campaign como plataforma única con diferentes aplicaciones que se combinan para crear una arquitectura abierta y escalable. Cada instancia de Campaign es una colección de procesos en la capa de aplicación, algunos de los cuales se comparten y otros están dedicados.

## Cloud Service administrados de Campaign{#ac-managed-services}

La versión 8 de Adobe Campaign se implementa as a Managed Service: todos los componentes de Adobe Campaign, incluida la interfaz de usuario, el motor de administración de la ejecución y las bases de datos de Campaign, están totalmente alojados por el Adobe, incluida la ejecución de correo electrónico, las páginas espejo, el servidor de seguimiento y los componentes web externos, como la cancelación de la suscripción de la página/centro de preferencias y páginas de aterrizaje.

## Procesos de Campaign

El servidor web de Campaign controla el acceso a los procesos web de Campaign. Javascript es el lenguaje del lado del servidor que se utiliza para las funciones y personalizaciones principales del producto. Tomcat es el motor back-end y está integrado en el producto Campaign como parte del proceso web. Javascript se utiliza, por ejemplo, en páginas JSP o JSSP para procesar contenido dinámico.

![](assets/do-not-localize/ac-processes.png)

SOAP La consola del cliente de Campaign se conecta al servidor web mediante XML de la aplicación a través de HTTP. El servidor web proporciona la capa de seguridad, pasa las solicitudes a la capa de aplicación mediante JavaScript y los procesos internos de Campaign acceden a la base de datos mediante SQL.

<!--The overall communication between Campaign processes are described in the following standalone deployment diagram: all Campaign components are installed in the same machine.

![](assets/do-not-localize//ac-standalone.png) -->

El usuario se conecta al servidor de aplicaciones de Campaign mediante el protocolo HTTP. Todos los datos y la información se administran en la base de datos de Campaign. Si un desarrollador de Campaign realiza cualquier cambio en la configuración, se captura en la base de datos. Si un especialista en marketing crea una nueva campaña, toda la información y los datos relacionados con esta nueva campaña también se administran en la base de datos. Cuando un experto en marketing ejecuta una campaña, las entregas de correo electrónico se envían a los perfiles desde el servidor de Campaign a través del servidor SMTP. A medida que los perfiles interactúan con las entregas de correo electrónico, como la apertura del correo electrónico, esos datos de seguimiento se devuelven al servidor de seguimiento.

[Más información sobre los procesos de Campaign](../architecture/general-architecture.md#dev-env).
