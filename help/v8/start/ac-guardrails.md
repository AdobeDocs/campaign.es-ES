---
title: Protecciones de Campaign v8
description: Protecciones de Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: cda523168525c24ec1c976850bc336f273276ac9
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 42%

---

# Protecciones del producto{#guardrails}

Los derechos, limitaciones de productos y protecciones de rendimiento se enumeran en [Página de descripción del producto de Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/es/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}.

A continuación encontrará limitaciones y protecciones adicionales al utilizar [!DNL Adobe Campaign].

Las protecciones y limitaciones identifican capacidades, arquitectura o procesos que no son compatibles con esta versión del producto o que no interactúan correctamente con él. Revise detenidamente estas limitaciones.

* Adobe Campaign v8 no está disponible para implementaciones locales/híbridas; solo se presenta como Cloud Service administrado por Adobe
* Los clientes existentes no pueden migrar de un entorno de Adobe Campaign existente a Adobe Campaign v8
* En el contexto de un [Implementación empresarial (FFDA)](../architecture/enterprise-deployment.md), no se proporciona replicación de datos bidireccional: la replicación solo se produce desde la base de datos local de Campaign a la base de datos de Cloud
* Las capacidades enumeradas [en esta sección](v7-to-v8.md#gs-unavailable-features) no están disponibles en la versión actual de Campaign v8
* Algunas funciones no disponibles o eliminadas siguen estando visibles en la interfaz de usuario
* En el contexto de un [Implementación empresarial (FFDA)](../architecture/enterprise-deployment.md), los mecanismos de suscripción (inclusión) y baja (exclusión) y el registro móvil son procesos asincrónicos. Las solicitudes se procesan cada hora a través de un flujo de trabajo técnico específico. [Más información](../architecture/replication.md#tech-wf)
* Los usuarios finales deben gestionar manualmente los duplicados. [Más información](../architecture/keys.md)
* Adobe Campaign v8 no admite rendimiento ampliado en aplicaciones web y API: en caso de necesidades específicas, póngase en contacto con el Adobe para obtener ayuda
* El módulo de optimización de Adobe Campaign Campaign no tiene en cuenta los envíos programados en las reglas de tipología de presión. Obtenga más información en la [documentación de la versión 7 de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=es#setting-the-period){target=&quot;_blank&quot;}