---
product: Adobe Campaign
title: Introducción a las campañas de marketing
description: Introducción a las campañas de marketing
feature: Audiencias
role: Data Engineer
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66,c4798c8f-619e-4a60-80d7-29b9e4c61168
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: ht
source-wordcount: '746'
ht-degree: 100%

---

# Introducción a las campañas de marketing{#gs-ac-campaigns}

Adobe Campaign ofrece un conjunto de soluciones que le ayudan a personalizar y entregar campañas en todos sus canales en línea y sin conexión. Puede crear, configurar, ejecutar y analizar campañas de marketing. Todas las campañas de marketing se pueden administrar desde un centro de control unificado. Descubra cómo examinar y crear campañas de marketing en esta sección.

Las campañas incluyen acciones (envíos) y procesos (importación o extracción de archivos), así como recursos (documentos de marketing, descripciones de envíos). Todos ellos se utilizan en las campañas de marketing. Las campañas son parte de un programa y los programas se incluyen en un plan de campaña.

## Organización de campañas en canales múltiples

Adobe Campaign le permite diseñar y organizar campañas dirigidas y personalizadas en varios canales: correo electrónico, correo directo, SMS, notificaciones push. Una sola interfaz proporciona todas las funcionalidades necesarias para programar, organizar, configurar, personalizar, automatizar, ejecutar y medir todas las campañas y comunicaciones.

![](assets/campaign-tab.png)

### Conceptos básicos

Antes de comenzar a implementar campañas de marketing, debe estar familiarizado con los siguientes conceptos:

* **Campaña de marketing**: una campaña unifica todos los elementos relacionados con una campaña de marketing, como envíos, reglas de direccionamiento, costes, archivos de exportación, documentos relacionados, etc. Cada campaña se adjunta a un programa.

* **Programa**: un programa permite definir acciones de marketing para un periodo de calendario (lanzamiento, escrutinio, lealtad, etc.). Cada programa contiene campañas vinculadas a un calendario, que proporciona una vista general.

* **Plan**: el plan de marketing puede contener varios programas. Está vinculado a un periodo, tiene un presupuesto asignado y también puede estar vinculado a documentos y objetivos.

* **Flujo de trabajo de la campaña**: un flujo de trabajo de campaña contiene actividades para crear la lógica de campaña. Utilice flujos de trabajo de la campaña para definir audiencias y crear envíos para todos los canales disponibles.

* **Campañas recurrentes**: las campañas recurrentes se crean a partir de una plantilla específica que define la plantilla de flujo de trabajo que se va a ejecutar y la programación de ejecución.

* **Campaña periódica**: una campaña periódica es una campaña creada automáticamente según la programación de ejecución de su plantilla.

## Espacio de trabajo de campañas de marketing

Adobe Campaign permite crear, configurar, ejecutar y analizar todas las campañas de marketing desde un centro de control unificado.

![](assets/calendar.png)

↗️ Descubra cómo acceder e implementar campañas de marketing en la [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/about-marketing-campaigns/accessing-marketing-campaigns.html?lang=es#orchestrating-campaigns){target=&quot;_blank&quot;}


## Pasos clave para comenzar

Los pasos clave para crear una campaña de marketing multicanal son estos:

1. **Planificar y diseñar programas y campañas de marketing**

   Defina la jerarquía y la programación, establezca el presupuesto, añada recursos, y seleccione operadores.

   ↗️ Obtenga información sobre cómo crear un plan de marketing y configurar campañas en la [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=es#creating-plan-and-program-hierarchy){target=&quot;_blank&quot;}

   Todas las campañas de marketing se basan en una plantilla que almacena las configuraciones y capacidades principales. Se proporciona una plantilla para crear una campaña sin ninguna configuración específica definida. Puede crear y configurar las plantillas de campañas y luego crear campañas a partir de estas plantillas.

   ↗️ Aprenda a usar plantillas de campaña en la [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=es#orchestrating-campaigns){target=&quot;_blank&quot;}

   ↗️ Descubra campañas recurrentes y cómo configurarlas en la [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=es#recurring-and-periodic-campaigns){target=&quot;_blank&quot;}

1. **Definir audiencias**

   Puede crear la audiencia en un flujo de trabajo o seleccionar un grupo existente, como una lista de destinatarios, suscriptores de un boletín informativo, destinatarios de una entrega anterior o cualquier condición de filtrado.

   ![](assets/campaign-wf.png)

   ↗️ Aprenda a definir la audiencia de sus mensajes en la [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=es#orchestrating-campaigns){target=&quot;_blank&quot;}

1. **Creación de entregas**

   Seleccione los canales, defina el contenido del mensaje e inicie las entregas.

   ![](assets/campaign-dashboard.png)

   ↗️ Obtenga información sobre cómo crear e iniciar entregas de campañas de marketing en la [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=es#creating-deliveries){target=&quot;_blank&quot;}

   Puede asociar varios documentos a una campaña: informe, foto, página web, diagrama, etc.

   ↗️ Obtenga más información acerca de los documentos asociados en la [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-assets.html?lang=es#adding-documents){target=&quot;_blank&quot;}

1. **Configuración del proceso de aprobación**

   Adobe Campaign permite configurar los procesos de aprobación de las etapas principales de la campaña de marketing en modo de colaboración. Para cada campaña, puede aprobar el objetivo de entrega, los contenidos y los costes. Los operadores de Adobe Campaign responsables de la aprobación pueden recibir notificaciones por correo electrónico y aceptar o rechazar la aprobación a través de la consola o de una conexión web.

   ↗️ Obtenga información sobre cómo configurar y administrar aprobaciones en la [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=es#orchestrating-campaigns){target=&quot;_blank&quot;}

