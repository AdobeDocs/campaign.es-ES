---
title: Arquitectura general
description: Obtenga más información acerca de la arquitectura y los componentes de Adobe Campaign. Obtenga más información acerca de cómo personalizar la consola de cliente y el entorno.
feature: Architecture, Deployment
role: Admin, Developer
level: Beginner
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '1136'
ht-degree: 7%

---

# Arquitectura general{#general-architecture}

La implementación típica de la solución de Adobe Campaign consta de los siguientes componentes:

* **Entorno de cliente personalizado**

  Interfaz gráfica intuitiva en la que los usuarios pueden comunicarse y rastrear ofertas de marketing, crear campañas, revisar y administrar todas las actividades, programas y planes de marketing, incluidos correos electrónicos, flujos de trabajo y páginas de aterrizaje, crear y administrar perfiles de clientes, y crear audiencias.

* **Entorno de desarrollo**

  Software del lado del servidor que ejecuta las campañas de marketing a través de canales de comunicación seleccionados, incluidos correos electrónicos, SMS, notificaciones push, correo directo, web o social, en función de las reglas y flujos de trabajo definidos en la interfaz de usuario.

* **Contenedores de base de datos**

  Basada en la tecnología de bases de datos relacionales, la base de datos en la nube de Adobe Campaign almacena toda la información, los componentes de campaña, las ofertas, los flujos de trabajo y los resultados de campaña en contenedores de base de datos.

## Entorno de cliente personalizado {#client-env}

Se puede acceder a la aplicación de diferentes maneras: interfaz de usuario web, consola de cliente (cliente enriquecido), acceso web (cliente ligero) o integración de API.

[Más información sobre la interfaz de usuario de Campaign](../start/campaign-ui.md).

## Entorno de desarrollo {#dev-env}

Adobe Campaign es una plataforma única con diferentes aplicaciones para crear una arquitectura abierta y escalable. La plataforma Adobe Campaign está escrita en una capa de aplicación flexible y se puede configurar fácilmente para satisfacer sus necesidades comerciales. La arquitectura distribuida garantiza la escalabilidad lineal del sistema, que puede abarcar desde miles de mensajes hasta millones de mensajes.

Algunos módulos de Campaign funcionan continuamente, mientras que otros se inician ocasionalmente para realizar tareas administrativas (por ejemplo, configurar la conexión a la base de datos) o para ejecutar una tarea recurrente (por ejemplo, consolidar la información de seguimiento).

Existen tres tipos de módulos de Adobe Campaign:

* **Módulos de varias instancias**: se ejecuta un solo proceso para todas las instancias. Esto se aplica a los siguientes módulos: web, syslogd, trackinglogd y watchdog.
* **Módulos de instancia mono**: se ejecuta un proceso por instancia. Esto se aplica a los siguientes módulos: mta, wfserver, inMail, sms y stat.
* **Módulos de utilidad**: estos módulos se ejecutan ocasionalmente para realizar operaciones ocasionales o recurrentes (limpieza, configuración, descarga de registros de seguimiento, etc.).

Los procesos principales son:

* **Servidor de aplicaciones** (web nlserver): este proceso expone toda la funcionalidad de Adobe Campaign SOAP a través de las API de servicios web (/ HTTP + XML). Además, puede generar dinámicamente las páginas web utilizadas para el acceso basado en HTML (informes, formularios web, etc.). Para conseguirlo, este proceso incluye un servidor JSP Apache Tomcat. Este es el proceso al que se conecta la consola.

* **Motor de flujo de trabajo** (nlserver wfserver): este proceso ejecuta los procesos de flujo de trabajo definidos en la aplicación. También gestiona flujos de trabajo técnicos ejecutados periódicamente, incluidos:

   * **Seguimiento**: recupera y consolida los registros de seguimiento para que pueda recuperar los registros del servidor de redirección y crear los indicadores agregados que usa el módulo de informes.
   * **Limpieza**: limpia la base de datos, purga los registros antiguos y evita que la base de datos crezca exponencialmente.
   * **Facturación**: envía un informe de actividad para la plataforma (tamaño de la base de datos, número de acciones de marketing, etc.).

* **Servidor de entrega** (mta de nlserver): Adobe Campaign tiene la funcionalidad de difusión de correo electrónico nativa. Este proceso funciona como un agente de transferencia de correo SMTP (MTA). Realiza una personalización &quot;uno a uno&quot; de los mensajes y gestiona su envío físico. Se ejecuta mediante trabajos de envío y gestiona reintentos automáticos. Además, cuando el seguimiento está habilitado, reemplaza automáticamente las direcciones URL para que apunten al servidor de redirección. Este proceso puede gestionar la personalización y el envío automático a un enrutador de terceros para SMS, fax y correo postal.

* **Servidor de redirección** (nlserver webmdl): por correo electrónico, Adobe Campaign administra automáticamente el seguimiento de aperturas y clics (el seguimiento transaccional en el nivel de sitio web es otra posibilidad). Para conseguirlo, las URL incorporadas en los mensajes de correo electrónico se reescriben para que apunten a este módulo, que registra el paso del usuario de Internet antes de redirigirlo a la URL requerida.

  SOAP Para garantizar la máxima disponibilidad, este proceso es totalmente independiente de la base de datos: los demás procesos del servidor se comunican con él utilizando llamadas de la red (HTTP, HTTP(S) y XML) únicamente. Técnicamente, esta funcionalidad se implementa en un módulo de extensión de un servidor HTTP (extensión ISAPI en IIS, o módulo DSO Apache, etc.) y solo está disponible en Windows.

Otros procesos más técnicos también están disponibles:

* **Administración de correos electrónicos rechazados** (nlserver inMail): este proceso le permite recoger automáticamente correos electrónicos de buzones configurados para recibir mensajes rechazados que se devuelven en caso de error de entrega. A continuación, estos mensajes se someten a un procesamiento basado en reglas para determinar los motivos de la falta de entrega (destinatario desconocido, cuota excedida, etc.) y para actualizar el estado de envío en la base de datos. Todas estas operaciones son totalmente automáticas y están preconfiguradas.

* **Estado de entrega de SMS** (nlserver sms): este proceso sondea el enrutador SMS para recopilar el estado de progreso y actualizar la base de datos.

* **Escritura de mensajes de registro** (nlserver syslogd): este proceso técnico captura los mensajes de registro y los seguimientos generados por los demás procesos y los escribe en el disco duro. Esto hace que haya amplia información disponible para el diagnóstico en caso de problemas.

* **Escritura de registros de seguimiento** (nlserver trackinglogd): este proceso guarda en el disco los registros de seguimiento generados por el proceso de redirección.

* **Escritura de eventos entrantes** (nlserver interactiond): este proceso garantiza la grabación en el disco de eventos entrantes, dentro del marco de Interacción.

* **Módulos de supervisión** (nlserver watchdog): este proceso técnico actúa como un proceso principal que genera a los demás. También los monitoriza y los relanza automáticamente en caso de incidentes, manteniendo así el máximo tiempo de actividad del sistema.

* **Servidor de estadísticas** (nlserver stat): este proceso mantiene estadísticas sobre el número de conexiones, los mensajes enviados para cada servidor de correo al que se envían los mensajes, así como sus limitaciones (número máximo de conexiones simultáneas, mensajes por hora/hora o conexión). También permite federar varias instancias o equipos si comparten las mismas direcciones IP públicas.


## Contenedores de base de datos {#db-containers}

En su [implementación empresarial (FDAC)](enterprise-deployment.md), la base de datos de Adobe Campaign Cloud se basa en [!DNL Snowflake], que contiene los datos funcionales (perfiles, suscripciones, contenido, etc.), los datos técnicos (trabajos de envío y registros, registros de seguimiento, etc.) y los datos de trabajo (compras, posibles clientes) de la solución, y todos los componentes de Adobe Campaign se comunican con la base de datos para realizar sus tareas específicas.

Puede implementar Adobe Campaign utilizando la base de datos y los esquemas predefinidos y, si es necesario, se puede ampliar este entorno predefinido. Adobe Campaign accede a todos los datos del data mart a través de llamadas SQL. Adobe Campaign también proporciona un complemento completo de herramientas de extracción, transformación y carga (ETL) para importar y exportar datos dentro y fuera del sistema.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Con **Campaign Managed Cloud Services**, su entorno y la configuración inicial se han configurado con Adobe, según los términos del acuerdo de licencia. No se le permite modificar paquetes integrados, esquemas integrados o informes instalados.
>
>Si necesita utilizar un complemento de Campaign o una funcionalidad específica que no se haya aprovisionado por usted, debe ponerse en contacto con el **Servicio de atención al cliente de Adobe**.

## Almacenamiento de base de datos {#db-storage}

La asignación de almacenamiento total se divide entre la base de datos principal y la base de datos secundaria del Snowflake (opcional). El lugar donde se almacenan los datos debe determinarse en el momento de la implementación o la actualización, según los casos de uso específicos del cliente.

Aprenda a monitorizar el uso de la base de datos en [Documentación del Panel de control de Campaign de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring.html){target="_blank"}.