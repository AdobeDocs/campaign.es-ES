---
solution: Campaign v8
product: Adobe Campaign
title: Cambio de la tabla de destinatarios predeterminada
description: Aprenda a utilizar una tabla de destinatarios personalizada
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 2%

---

# Usar una tabla de destinatarios personalizada{#gs-ac-custom-recipient}

Adobe Campaign incluye una tabla de perfiles integrada: **nmsRecipient**. Esta tabla tiene una serie de campos predefinidos y tablas que se pueden ampliar fácilmente. Obtenga más información sobre esta tabla en [esta página](datamodel.md#ootb-profiles).

La extensión de tabla integrada ofrece flexibilidad, pero no permite eliminar algunos campos o vínculos que no se utilizan. Como consecuencia, el uso de una tabla de destinatarios personalizada puede ser una buena opción cuando el modelo de datos difiere drásticamente de la estructura de la tabla de destinatarios integrada en Campaign o si tiene un gran número de perfiles.  Sin embargo, este método requiere ciertas precauciones al implementarlo.

Esta funcionalidad permite a Adobe Campaign procesar datos desde una base de datos externa: estos datos se utilizan como un conjunto de perfiles para las entregas. Implementar este proceso implica limitaciones, como:

* Sin flujo de actualización de la base de datos de Campaign Cloud: los datos de esta tabla se pueden actualizar directamente a través del motor de base de datos que lo aloja.
* Los procesos que funcionan en la base de datos existente deben ser estables.
* Uso de una base de datos de perfiles con una estructura no estándar: posibilidad de enviar a perfiles guardados en varias tablas con varias estructuras, utilizando una sola instancia.

En esta sección se describen los puntos clave para asignar las tablas existentes en Adobe Campaign y los ajustes de configuración que se aplican para ejecutar entregas en función de cualquier tabla. También describe cómo diseñar interfaces de consulta para usuarios finales.

>[!CAUTION]
>
>La personalización de Adobe Campaign está reservada para usuarios expertos. Requiere experiencia en el diseño de esquemas y formularios de entrada.

