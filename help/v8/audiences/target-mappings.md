---
title: Trabajar con asignaciones de destino
description: Aprenda a utilizar y crear asignaciones de destino
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
exl-id: 5256fc15-1878-4064-9c75-7876a3826b83
TQID: https://experienceleague.adobe.com/ArJJi775HkzlpPOu-SoKg8UTcYTperTC1ySmXrHHpJg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 376
ht-degree: 38%

---

# Trabajar con asignaciones de destino{#gs-target-mappings}

De manera predeterminada, las plantillas de envío de correo electrónico y SMS tienen como destino **[!UICONTROL Recipients]**. Por consiguiente, la asignación de destinatario utiliza los campos de la tabla **nms:recipient**.

Para las notificaciones push, la asignación de destino predeterminada es **Aplicaciones de suscriptor (nms:appSubscriptionRcp)**, que está vinculada a la tabla de destinatarios.

Puede utilizar otras asignaciones de destino para los envíos o crear una nueva asignación de destino.

## Asignaciones de destino integradas {#ootb-mappings}

Adobe Campaign viene con las siguientes asignaciones de destino integradas:

| Name | Usar para | Esquema |
|---|---|---|
| Recipients | Envío a destinatarios (tabla de destinatarios integrada) | nms:recipient |
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

Obtenga más información acerca de las tablas de destinatarios personalizadas en [esta página](../dev/custom-recipient.md).

El asistente de creación de asignaciones de destino de Adobe Campaign le ayuda a crear todos los esquemas necesarios para utilizar la asignación de destino personalizada.

1. Vaya a **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** desde el explorador de Adobe Campaign.

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
