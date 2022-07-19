---
title: Protecciones de Campaign v8
description: Protecciones de Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 97%

---

# Protecciones del producto{#guardrails}

Los derechos, limitaciones de productos y protecciones de rendimiento se enumeran en la [página de descripción del producto de Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}.

A continuación, encontrará limitaciones y protecciones adicionales al utilizar [!DNL Adobe Campaign].

Las protecciones y limitaciones identifican funcionalidades, arquitectura o procesos que no son compatibles con esta versión del producto o que no interactúan correctamente con él. Revise detenidamente estas limitaciones.

* Adobe Campaign v8 no está disponible para implementaciones locales o híbridas; solo se presenta como servicio en la nube administrado por Adobe
* Los clientes existentes no pueden migrar de un entorno de Adobe Campaign existente a Adobe Campaign v8
* En el contexto de una [implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), no se proporciona replicación de datos bidireccional: la replicación solo se produce de la base de datos local de Campaign a la base de datos en la nube
* Las capacidades enumeradas [en esta sección](v7-to-v8.md#gs-unavailable-features) no están disponibles en la versión actual de Campaign v8
* Algunas funciones no disponibles o eliminadas siguen estando visibles en la interfaz de usuario
* En el contexto de una [implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), los mecanismos de suscripción (inclusión) y baja (exclusión) y el registro móvil son procesos asincrónicos. Las solicitudes se procesan cada hora a través de un flujo de trabajo técnico específico. [Más información](../architecture/replication.md#tech-wf)
* Los usuarios finales deben gestionar manualmente los duplicados. [Más información](../architecture/keys.md)
* Adobe Campaign v8 no admite rendimiento ampliado en aplicaciones web y API: en caso de necesidades específicas, póngase en contacto con Adobe para obtener ayuda
* El módulo Optimización de la campaña de Adobe Campaign no tiene en cuenta los envíos programados en las reglas de tipología de presión. Obtenga más información en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/pressure-rules.html).