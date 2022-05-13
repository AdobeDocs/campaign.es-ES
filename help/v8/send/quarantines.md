---
title: Quarantine management in Campaign
description: Understand quarantine management in Adobe Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: 1ff06c69a4118afa228522d580dd5caa36a69275
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 38%

---

# Quarantine {#quarantine-management}

Adobe Campaign manages a list of quarantined addresses for online channels (email, SMS, push notification). Some internet access providers automatically consider emails as spam if the rate of invalid addresses is too high. Por lo tanto, la cuarentena le permite evitar ser incluido en la lista de bloqueados de bloqueados por estos proveedores. Además, la cuarentena reduce el coste de entrega de los SMS mediante la exclusión en las entregas de los números de teléfono incorrectos.

When their address or phone number is quarantined, recipients are excluded from the target during delivery analysis: you will not be able to send marketing messages, including automated workflow emails, to those contacts. If those quarantined addresses are also present in lists, they will be excluded when sending to those lists. An email address can be quarantined, for example, when the mailbox is full, if the address does not exist, or if the email server is unavailable.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**************** Del mismo modo, un perfil cuya dirección de correo electrónico se haya puesto en cuarentena puede actualizar su perfil e introducir una nueva, y luego puede volver a recibir entregas. Del mismo modo, si dos perfiles tienen el mismo número de teléfono, ambos se verán afectados si el número está en cuarentena. Las direcciones en cuarentena o los números de teléfono se muestran en los [registros de exclusión](#delivery-quarantines) (para una entrega) o en la [lista de cuarentena](#non-deliverable-bounces) (para toda la plataforma).

**** As a consequence, if a profile on the denylist for the email channel has two email addresses, both addresses will be excluded from delivery. Puede comprobar si un perfil está en la lista de bloqueados de uno o más canales en la sección **[!UICONTROL No longer contact]** de la pestaña **[!UICONTROL General]** del perfil. [Más información](../audiences/view-profiles.md)

>[!NOTE]
>
>**[!UICONTROL Denylisted]** Their profile is updated accordingly.

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## Why is an email, phone or device sent to quarantine {#quarantine-reason}

Adobe Campaign manages quarantine according to the type of delivery failure and its reason. These are assigned during error messages qualification. [](delivery-failures.md)

Two types or errors can be captured:

* ****
* **** [](delivery-failures.md#retries) [Más información](delivery-failures.md#retries).

En la lista de direcciones en cuarentena, el campo **[!UICONTROL Error reason]** indica por qué la dirección seleccionada se envía a cuarentena. [Más información](#identifying-quarantined-addresses-for-the-entire-platform).


If a user qualifies an email as a spam, the message is automatically redirected towards a technical mailbox managed by Adobe. A continuación, la dirección de correo electrónico del usuario se envía automáticamente a la cuarentena con el estado **[!UICONTROL Denylisted]**. Este estado hace referencia únicamente a la dirección y el perfil no se incluye en la lista de bloqueados para que el usuario siga recibiendo mensajes SMS y notificaciones push. [](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#feedback-loops)

>[!NOTE]
>
>La cuarentena en Adobe Campaign distingue entre mayúsculas y minúsculas. Asegúrese de importar las direcciones de correo electrónico en minúsculas para que no se redireccionen más adelante.

## Access quarantined addresses {#access-quarantined-addresses}

Quarantined addresses can be displayed for a specific delivery or for the entire platform.

### Quarantines for a delivery{#delivery-quarantines}

Quarantine addresses are listed during the delivery preparation phase, in the delivery logs of the delivery dashboard.

**[!UICONTROL Delivery summary]**

* El número de direcciones puestas en cuarentena durante el análisis de la entrega.
* El número de direcciones puestas en cuarentena después de la acción de entrega.

### Non deliverable and bounce addresses{#non-deliverable-bounces}

******[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** ************

![](assets/tech-quarantine.png)

>[!NOTE]
>
>Number of quarantines increase with time. Por ejemplo, si se considera que la duración de una dirección de correo electrónico es de tres años y la lista de distribución aumenta en un 50 % cada año, el aumento de la cuarentena se puede calcular de la siguiente manera:
>
>&#42;
>
>&#42;

**[!UICONTROL Non-deliverables and bounces]****** You can filter data for a specific delivery, or customize this report as needed.

[](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=es)

### Dirección de correo en cuarentena {#quarantined-recipient}

Se puede buscar el estado del correo electrónico de cualquier destinatario.

Para ello, seleccione el perfil de destinatario y haga clic en la pestaña **[!UICONTROL Deliveries]**. For all deliveries to that recipient, you can find out whether the address failed, was quarantined during analysis, etc.

**[!UICONTROL Quarantined email address]**

![](assets/quarantine-filter.png)


## Eliminación de una dirección en cuarentena {#remove-a-quarantined-address}

****

Las direcciones se eliminan automáticamente de la lista de cuarentena en los siguientes casos:

* Las direcciones de un estado **[!UICONTROL With errors]** se eliminarán de la lista de cuarentena tras un envío correcto.
* Las direcciones de un estado **[!UICONTROL With errors]** se eliminarán de la lista de cuarentena si el último rebote suave se produjo hace más de 10 días. Para obtener más información sobre la administración de errores leves, consulte [esta sección](#soft-error-management).
* Las direcciones con un estado **[!UICONTROL With errors]** que rebotó con el error **[!UICONTROL Mailbox full]** se eliminarán de la lista de cuarentena pasados 30 días.

A continuación, su estado cambia a **[!UICONTROL Valid]**.

>[!CAUTION]
>
>Los destinatarios con una dirección en un estado **[!UICONTROL Quarantine]** o **[!UICONTROL Denylisted]** nunca se eliminarán, aunque reciban un correo electrónico.

You can also manually remove an address from the quarantine list. To remove an address from quarantine, you can:

* **[!UICONTROL Valid]****[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**

   ![](assets/tech-quarantine-status.png)

* **[!UICONTROL Allowlisted]**

>[!CAUTION]
>
>If you remove an address from quarantine list, you will start again sending to this address again. This can have severe impacts on your deliverability and IP reputation, which could eventually lead to your IP address or sending domain being blocked. Proceda con mucho cuidado cuando considere la posibilidad de eliminar cualquier dirección de la cuarentena. If you need assistance, contact Adobe Support.
