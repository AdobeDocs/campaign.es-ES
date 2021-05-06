---
solution: Campaign Classic
product: campaign
title: Directrices de implementación
description: Aprenda a implementar Campaign v8
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
translation-type: tm+mt
source-git-commit: 6fee88c2bcfade752d45712adeab50e199f0c07c
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 4%

---

# Directrices de implementación de Campaign

En esta sección, aprenderá a ajustar Adobe Campaign a los requisitos de su empresa. Siga estas directrices para estructurar y organizar la implementación.

1. **Definir configuración**: conceder acceso, compartir consola de cliente, configurar canales (correo electrónico, push, sms)
1. **Prepare su entorno**: importar perfiles, crear audiencias, diseñar plantillas de flujo de trabajo y campaña, crear reglas de tipología
1. **Personalice la instancia**: crear nuevos campos de datos, añadir tablas/esquemas
1. **Amplíe la implementación**: conexión a soluciones de Adobe, otros productos y sistemas: conectores, configuración de varias soluciones

## Antes de empezar

Esta sección incluye información para desarrolladores específica de su implementación que deben cuidar de la privacidad y la seguridad antes de comenzar.

### Privacidad

Adobe Campaign incluye procesos y configuraciones que permiten utilizar Campaign de conformidad con las leyes aplicables sobre privacidad de datos y las preferencias de los destinatarios. Puede administrar:

* **Adquisición** de datos: Adobe Campaign le permite recopilar datos, incluida información personal y confidencial. Por lo tanto, es esencial que reciba y administre el consentimiento de sus destinatarios. Obtenga más información en la [documentación del Campaign Classic](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **Consentimiento de usuario y retención** de datos: Obtenga información sobre cómo obtener el consentimiento del usuario, configurar mecanismos de suscripción de doble adhesión, facilitar la exclusión y configurar la retención de datos en la documentación de privacidad del  [Campaign Classic](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **Reglamentos** de protección de datos y privacidad: consulte la  [documentación de privacidad del ](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) Campaign Classic para obtener información sobre el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Privacidad del Consumidor de California (CCPA) y otros requisitos de privacidad internacionales, y cómo estos reglamentos afectan a su organización y a Adobe Campaign.

### Seguridad

Conozca las directrices y los principios de seguridad con Adobe Campaign en [Campaign Security checklist](../config/security.md))

## Definir la configuración de campaña

### Agregar usuarios y conceder permisos

Puede agregar usuarios manualmente a Campaign y asociarlos a grupos, alineados con la jerarquía de funciones. Los usuarios podrán entonces iniciar sesión y acceder a los datos y permisos adecuados para ellos.

:arrow_upper_right: Aprenda a añadir usuarios a Adobe Campaign en [esta sección](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started).

### Instalación de la consola del cliente de Campaign

La interfaz de usuario principal de la aplicación es un cliente enriquecido, es decir, una aplicación nativa (Windows) que se comunica con el servidor de aplicaciones de Adobe Campaign únicamente con protocolos de Internet estándar (SOAP, HTTP, etc.). Adobe Campaign Client Console ofrece una buena facilidad de uso para la productividad, utiliza muy poco ancho de banda (mediante el uso de una caché local) y está diseñado para facilitar la implementación. Esta consola se puede implementar desde un explorador de Internet, se puede actualizar automáticamente y no requiere ninguna configuración de red específica porque solo genera tráfico HTTP(S).

:bulb: [Obtenga más información sobre la Consola de cliente de Campaign](connect.md).

## Preparación del entorno

Antes de empezar a enviar mensajes y crear campañas de marketing, debe:

1. Importar perfiles y crear audiencias

   Campaign le ayuda a añadir contactos a la base de datos de Cloud. Puede cargar un archivo, programar y automatizar varias actualizaciones de contacto, recopilar datos en la web o introducir información de perfiles directamente en la tabla de destinatarios.

   :bulb: [Obtenga información sobre cómo importar perfiles](import.md).

   Las audiencias se agrupan en listas y se pueden crear mediante flujos de trabajo. A continuación, se pueden definir como objetivo en los envíos multicanal.

   :bulb: [Obtenga información sobre cómo definir audiencias](audiences.md).

1. Crear plantillas

   Las campañas, los envíos, los trabajos o los flujos de trabajo se basan en una plantilla, que almacena la configuración y las capacidades clave. Se proporciona una plantilla integrada para cada componente, para el que no se ha definido ninguna configuración específica. Debe configurar y adaptar las plantillas a sus necesidades y ponerlas a disposición de los usuarios finales.

   :arrow_upper_right: [Más información sobre las plantillas de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   :arrow_upper_right: Aprenda a trabajar con plantillas de campaña en [esta página](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   :arrow_upper_right: Obtenga información sobre cómo configurar una plantilla de flujo de trabajo en [esta página](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)

1. Configuración de reglas de tipología

   Aproveche las reglas de tipologías de Campaign para filtrar, controlar y monitorizar los envíos. Por ejemplo, las reglas de fatiga controlan la frecuencia y la cantidad de mensajes para evitar la saturación de destinatarios. Una vez implementadas, se hace referencia a las reglas de tipología en las entregas.

   :arrow_upper_right: [Obtenga más información sobre tipologías y administración de la fatiga](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. Familiarícese con el modelo de datos integrado de Campaign

   Adobe Campaign viene con un modelo de datos predefinido. Para implementar y personalizar su entorno, debe estar familiarizado con las tablas integradas del modelo de datos de Adobe Campaign y su interacción.

   :bulb: [Obtenga más información sobre el modelo de datos de Campaign](../dev/datamodel.md).

## Personalizar la instancia

Puede personalizar muchas áreas y capacidades de Campaign diferentes. La mayoría de nuestros clientes personalizan tres cosas:

1. **Tablas y esquemas**

   Adobe Campaign incluye esquemas comunes para identificar datos como: destinatarios, registros de envío, suscripciones, etc.

   :bulb: Consulte esta sección para obtener más información sobre [el modelo de datos integrado de Campaign](../dev/datamodel.md).

   :bulb: Puede ampliar los esquemas existentes o crear nuevos esquemas desde cero. Obtenga más información en [esta página](../dev/customize.md).

1. **Paneles y listas**

   Puede configurar listas, agregar y quitar campos y personalizar columnas fácilmente.

   :bulb: Obtenga información sobre cómo administrar filtros y listas en Campaign en [esta página](../dev/customize.md#gs-lists-and-filters).

   También puede crear nuevos tableros para mostrar los datos de Campaign según sus necesidades.

   :bulb: Obtenga más información en [esta página](../dev/customize.md#gs-custom-dashboards).

1. **Informes**

   Campaign proporciona un conjunto de informes integrados sobre monitorización de envío, URL y flujos de clics, seguimiento, indicadores de envío y más.

   Además de los informes integrados, Adobe Campaign permite generar informes en distintos contextos y satisfacer diferentes necesidades. En este documento se describen los principios de uso y los modos de implementación.

   :bulb: Obtenga más información sobre las funcionalidades de informes en Campaign en [esta página](reporting.md).


## Configuración de la automatización de campañas

Para organizar campañas de marketing complejas para distintas audiencias en varios canales, aproveche las capacidades de automatización de Campaign.

* Flujos de trabajo: administrar procesos y datos

* Suscripciones y páginas de aterrizaje

* Reglas de tipología: fatiga y gestión de control

## Ampliación de la implementación

### Implementación de varias soluciones

Si utiliza otras soluciones de Adobe, puede conectarlas al entorno de Campaign y combinar funciones.

* Campaña: Journey Orchestration
* Campaign: CDP en tiempo real
* Campaña: Déclencheur del Experience Cloud
* Campaña: Experience Manager
* Campaign - Target
* Campaign: Audience Manager/servicio principal People
* Campaign - Asset
* Campaign: Conectores de datos de Analytics


También puede utilizar el inicio de sesión único (SSO) para conectarse a Campaign. Obtenga más información en [esta página](connect.md).

:bulb: Descubra la lista completa de soluciones de Adobe que se pueden integrar con Adobe Campaign [en esta página](../connect/integration.md).

### Conectores

Conecte Campaign con sistemas de terceros para combinar una amplia gama de funcionalidades y automatizar procesos.

:bulb: Obtenga más información sobre los conectores disponibles en [esta sección](../connect/integration.md).

**Conecte su CRM a Campaign**

Puede conectar su plataforma de Adobe Campaign a sus sistemas de terceros de CRM y sincronizar los datos: contactos, cuentas, compras, etc.

:bulb: Aprenda a conectar su sistema CRM a Campaign en [esta sección](../connect/integration.md#gs-crm-connectors)

**Conexión a una base de datos externa**

Puede conectar la base de datos de Campaign Cloud a sistemas externos mediante el módulo Federated Data Access (FDA).

:bulb: Aprenda a configurar el módulo FDA de Campaign para definir los parámetros de acceso en [esta sección](../connect/integration.md#gs-fda)
