---
title: Paquetes integrados
description: Descubra qué paquetes integrados están en Campaign v8, en qué se diferencian de los paquetes de datos personalizados y cuáles están disponibles
feature: Architecture
role: Admin, Developer
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e656c701-3899-4db3-989c-de0980ddfffa
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 87e9b7ceb3c082407ac4534e0909c6f7db76e62a
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 17%
---
# Paquetes integrados {#built-in-packages}

Los paquetes integrados (también conocidos como paquetes estándar) contienen las funciones de Adobe Campaign. En la versión 8 de Campaign, Adobe instala y administra estos paquetes por usted. No es necesario que los instale.

## Paquetes integrados y paquetes personalizados {#built-in-vs-custom}

Campaign utiliza dos tipos de paquetes. Asegúrese de que trabaja con el correcto.

| | Paquetes integrados | Paquetes personalizados |
|---|---|---|
| Objetivo | Proporcionar las funciones de Campaign, como canales, integraciones y complementos. | Exporte e importe su propia configuración y datos, por ejemplo, desde un entorno de ensayo a un entorno de producción. |
| Quién los administra | Adobe los instala y administra. Con Cloud Services administrados, no puede modificar los paquetes integrados instalados. | Puede crearlos, exportarlos e importarlos. |

## Compruebe los paquetes instalados {#check-installed-packages}

Para comprobar qué paquetes integrados están instalados en su instancia, vaya a **[!UICONTROL Administration > Configuration > Package management > Installed packages]**. También puede verlos en la Monitorización de instancias del Panel de control de Campaign. Obtenga más información en [Resumen de supervisión de campañas](../start/monitor.md#monitor-instance).

Si necesita un paquete o complemento que no se haya aprovisionado por usted, póngase en contacto con el Servicio de atención al cliente de Adobe o con su administrador de transición de Adobe.

## Lista de paquetes integrados {#list-of-built-in-packages}

En la tabla siguiente se enumeran los paquetes integrados para obtener información. La disponibilidad de cada paquete está sujeta al acuerdo de licencia y al modelo de implementación.

| Paquete | Descripción |
|---|---|
| envío | Paquete principal obligatorio de Adobe Campaign. Permite realizar envíos. [Más información](../start/gs-message.md) |
| Campañas de marketing (Campaign) | Define, optimiza, ejecuta y analiza las comunicaciones y las campañas de marketing. [Más información](../start/campaigns.md) |
| Recursos de Marketing (MRM) | Controla las acciones de marketing de forma cooperativa, con administración y seguimiento de tareas, presupuestos y recursos de marketing. [Más información](../../automation/mrm/about-marketing-resource-management.md) |
| Motor de ofertas (interacción) | Responde en tiempo real durante una interacción con un contacto realizando una o varias ofertas adaptadas. [Más información](../interaction/interaction.md) |
| Redes sociales (Marketing social) | Sincroniza Adobe Campaign con X (anteriormente Twitter). [Más información](../connect/ac-tw.md) |
| Control y ejecución de mensajes transaccionales (Centro de mensajes) | Gestiona los mensajes de déclencheur generados a partir de eventos en sistemas de información, con mayor disponibilidad y mejor gestión de carga. [Más información](../send/transactional.md) |
| Canal LINE | Realiza envíos a través del canal LINE. [Más información](../send/line/line.md) |
| Canal de correo directo | Envía envíos a través del canal de correo postal. [Más información](../send/direct-mail.md) |
| Canal móvil (SMS) | Envía envíos a través del canal móvil (SMS), incluido el conector de SMS v2 (disponible de forma general desde la versión 8.9.1). [Más información](../send/sms/sms.md) |
| Canal de aplicaciones móviles | Envía notificaciones personalizadas a dispositivos iOS y Android a través de aplicaciones. [Más información](../send/push.md) |
| Administrador de contenido | Crea boletines informativos o sitios web recurrentes y, a continuación, valida y publica los mensajes. [Más información](../../automation/workflow/content-management.md) |
| Encuestas en línea (Gestor de encuestas) | Crea y administra formularios en línea para agregar o modificar información de perfil, suscribirse, cancelar la suscripción o entrar en una competencia. [Más información](../dev/surveys/about-surveys.md) |
| Análisis de marketing | Analiza y mide datos, calcula estadísticas y simplifica la creación de informes. [Más información](../reporting/gs-reporting.md) |
| Gestor de respuestas | Mide el éxito y la rentabilidad de las campañas u ofertas de marketing en todos los canales. [Más información](../../automation/response/about-response-manager.md) |
| Acceso a datos externos (Acceso de datos federado) | Procesa la información almacenada en bases de datos externas sin cambiar la estructura de los datos de Adobe Campaign. [Más información](../connect/fda.md) |
| Optimización de la campaña | Controla, filtra y supervisa los envíos para que los mensajes cumplan las necesidades de los clientes y las políticas de comunicación de la empresa. [Más información](../../automation/campaign-opt/campaign-typologies.md) |
| Monitorización de la capacidad de entrega (capacidad de entrega por correo electrónico) | Mide si los mensajes llegan a la bandeja de entrada sin rebotar ni marcarse como correo no deseado. [Más información](../send/monitoring-deliverability.md) |
| Administración de cupones | Crea conjuntos de cupones para añadirlos a ofertas de marketing. [Más información](../send/personalized-coupons.md) |
| Renderizado de la bandeja de entrada (IR) | Previsualiza los mensajes en los contextos en los que se pueden recibir y comprueba la compatibilidad con los principales clientes de escritorio y correo electrónico web. [Más información](../send/inbox-rendering.md) |
| Marketing central/local (Marketing distribuido) | Implementa campañas cooperativas entre entidades centrales, como la sede central, y entidades locales, como los puntos de ventas. [Más información](../../automation/distributed-marketing/about-distributed-marketing.md) |
| Conectores CRM | Vincula Adobe Campaign a sistemas CRM de terceros. [Más información](../connect/crm.md) |
| Conectores de análisis web | Permite que Adobe Campaign y Adobe Analytics interactúen. [Más información](../connect/ac-aa.md) |
| Integración de AEM | Administra el contenido de los correos electrónicos y los formularios en Adobe Experience Manager. [Más información](../connect/ac-aem.md) |
| Integración de públicos compartidos de Adobe Experience Cloud | Intercambia y comparte audiencias con soluciones y aplicaciones de [!DNL Adobe CX Enterprise] (anteriormente Adobe Experience Cloud). [Más información](../start/shared-audiences.md) |
| Integración con Adobe Experience Cloud | Importa y exporta audiencias de [!DNL Adobe CX Enterprise] soluciones (anteriormente Adobe Experience Cloud) a Adobe Campaign. [Más información](../connect/integration.md) |
| Reglamento de protección de datos de privacidad | Añade funcionalidad para ayudar con el cumplimiento de la privacidad. [Más información](../start/privacy.md) |
| Compatibilidad con AMP | Envía correos electrónicos dinámicos con el formato AMP interactivo para correo electrónico. [Más información](../send/defining-interactive-content.md) |


>[!NOTE]
>
>Los paquetes Recursos de marketing (MRM), Administración de cupones y Encuestas en línea no están disponibles en el contexto de una implementación empresarial (FDAC) de Campaign. Obtenga más información en [Disponibilidad de funciones](../architecture/enterprise-deployment.md#feature-availability).

## Temas relacionados {#related-topics}

* [Trabajar con paquetes de datos](../dev/packages.md): cree, exporte e importe sus propios paquetes personalizados.
* [Flujos de trabajo técnicos](../../automation/workflow/technical-workflows.md): los flujos de trabajo técnicos integrados y el paquete que instala cada uno de ellos.
* [Disponibilidad de características en implementaciones de FDAC](enterprise-deployment.md#feature-availability): las capacidades que no están disponibles en implementaciones de empresas (FDAC).
* [Funciones no admitidas](../start/v7-to-v8.md#gs-removed): las funciones de Campaign Classic v7 que ya no son compatibles con v8.
* [Principios globales](general-architecture.md): lo que puede y no puede modificar en un entorno de Cloud Services administrados.
* [Introducción a la versión 8 de Campaign](../start/get-started.md): una descripción general de las funciones principales y los complementos.
