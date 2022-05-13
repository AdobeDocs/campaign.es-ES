---
title: Limitaciones conocidas de Campaign v8
description: Limitaciones conocidas
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 72%

---

# Limitaciones conocidas

Las limitaciones conocidas identifican capacidades, arquitectura o procesos que no son compatibles con esta versión del producto o que no interactúan correctamente con él. Revise detenidamente estas limitaciones.

En Adobe Campaign v8, existen las siguientes limitaciones:

* Adobe Campaign v8 no está disponible para implementaciones locales/híbridas; solo se presenta como Cloud Service administrado por Adobe.
* Los clientes existentes no pueden migrar de un entorno de Adobe Campaign existente a Adobe Campaign v8
* [](../architecture/enterprise-deployment.md)
* Las capacidades enumeradas [en esta sección](capability-matrix.md#gs-unavailable-features) no están disponibles en la versión actual de Campaign v8
* Algunas funciones no disponibles o eliminadas siguen estando visibles en la interfaz de usuario
* [](../architecture/enterprise-deployment.md) Las solicitudes se procesan cada hora a través de un flujo de trabajo técnico específico. [Más información](../architecture/replication.md#tech-wf)
* Los usuarios finales deben gestionar manualmente los duplicados. [Más información](../architecture/keys.md)
* Adobe Campaign v8 no admite rendimiento ampliado en aplicaciones web y API. En caso de tener necesidades específicas, póngase en contacto con Adobe para obtener ayuda.
* Adobe Campaign Campaign Optimization module does not take into account scheduled deliveries in pressure typology rules. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=es#setting-the-period).