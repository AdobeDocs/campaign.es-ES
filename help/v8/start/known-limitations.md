---
product: Adobe Campaign
title: Limitaciones conocidas de Campaign v8
description: Limitaciones conocidas
feature: Información general
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: cf00895f988514fc029d0060d7404bdef0c8b30e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 87%

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
* Adobe Campaign v8 no admite rendimiento ampliado en aplicaciones web y API. En caso de necesidades específicas, póngase en contacto con el Adobe para obtener ayuda.


