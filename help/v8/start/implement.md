---
title: Directrices de implementación
description: Aprenda a implementar Campaign v8
feature: Overview
role: User
level: Intermediate
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 97%

---

# Directrices de implementación de Campaign{#gs-implementation}

En esta sección, aprenderá a ajustar Adobe Campaign a los requisitos de su compañía. Siga estas directrices para estructurar y organizar la implementación.

1. **Definir la configuración**: conceder acceso, compartir la consola del cliente, configurar canales (correo electrónico, push, sms). [Más información](#implementation-ac-settings)
1. **Prepare su entorno**: importar perfiles, crear público, diseñar plantillas de flujo de trabajo y campaña, crear reglas de tipología. [Más información](#implementation-prepare-your-env)
1. **Personalice la instancia**: crear nuevos campos de datos, añadir tablas/esquemas. [Más información](#implementation-custom-your-instance)
1. **Automatice sus procesos**: configure las funcionalidades de automatización de Adobe Campaign. [Más información](#implementation-automation)
1. **Amplíe la implementación**: conectar con soluciones de Adobe, otros productos y sistemas, conectores y configuración de varias soluciones. [Más información](#implementation-extend)

>[!CAUTION]
>
>Con **Campaign Managed Cloud Services**, su entorno y la configuración inicial los establece Adobe, según los términos del acuerdo de licencia. No se le permite modificar paquetes integrados, esquemas integrados o informes instalados.
>
>Si ha de utilizar un complemento de Campaign o una funcionalidad específica que no se le haya suministrado, debe ponerse en contacto con el **Gestor de transición de Adobe**.

## Antes de empezar{#before-starting}

Esta sección contiene información esencial acerca de la privacidad y seguridad que debe revisarse y tenerse en cuenta antes incluso de iniciar la implementación real.

### Privacidad{#implementation-privacy}

Adobe Campaign incluye procesos y configuraciones que permiten utilizar Campaign de conformidad con las leyes aplicables sobre privacidad de datos y las preferencias de los destinatarios. Puede administrar:

* **Adquisición de datos**: Adobe Campaign le permite recopilar datos, incluida la información personal y confidencial. Por lo tanto, es esencial que reciba y administre el consentimiento de sus destinatarios.

  Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=es#data-acquisition){target="_blank"}

* **Consentimiento de usuario y retención de datos**: debe obtener el consentimiento del usuario, configurar mecanismos de suscripción de inclusión doble, facilitar la exclusión y configurar la retención de datos.

  Obtenga más información en [Documentación de privacidad de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=es#consent){target="_blank"}

* **Reglamentos de protección de datos y privacidad**: consulte [esta sección](privacy.md) para obtener información sobre los requisitos de privacidad y cómo afectan estas regulaciones a su organización y a Adobe Campaign.

### Seguridad

Conozca las directrices y los principios de seguridad con Adobe Campaign en la [Campaign Security checklist](../config/security.md).

## Definir la configuración de Campaign{#implementation-ac-settings}

### Agregar usuarios y conceder permisos{#implementation-add-users}

Puede añadir usuarios manualmente a Campaign y asociarlos a grupos, alineados con la jerarquía de funciones. Los usuarios podrán entonces iniciar sesión y acceder a los datos y permisos adecuados para ellos.

Aprenda a añadir usuarios a Adobe Campaign en [esta sección](../start/gs-permissions.md).

### Instalación de la consola del cliente de Campaign{#implementation-install-console}

La interfaz de usuario principal de la aplicación es un cliente enriquecido; es decir, es una aplicación nativa (Windows) que se comunica con el servidor de aplicaciones de Adobe Campaign únicamente con protocolos de Internet estándar (SOAP, HTTP, etc.). La consola del cliente de Adobe Campaign ofrece una buena facilidad de uso para la productividad, utiliza muy poco ancho de banda (mediante el uso de una caché local) y está diseñada para facilitar la implementación. Esta consola se puede implementar desde un explorador web, se puede actualizar automáticamente y no requiere ninguna configuración de red específica porque solo genera tráfico HTTP(S).

[Obtenga más información sobre la consola del cliente de Campaign](connect.md).

## Preparación del entorno{#implementation-prepare-your-env}

Antes de empezar a enviar mensajes y crear campañas de marketing, debe realizar esto:

1. **Importar perfiles y crear públicos**

   Campaign le ayuda a añadir contactos a la base de datos de Cloud. Puede cargar un archivo, programar y automatizar varias actualizaciones de contacto, recopilar datos en la web o introducir información de perfil directamente en la tabla de destinatarios.

   [Obtenga información sobre cómo importar perfiles](import.md).

   Los públicos se agrupan en listas y se pueden crear mediante flujos de trabajo. A continuación, se pueden definir como objetivo en los envíos multicanal.

   [Obtenga información sobre cómo definir públicos](audiences.md).

1. **Uso de plantillas**

   Las campañas, las entregas, los trabajos o los flujos de trabajo se basan en una plantilla, que almacena la configuración y las capacidades clave. Se proporciona una plantilla integrada por componente que no tiene definida ninguna configuración específica. Debe configurar y adaptar las plantillas a sus necesidades, y ponerlas a disposición de los usuarios finales.


   Aprenda a trabajar con plantillas de campaña en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html?lang=es){target="_blank"}.

   Aprenda a configurar una plantilla de flujo de trabajo en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=es){target="_blank"}.

   Obtenga más información acerca de las plantillas de correo electrónico en esta [página](../send/create-templates.md).


1. **Configuración de reglas de tipología**

   Aproveche las reglas de tipologías de Campaign para filtrar, controlar y monitorizar las entregas. Por ejemplo, las reglas de fatiga controlan la frecuencia y la cantidad de mensajes para evitar la saturación de destinatarios. Una vez implementadas, se hace referencia a las reglas de tipología en las entregas.

   Obtenga más información acerca de la administración de tipologías y fatiga en [esta sección](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=es){target="_blank"}.

1. **Familiarícese con el modelo de datos integrado de Campaign**

   Adobe Campaign viene con un modelo de datos predefinido. Para implementar y personalizar su entorno, debe estar familiarizado con las tablas integradas del modelo de datos de Adobe Campaign y con cómo se relacionan entre sí.

   [Más información sobre el modelo de datos de Campaign](../dev/datamodel.md).

## Personalizar la instancia{#implementation-custom-your-instance}

Puede personalizar muchas áreas y capacidades de Campaign diferentes. La mayoría de nuestros clientes personalizan tres cosas:

1. **Tablas y esquemas**

   Adobe Campaign incluye esquemas comunes para identificar datos como destinatarios, registros de envío, suscripciones, etc.

   Consulte esta sección para obtener más información sobre el [modelo de datos integrado de Campaign](../dev/datamodel.md).

   Puede ampliar los esquemas existentes o crear nuevos esquemas desde cero. Obtenga más información en [esta página](../dev/customize.md).

1. **Paneles de control y listas**

   Puede configurar listas, añadir y quitar campos, y personalizar columnas fácilmente.

   Obtenga información sobre cómo administrar filtros y listas en Campaign en [esta página](../dev/customize.md#gs-lists-and-filters).

   También puede crear nuevos paneles de control para mostrar los datos de Campaign según sus necesidades.

   Obtenga más información en [esta página](../dev/customize.md#gs-custom-dashboards).

1. **Informes**

   Campaign proporciona un conjunto de informes integrados sobre monitorización de entregas, URL y flujos de clics, seguimiento, indicadores de envío y más.

   Además de los informes integrados, Adobe Campaign permite generar informes en distintos contextos y satisfacer diferentes necesidades. En este documento se describen los principios de uso y los modos de implementación.

   Obtenga más información sobre las funcionalidades de creación de informes en Campaign en [esta página](../reporting/gs-reporting.md).


## Configuración de la automatización de campañas{#implementation-automation}

Para organizar campañas de marketing complejas para distintos públicos en varios canales, aproveche las capacidades de automatización de Campaign.

* Use **flujos de trabajo** para administrar procesos y datos. Obtenga más información en [esta documentación](../../automation/workflow/about-workflows.md)

* Configure procesos de **suscripción** y **páginas de destino**.  Obtenga más información en [esta página](../start/subscriptions.md)

* Configure **reglas de tipología** para definir la fatiga y la gestión de control.  Obtenga más información en [esta documentación](../../automation/campaign-opt/campaign-typologies.md)


## Ampliación de la implementación{#implementation-extend}

### Implementación de varias soluciones{#implementation-multi-solutions}

Si utiliza otras soluciones de Adobe, puede conectarlas al entorno de Campaign y combinar funciones.

* Campaign: Journey Orchestration
* Campaign: CDP en tiempo real
* Campaign: Activadores de Experience Cloud
* Campaign: Experience Manager
* Campaign: Target
* Campaign: Audience Manager/servicio principal People
* Campaign: Asset
* Campaign: Conectores de datos de Analytics


También puede utilizar el inicio de sesión único (SSO) para conectarse a Campaign. Obtenga más información en [esta página](connect.md).

Descubra la lista completa de soluciones de Adobe que se pueden integrar con Adobe Campaign [en esta página](../connect/integration.md).

### Conectores{#implementation-connectors}

Conecte Campaign con sistemas de terceros para combinar una amplia gama de funcionalidades y automatizar procesos.

Obtenga más información sobre los conectores disponibles en [esta sección](../connect/integration.md).

**Conexión del CRM a Campaign**

Puede conectar su plataforma de Adobe Campaign a sus sistemas de terceros de CRM y sincronizar los datos: contactos, cuentas, compras, etc.

Aprenda a conectar su sistema CRM a Campaign en [esta sección](../connect/integration.md#gs-crm-connectors)

**Conexión a una base de datos externa**

Puede conectar la base de datos de Campaign Cloud a sistemas externos mediante el módulo de acceso de datos federado (FDA).

Aprenda a configurar el módulo FDA de Campaign para definir los parámetros de acceso en [esta sección](../connect/integration.md#gs-fda)
