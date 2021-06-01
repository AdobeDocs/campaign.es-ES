---
product: Adobe Campaign
title: Limitaciones conocidas de Campaign v8
description: Limitaciones conocidas
feature: Información general
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 1%

---

# Limitaciones conocidas

Las limitaciones conocidas identifican capacidades, arquitectura o procesos que no son compatibles con esta versión del producto o que no interactúan correctamente con él. Revise detenidamente estas limitaciones.

Para Adobe Campaign v8, existen las siguientes limitaciones:

* Adobe Campaign v8 no está disponible para implementaciones locales/híbridas; solo se presenta como Cloud Service administrado por Adobe.
* Los clientes existentes no pueden migrar de un entorno de Adobe Campaign existente a Adobe Campaign v8
* Sin replicación de datos bidireccional: la replicación solo se produce desde la base de datos local de Campaign a la base de datos de Cloud
* Las capacidades enumeradas [en esta sección](capability-matrix.md#gs-unavailable-features) no están disponibles en la versión actual de Campaign v8
* Algunas funciones no disponibles o eliminadas siguen estando visibles en la interfaz de usuario
* Los mecanismos de suscripción (inclusión) y baja (exclusión), y el registro móvil son procesos asincrónicos. Las solicitudes se procesan cada hora a través de un flujo de trabajo técnico específico. [Obtenga más información](../config/replication.md#tech-wf)
* Administración de ID - duplicados - para confirmar + detalles
* LINE: para confirmar más detalles
* Latencia: para confirmar + detalles
