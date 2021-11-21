---
title: Directrices de implementación
description: Aprenda a implementar Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: eb8ad88ffd9dbaaf1f9ace2e88ba4486711bc72d
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 100%

---

# Directrices de implementación de Campaign

En esta sección, aprenderá a ajustar Adobe Campaign a los requisitos de su compañía. Siga estas directrices para estructurar y organizar la implementación.

1. **Definir configuración**: conceder acceso, compartir la consola del cliente, configurar canales (correo electrónico, push, sms)
1. **Prepare su entorno**: importar perfiles, crear audiencias, diseñar plantillas de flujo de trabajo y campaña, crear reglas de tipología
1. **Personalice la instancia**: crear nuevos campos de datos, añadir tablas/esquemas
1. **Amplíe la implementación**: conectar con soluciones de Adobe, otros productos y sistemas, conectores y configuración de varias soluciones

>[!CAUTION]
>
>Con **Campaign Managed Cloud Services**, su entorno y la configuración inicial se han configurado con Adobe, según los términos del acuerdo de licencia. No se le permite modificar paquetes integrados, esquemas integrados o informes instalados.
>
>Si necesita utilizar un complemento de Campaign o una funcionalidad específica que no se haya aprovisionado por usted, debe ponerse en contacto con el **Servicio de atención al cliente de Adobe**.

## Antes de empezar

Esta sección contiene información esencial acerca de la privacidad y seguridad que debe revisarse y tenerse en cuenta antes incluso de iniciar la implementación real.

### Privacidad

Adobe Campaign incluye procesos y configuraciones que permiten utilizar Campaign de conformidad con las leyes aplicables sobre privacidad de datos y las preferencias de los destinatarios. Puede administrar:

* **Adquisición de datos**: Adobe Campaign le permite recopilar datos, incluida la información personal y confidencial. Por lo tanto, es esencial que reciba y administre el consentimiento de sus destinatarios. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=es#data-acquisition)

* **Consentimiento de usuario y retención de datos**: Aprenda a obtener el consentimiento del usuario, configurar mecanismos de suscripción de doble inclusión, facilitar la exclusión y configurar la retención de datos en la documentación de privacidad de [Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=es#consent)

* **Reglamentos de protección de datos y privacidad**: Consulte la [documentación de privacidad de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=es){target=&quot;_blank&quot;} para obtener información acerca del Reglamento general de protección de datos (RGPD) de la Unión Europea, la Ley de privacidad del consumidor de California (CCPA) y otros requisitos de privacidad internacionales, y cómo estos reglamentos afectan a su organización y a Adobe Campaign.

### Seguridad

Conozca las directrices y los principios de seguridad con Adobe Campaign en la [Campaign Security checklist](../config/security.md).

## Definir la configuración de Campaign

### Agregar usuarios y conceder permisos

Puede añadir usuarios manualmente a Campaign y asociarlos a grupos, alineados con la jerarquía de funciones. Los usuarios podrán entonces iniciar sesión y acceder a los datos y permisos adecuados para ellos.

![](../assets/do-not-localize/book.png) Aprenda a añadir usuarios a [esta sección](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=es#getting-started){target=&quot;_blank&quot;}.

### Instalación de la consola del cliente de Campaign

La interfaz de usuario principal de la aplicación es un cliente enriquecido; es decir, es una aplicación nativa (Windows) que se comunica con el servidor de aplicaciones de Adobe Campaign únicamente con protocolos de Internet estándar (SOAP, HTTP, etc.). La consola del cliente de Adobe Campaign ofrece una buena facilidad de uso para la productividad, utiliza muy poco ancho de banda (mediante el uso de una caché local) y está diseñada para facilitar la implementación. Esta consola se puede implementar desde un explorador web, se puede actualizar automáticamente y no requiere ninguna configuración de red específica porque solo genera tráfico HTTP(S).

![](../assets/do-not-localize/glass.png) [Obtenga más información sobre la consola del cliente de Campaign](connect.md).

## Preparación del entorno

Antes de empezar a enviar mensajes y crear campañas de marketing, debe realizar esto:

1. Importar perfiles y crear audiencias

   Campaign le ayuda a añadir contactos a la base de datos de Cloud. Puede cargar un archivo, programar y automatizar varias actualizaciones de contacto, recopilar datos en la web o introducir información de perfil directamente en la tabla de destinatarios.

   ![](../assets/do-not-localize/glass.png) [Obtenga información sobre cómo importar perfiles](import.md).

   Las audiencias se agrupan en listas y se pueden crear mediante flujos de trabajo. A continuación, se pueden definir como objetivo en los envíos multicanal.

   ![](../assets/do-not-localize/glass.png) [Obtenga información sobre cómo definir audiencias](audiences.md).

1. Crear plantillas

   Las campañas, las entregas, los trabajos o los flujos de trabajo se basan en una plantilla, que almacena la configuración y las capacidades clave. Se proporciona una plantilla integrada por componente que no tiene definida ninguna configuración específica. Debe configurar y adaptar las plantillas a sus necesidades, y ponerlas a disposición de los usuarios finales.

   ![](../assets/do-not-localize/book.png) [Más información acerca de las plantillas de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=es){target=&quot;_blank&quot;}

   ![](../assets/do-not-localize/book.png) Aprenda a usar plantillas de campaña en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=es#orchestrating-campaigns){target=&quot;_blank&quot;}

   ![](../assets/do-not-localize/book.png) Aprenda a configurar una plantilla de flujo de trabajo en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=es#workflow-templates){target=&quot;_blank&quot;}

1. Configuración de reglas de tipología

   Aproveche las reglas de tipologías de Campaign para filtrar, controlar y monitorizar las entregas. Por ejemplo, las reglas de fatiga controlan la frecuencia y la cantidad de mensajes para evitar la saturación de destinatarios. Una vez implementadas, se hace referencia a las reglas de tipología en las entregas.

   ![](../assets/do-not-localize/book.png) Obtenga más información acerca de tipologías y administración de la fatiga en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=es#orchestrating-campaigns){target=&quot;_blank&quot;}

1. Familiarícese con el modelo de datos integrado de Campaign

   Adobe Campaign viene con un modelo de datos predefinido. Para implementar y personalizar su entorno, debe estar familiarizado con las tablas integradas del modelo de datos de Adobe Campaign y con cómo se relacionan entre sí.

   ![](../assets/do-not-localize/glass.png) [Obtenga más información acerca del modelo de datos de Campaign](../dev/datamodel.md).

## Personalizar la instancia

Puede personalizar muchas áreas y capacidades de Campaign diferentes. La mayoría de nuestros clientes personalizan tres cosas:

1. **Tablas y esquemas**

   Adobe Campaign incluye esquemas comunes para identificar datos como destinatarios, registros de envío, suscripciones, etc.

   ![](../assets/do-not-localize/glass.png) Consulte esta sección para obtener más información acerca del [modelo de datos integrado de Campaign](../dev/datamodel.md).

   ![](../assets/do-not-localize/glass.png) Puede ampliar los esquemas existentes o crear nuevos esquemas desde cero. Obtenga más información en [esta página](../dev/customize.md).

1. **Paneles y listas**

   Puede configurar listas, añadir y quitar campos, y personalizar columnas fácilmente.

   ![](../assets/do-not-localize/glass.png) Obtenga información sobre cómo administrar filtros y listas en Campaign en [esta página](../dev/customize.md#gs-lists-and-filters).

   También puede crear nuevos paneles para mostrar los datos de Campaign según sus necesidades.

   ![](../assets/do-not-localize/glass.png) Obtenga más información en [esta página](../dev/customize.md#gs-custom-dashboards).

1. **Informes**

   Campaign proporciona un conjunto de informes integrados sobre monitorización de entregas, URL y flujos de clics, seguimiento, indicadores de envío y más.

   Además de los informes integrados, Adobe Campaign permite generar informes en distintos contextos y satisfacer diferentes necesidades. En este documento se describen los principios de uso y los modos de implementación.

   ![](../assets/do-not-localize/glass.png) Obtenga más información acerca de las funcionalidades de creación de informes en Campaign en [esta página](reporting.md).


## Configuración de la automatización de campañas

Para organizar campañas de marketing complejas para distintas audiencias en varios canales, aproveche las capacidades de automatización de Campaign.

* Flujos de trabajo: administrar procesos y datos

* Suscripciones y páginas de destino

* Reglas de tipología: fatiga y gestión de control

## Ampliación de la implementación

### Implementación de varias soluciones

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

![](../assets/do-not-localize/glass.png) Descubra la lista completa de soluciones de Adobe que se pueden integrar con Adobe Campaign [en esta página](../connect/integration.md).

### Conectores

Conecte Campaign con sistemas de terceros para combinar una amplia gama de funcionalidades y automatizar procesos.

![](../assets/do-not-localize/glass.png) Obtenga más información acerca de los conectores disponibles en [esta sección](../connect/integration.md).

**Conexión del CRM a Campaign**

Puede conectar su plataforma de Adobe Campaign a sus sistemas de terceros de CRM y sincronizar los datos: contactos, cuentas, compras, etc.

![](../assets/do-not-localize/glass.png) Aprenda a conectar su sistema CRM a Campaign en [esta sección](../connect/integration.md#gs-crm-connectors)

**Conexión a una base de datos externa**

Puede conectar la base de datos de Campaign Cloud a sistemas externos mediante el módulo de acceso de datos federado (FDA).

![](../assets/do-not-localize/glass.png) Aprenda a configurar el módulo FDA de Campaign para definir los parámetros de acceso en [esta sección](../connect/integration.md#gs-fda)
