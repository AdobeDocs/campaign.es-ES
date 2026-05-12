---
title: Mecanismos de protección de Campaign v8
description: Mecanismos de protección de Campaign v8
feature: Configuration
role: User
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
TQID: https://experienceleague.adobe.com/4FF81xd4CiMT3fusDRU32n0-ap16O1RVUEhGIbz33Os
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 265
ht-degree: 78%

---

# Mecanismos de protección del producto{#guardrails}

Los derechos, limitaciones de productos y protecciones de rendimiento se enumeran en [página de descripción del producto de Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/es/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

A continuación, encontrará limitaciones y mecanismos de protección adicionales al utilizar [!DNL Adobe Campaign].

Los mecanismos de protección y las limitaciones identifican funcionalidades, arquitectura o procesos que no son compatibles con esta versión del producto o que no interactúan correctamente con él. Revise detenidamente estas limitaciones.

* Adobe Campaign v8 no está disponible para implementaciones locales o híbridas; solo se presenta como servicio en la nube administrado por Adobe
* No hay ninguna migración automática a Adobe Campaign v8 disponible para los clientes existentes
* En el contexto de una [implementación empresarial (FDAC)](../../v8/architecture/enterprise-deployment.md), no se proporciona replicación de datos bidireccional: la replicación solo se produce de la base de datos local de Campaign a la base de datos en la nube
* Las capacidades enumeradas [en esta sección](v7-to-v8.md#gs-unavailable-features) no están disponibles en la versión actual de Campaign v8
* Algunas funciones no disponibles o eliminadas siguen estando visibles en la interfaz de usuario
* En el contexto de una [implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), los mecanismos de suscripción (inclusión) y baja (exclusión) y el registro móvil son procesos asincrónicos. Las solicitudes se procesan cada hora a través de un flujo de trabajo técnico específico. [Más información](../architecture/replication.md#tech-wf)
* En el contexto de una implementación de [Enterprise (FDAC)](../architecture/enterprise-deployment.md), los usuarios finales deben gestionar manualmente los duplicados. [Más información](../architecture/keys.md)
* Adobe Campaign v8 no admite rendimiento ampliado en aplicaciones web y API: en caso de necesidades específicas, póngase en contacto con Adobe para obtener ayuda
* En el contexto de una [implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), el módulo Optimización de la campaña de Adobe Campaign no tiene en cuenta los envíos programados en las reglas de tipología de presión. Obtenga más información en [esta página](../../automation/campaign-opt/pressure-rules.md)