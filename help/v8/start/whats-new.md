---
title: Novedades de la versión 8 de Campaign
description: Descubra las funcionalidades clave de la versión 8 de Adobe Campaign, sus novedades y lo que puede esperar de la última versión.
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: f16fe79b8417a3fa146baf432f829c73fb839953
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 94%

---

# ¿Qué novedades hay en la versión 8 de Adobe Campaign?  {#ac-gs-what-is-new}

La versión 8 de Adobe Campaign está diseñada para especialistas en marketing en canales múltiples que necesitan la mejor solución de nube para la administración de campañas en canales múltiples a escala empresarial. Proporciona sólidas capacidades de ETL y administración de datos para ayudar a diseñar y depurar la campaña perfecta. Su motor de orquestación proporciona programas de marketing multitáctil enriquecidos con un enfoque central en los recorridos impulsados por lotes. También viene acompañado de un servidor de mensajería en tiempo real escalable que permite a los equipos de marketing enviar mensajes predefinidos basados en una carga útil inclusiva desde cualquier sistema de TI para tareas como restablecimiento de contraseñas, confirmación de pedidos, recibos electrónicos y mucho más.

La versión 8 de Adobe Campaign ofrece mejoras significativas en infraestructura, seguridad, capacidad de envío y supervisión.

![](assets/home-page.png)

## Funcionalidades clave{#key-capabilities}

A continuación se enumeran las funcionalidades clave.

### Administración central del flujo de trabajo{#central-wf-mgt}

Mejora de la velocidad y la escala de cada aspecto de sus campañas de marketing, desde la creación de segmentos y la preparación de mensajes hasta la entrega.

Adobe Campaign le permite sincronizar sus canales fácilmente con una interfaz única y fácil de usar para la orquestación de campañas. Así que sus canales en línea, como correo electrónico, web, móvil y social, coinciden con sus canales sin conexión, incluidos el correo directo, el centro de llamadas, las tiendas, etc. Le permite ofrecer a sus clientes una experiencia coherente y contextual tanto en los canales digitales como en los tradicionales. Adobe Campaign facilita la entrega de contenido a todas las rutas que puedan seguir sus clientes en cualquier canal.

![](../assets/do-not-localize/glass.png)[Obtenga más información acerca de los flujos de trabajo de Campaign](../config/workflows.md)

### Marketing por correo electrónico personalizado {#perso-email-mkt}

Cree correos electrónicos personalizados y relevantes para el contexto que sean coherentes con el resto de la experiencia del cliente.

Con Adobe Campaign, puede mejorar sus correos electrónicos, personalizarlos y hacerlos más rentables. Los correos electrónicos son fáciles de crear y de enviar. La versión 8 de Campaign le ofrece la flexibilidad de diseñar, personalizar, probar, perfeccionar y mejorar cada mensaje que envía.

![](../assets/do-not-localize/glass.png) [Obtenga más información acerca las funcionalidades de personalización](create-message.md)

### Administración de datos de clientes {#customer-data-mgt}

Vea toda la imagen de sus clientes para crear rápidamente campañas personalizadas a escala empresarial.

Adobe Campaign le ayuda a generar perfiles de clientes a partir de datos recopilados en todos sus canales. Con este perfil, puede orquestar campañas en varios canales. Al conectar todos los canales de marketing, puede personalizar los diferentes recorridos que cada cliente adoptará de la manera que les resulte más apropiada.

![](../assets/do-not-localize/glass.png) [Obtenga más información acerca la administración de datos de clientes](audiences.md)

### Administración de campañas de la mejor clase {#best-in-campaign-mgt}

La versión 8 de Adobe Campaign proporciona a los especialistas en marketing las mejores funciones de su clase para planificar, iniciar y medir campañas en todos los canales.

Las funciones incluyen un perfil integrado que proporciona una sola vista del cliente. Administración y segmentación de datos para la creación de audiencias de campaña a escala. Administración de flujos de trabajo multicanal para automatizar campañas de varios canales y de varias ondas. Correo electrónico integrado, reduce la dependencia de los costosos ESP. Creación de informes y análisis para comprender el comportamiento de los clientes y el rendimiento de las campañas.

![](../assets/do-not-localize/glass.png)[Obtenga más información acerca de la administración de Campaign](campaigns.md)


### Conexiones a Adobe Experience Platform {#connection-to-aep}

La versión 8 de Adobe Campaign admite conectores de datos con Real-Time CDP y Adobe Experience Platform, de modo que las organizaciones puedan aprovechar el perfil unificado del cliente en tiempo real.

Además, la versión 8 de Adobe Campaign está integrada de forma nativa con las funciones de orquestación de recorrido en tiempo real, de modo que los especialistas en marketing pueden reutilizar las mismas plantillas y capacidades de entrega en Adobe Campaign para interactuar con los clientes en tiempo real. Estas inversiones optimizarán la experiencia del cliente de Adobe Campaign y desbloquearán nuevos casos de uso, como la capacidad de añadir recorridos personalizados del cliente en tiempo real a las campañas.

También puede configurar la optimización del tiempo de envío predictivo y la puntuación de participación predictiva con la inteligencia artificial aplicada a la trayectoria, y aumentar las tasas de apertura, los clics y los ingresos.

![](../assets/do-not-localize/glass.png) [Obtenga más información sobre las integraciones de Campaign](../connect/integration.md)


### Managed Cloud Services {#acms-desc}

La versión 8 de Adobe Campaign está disponible as a Managed Cloud Service, y proporciona supervisión proactiva, alertas oportunas y administración de servicios.

Adobe Managed Cloud Service proporciona a los especialistas en marketing una solución de administración de campañas en canales múltiples más ágil, segura y escalable con un bajo coste total de propiedad. La nueva oferta combina servicios con supervisión proactiva y alertas oportunas.

>[!NOTE]
>
>La nueva arquitectura de la nube permite a Campaign optimizar los procesos, reducir los costes, administrar los riesgos y mejorar la seguridad de los datos. El entorno de Campaign v8 viene con una nube privada virtual (VPC) dedicada preconfigurada para usted.

### Velocidad y escala {#speed-scale}

Adobe Campaign ahora puede aprovechar las tecnologías de bases de datos a escala de nube para mejorar considerablemente su escala y velocidad.

[La versión 8 de Campaign Enterprise](../architecture/enterprise-deployment.md) incorpora el concepto de **Acceso de datos federado completo** (FDAC): todos los datos ahora son remotos en la base de datos de Cloud. Con esta nueva oferta, la versión 8 de Campaign simplifica la administración de datos: no se requiere ningún índice en la base de datos en la nube. Basta con crear las tablas, copiar los datos y empezar. [!DNL Snowflake] es la base de datos de Campaign Cloud que le proporcionará velocidad y solidez: no hay sobrecarga de los picos de actividad del sistema. La tecnología de la base de datos en la nube no requiere ningún mantenimiento específico para garantizar el nivel de rendimiento.

![](../assets/do-not-localize/glass.png) [Obtenga más información acerca la implementación de Enterprise (FDAC)](../architecture/enterprise-deployment.md)

>[!CAUTION]
>
>* La versión 8 de Campaign **solo** está disponible as a Managed Cloud Service y no se puede implementar en entornos locales o híbridos.
>
>* La migración automatizada desde el entorno de la versión 7 de Campaign Classic existente aún no está disponible.


## Interfaz de administración de autoservicio{#self-service-admin}

Como administrador de productos, puede administrar la configuración y rastrear los usos de cada una de las instancias de Campaign versión 8 con el **Panel de control de Campaign**.

A través de una interfaz de usuario intuitiva, los administradores pueden monitorizar el uso de los recursos clave, realizar tareas avanzadas como incluir direcciones IP en la lista de permitidos, supervisar el almacenamiento SFTP, administrar claves, etc. Esta interfaz de autoservicio le ofrece más flexibilidad y le ayuda a lo siguiente:

* Cambiar la configuración rápidamente por su cuenta, sin ponerse en contacto con el Soporte de Adobe
* Configure las opciones en función de las diferentes necesidades comerciales en distintos momentos
* Mejore la seguridad controlando la configuración de acceso según sus necesidades

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [Más información sobre el Panel de control de Campaign de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=es){target="_blank"}


