---
solution: Campaign Classic
product: campaign
title: 'Campaign Classic v7: matriz de capacidades de Campaign v8'
description: Comprender las diferencias entre Campaign Classic v7 y Campaign v8
feature: Información general
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
translation-type: tm+mt
source-git-commit: 04859274593f507a0b07f46cf6a65434b6a4bc60
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 3%

---

# Campaign Classic v7: Funcionalidades de Campaign v8{#gs-matrix}


Como usuario Campaign Classic v7 existente, debe esperar cualquier interrupción en la forma en que normalmente &quot;juega&quot; con Adobe Campaign. La mayoría de los cambios no están visibles, excepto los cambios pequeños que aparecen en los pasos de interfaz de usuario y configuración.

Cambios clave:

* Crear segmentos hasta 200 veces más rápido

* Aumentar la velocidad de entrega

* Informes en tiempo real

Como usuario Campaign Classic, tenga en cuenta que la mayoría de las funciones de Campaign Classic v7 están disponibles con Campaign v8, excepto un pequeño conjunto de ellas, que se enumeran en [esta sección](#gs-removed). Otros vendrán en futuras versiones. [Obtenga más información](#gs-unavailable-features)


## Cambios en la configuración del producto

### Campaña y Snowflake {#ac-gs-snowflake}

El almacenamiento en la nube se realiza en el Snowflake: una nueva cuenta externa garantiza la conectividad con la base de datos en la nube. [Más información](#ac-gs-snowflake).

Este es un cambio fundamental en la arquitectura del software. Los datos ahora son remotos: Campaign federa todos los datos, incluidos los perfiles. El proceso de campaña ahora escala de principio a fin, desde Segmentación a Ejecución de entrega: La ingesta de datos, la segmentación, el establecimiento de objetivos, las consultas, la ejecución del envío ahora se ejecutarán en minutos.

Esta nueva versión resuelve todo el desafío de Scaling, manteniendo el mismo nivel de flexibilidad y extensibilidad. El número de perfiles es casi ilimitado y se puede ampliar la retención de datos.

Una nueva cuenta externa **externa** integrada está dedicada a FDA completa. Este es el corazón de la conectividad de la base de datos de Cloud. Recomendamos salir tal cual.

Cualquier esquema/tabla integrado que deba moverse o replicarse en la base de datos de Cloud viene con una extensión de esquema integrada en el espacio de nombres **xxl**. En cuanto a la extensión de esquema, el nuevo espacio de nombres XXL se utilizará para cualquier parte nueva de la configuración de OOTB, como JavaScript, JSSP, etc.

Estas extensiones incluyen cualquier modificación necesaria para mover esquemas integrados de la base de datos local de Campaign a la base de datos de Snowflake Cloud y adaptar su estructura en consecuencia: nuevo UUID, vínculos actualizados, etc.

>[!CAUTION]
>
> Los datos del cliente no se almacenan en la base de datos local de Campaign. Como consecuencia, cualquier tabla personalizada debe crearse en la base de datos de Cloud.


### Duplicación de datos

Un flujo de trabajo técnico específico gestiona la duplicación de tablas que deben estar presentes en ambos lados (base de datos local de Campaign y base de datos de Cloud). Este flujo de trabajo se activa cada hora y depende de una nueva biblioteca JavaScript integrada.

>[!NOTE]
>
> Se han creado varias políticas de replicación en función del tamaño de la tabla (XS, XL, etc.).
> Algunas tablas se replican en tiempo real, ya que otras se realizarán por hora. Algunas tablas tendrán actualizaciones incrementales, ya que otras se actualizarán por completo.


[Más información sobre la replicación de datos](../config/replication.md)

### Administración de ID

Los objetos de Campaign v8 ahora utilizan **Universally Unique ID (UUID)**, lo que implica valores únicos ilimitados para identificar los datos

Tenga en cuenta que este ID se basa en cadenas y no en secuencias.

### Mantenimiento simplificado

Los usuarios de Campaign no necesitan ser expertos en bases de datos: ya no es necesario mantener flujos de trabajo largos ni indexar tablas complejas.

## Funciones no disponibles temporales{#gs-unavailable-features}

Tenga en cuenta que algunas funciones no están disponibles en esta primera versión, pero se lanzarán próximamente, como:

* Administración de recursos de marketing
* Distributed Marketing
* Mensajes entrantes de Administración de ofertas (módulo de interacción)
* Campaign Optimization (Optimización de la campaña)
* Gestor de respuestas
* Marketing social con Twitter
* Modelos de implementación híbridos/locales

## Funciones eliminadas{#gs-removed}

Para alinearse con la nueva arquitectura y el modelo de implementación de Campaign v8, algunas funciones históricas del Campaign Classic v7 no están disponibles en Campaign v8.

* Cupones
* Seguimiento web
* Encuestas
* Marketing social con Facebook
* Conector ACS (oferta principal)
* Base de datos Microsoft SQL
* base de datos de oracle
