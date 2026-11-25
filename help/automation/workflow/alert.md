---
product: campaign
title: Alerta
description: Alerta
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8fb36117-b126-470a-9c94-eb5c0a4aca1a
TQID: 'https://experienceleague.adobe.com/rTcTh1kbiAHwo1t1wo2SBUEBTR768IkDIP2J4BbFfp8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 71%
---
# Alerta{#alert}



Una actividad de **Alert** envía un mensaje a un grupo de operadores. Funciona del mismo modo que una actividad de aprobación, pero no se espera ninguna respuesta en este caso.

![Actividad de alerta con el grupo de tipo de asignación, el usuario asignado y el título y cuerpo del mensaje.](assets/edit_alerte.png)

Una alerta no es persistente y, por lo tanto, no es visible desde la consola del cliente. Los operadores del grupo asignado deben tener una dirección de correo electrónico completa para recibir la notificación. La configuración de esta actividad es similar a la de una **Approval**. La plantilla de entrega predeterminada utilizada para alertar a los operadores es &#39;alertAssignee&#39;.
