---
title: Limitaciones conocidas de Campaign v8
description: Limitaciones conocidas
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 100%

---

# Limitaciones conocidas

Las limitaciones conocidas identifican capacidades, arquitectura o procesos que no son compatibles con esta versión del producto o que no interactúan correctamente con él. Revise detenidamente estas limitaciones.

En Adobe Campaign v8, existen las siguientes limitaciones:

* Adobe Campaign v8 no está disponible para implementaciones locales/híbridas; solo se presenta como Cloud Service administrado por Adobe.
* Los clientes existentes no pueden migrar de un entorno de Adobe Campaign existente a Adobe Campaign v8
* Sin replicación de datos bidireccional: la replicación solo se produce desde la base de datos local de Campaign a la base de datos en la nube
* Las capacidades enumeradas [en esta sección](capability-matrix.md#gs-unavailable-features) no están disponibles en la versión actual de Campaign v8
* Algunas funciones no disponibles o eliminadas siguen estando visibles en la interfaz de usuario
* Los mecanismos de suscripción (inclusión) y baja (exclusión), y el registro móvil son procesos asíncronos. Las solicitudes se procesan cada hora a través de un flujo de trabajo técnico específico. [Más información](../config/replication.md#tech-wf)
* Los usuarios finales deben gestionar manualmente los duplicados. [Más información](../dev/keys.md)
* Adobe Campaign v8 no admite rendimiento ampliado en aplicaciones web y API. En caso de tener necesidades específicas, póngase en contacto con Adobe para obtener ayuda.
* El módulo de optimización de la campaña de Adobe Campaign no tiene en cuenta los envíos programados en las reglas de tipología de presión. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=es#setting-the-period).