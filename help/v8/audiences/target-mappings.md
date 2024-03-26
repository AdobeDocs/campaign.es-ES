---
title: Trabajar con asignaciones de destino
description: Aprenda a utilizar y crear asignaciones de destino
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
exl-id: 5256fc15-1878-4064-9c75-7876a3826b83
source-git-commit: 4c787abbf9b13c08263e602930bc532d73e08a5a
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 38%

---

# Trabajar con asignaciones de destino{#gs-target-mappings}

De forma predeterminada, las plantillas de envío de correo electrónico y SMS están segmentadas **[!UICONTROL Recipients]**. El destino de mapeo utiliza los campos de la tabla **nms:recipient**.

Para las notificaciones push, la asignación de destino predeterminada es **Aplicaciones del suscriptor (nms:appSubscriptionRcp)**, que está vinculado a la tabla de destinatarios.

Puede utilizar otras asignaciones de destino para los envíos o crear una nueva asignación de destino.

## Asignaciones de destino integradas {#ootb-mappings}

Adobe Campaign viene con las siguientes asignaciones de destino integradas:

| Nombre | Usar para | Esquema |
|---|---|---|
| Destinatarios | Envío a destinatarios (tabla de destinatarios integrada) | nms:recipient |
| Visitantes | Envío a los visitantes cuyos perfiles se hayan recopilado mediante recomendación (marketing viral) por ejemplo. | mns:visitor |
| Suscripciones | Envío a destinatarios suscritos a un servicio de información como un boletín informativo | nms:subscription |
| Suscripciones de visitantes | Envío a los visitantes que están suscritos a un servicio de información | nms:visitorSub |
| Operadores | Envío a los operadores de Adobe Campaign | nms:operator |
| Archivo externo | Envío a través de un archivo que contiene toda la información necesaria para la entrega | No hay ningún esquema vinculado, no se ha introducido ningún destino |
| Aplicaciones del suscriptor | Envío a destinatarios suscritos a una aplicación | nms:appSubscriptionRcp |


## Creación de una asignación de destino {#new-mapping}

También puede crear una asignación de destino. Es posible que tenga que agregar una asignación de destino personalizada, por ejemplo, si:

* se utiliza una tabla de destinatarios personalizada,
* puede configurar una dimensión de filtrado diferente de la dimensión de segmentación integrada en la pantalla de asignación de destino.

Obtenga más información sobre las tablas de destinatarios personalizadas en [esta página](../dev/custom-recipient.md).

El asistente de creación de asignaciones de destino de Adobe Campaign le ayuda a crear todos los esquemas necesarios para utilizar la asignación de destino personalizada.

1. Navegar a **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** desde el explorador de Adobe Campaign.

1. Cree una nueva asignación de destino y seleccione el esquema personalizado como dimensión de segmentación.

   ![](assets/new-target-mapping.png)


1. Indique los campos donde se almacena la información de perfil: apellidos, nombre, correo electrónico, dirección, etc.

   ![](assets/wf_new_mapping_define_join.png)

1. Especifique los parámetros para el almacenamiento de información, incluido el sufijo de los esquemas de extensión para que se puedan identificar fácilmente.

   ![](assets/wf_new_mapping_define_names.png)

   Puede elegir si desea almacenar las exclusiones (**excludelog**), con mensajes (**broadlog**) o en una tabla independiente.

   También puede elegir si desea administrar el seguimiento para esta asignación de envíos (**trackinglog**).

1. A continuación, seleccione las extensiones que se van a tener en cuenta. El tipo de extensión depende de la configuración de Campaign y de los complementos.

   ![](assets/wf_new_mapping_define_extensions.png)

   Haga clic en el botón **[!UICONTROL Save]** para iniciar la creación de la asignación de entrega: todas las tablas vinculadas se crean automáticamente en función de los parámetros seleccionados.
