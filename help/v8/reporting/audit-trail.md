---
product: campaign
title: Pista de auditoría
description: Obtenga información sobre cómo monitorizar la instancia con la pista de auditoría de Campaign
feature: Audit Trail, Monitoring, Workflows
source-git-commit: bb74393f0b24fa5b9781eee15c4527daba527192
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 2%

---

# Pista de auditoría{#audit-trail}

El **[!UICONTROL Audit trail]** La funcionalidad de Adobe Campaign ofrece un registro granular de todas las modificaciones realizadas en entidades importantes de su instancia, normalmente las que afectan de forma significativa al funcionamiento sin problemas de la instancia. Funciona como un registro en tiempo real y captura una lista detallada de acciones y eventos a medida que se producen.

>[!NOTE]
>
>Adobe Campaign no audita los cambios realizados en los derechos de usuario, las plantillas, la personalización o las campañas.\
>Solo los administradores de la instancia pueden administrar la pista de auditoría.

+++ Más información sobre las Entidades disponibles de pista de auditoría

* **Pista de auditoría de esquema**: le permite explorar los cambios realizados en los esquemas, así como identificar quién realizó estas modificaciones y cuándo se produjeron.

  Para obtener información detallada sobre los esquemas, consulte [página](../dev/schemas.md).

* **Pista de auditoría de flujo de trabajo** realiza un seguimiento de todas las acciones relacionadas con sus flujos de trabajo, incluidas:

   * Start
   * Pause
   * Stop
   * Restart
   * Limpieza igual al historial de purga de acciones
   * Simular, que es igual a la acción Iniciar en modo de simulación
   * Activación igual a la acción Ejecutar tareas pendientes ahora
   * Interrupción incondicional

  Para obtener más información sobre los flujos de trabajo, consulte [página](../../automation/workflow/about-workflows.md).

  Para obtener más información sobre la monitorización de flujos de trabajo, consulte la [sección dedicada](../../automation/workflow/monitor-workflow-execution.md).

* **Pista de auditoría de opción** le permite comprobar las actividades y las últimas modificaciones realizadas en las opciones.

  Para obtener más información, consulte [página](https://experienceleague.adobe.com/en/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options).

* **Pista de auditoría de envíos** permite comprobar las actividades y las últimas modificaciones realizadas en los envíos.

  Para obtener más información sobre las entregas, consulte [página](../start/create-message.md).

* **Cuenta externa** permite comprobar las modificaciones realizadas en cuentas externas, utilizadas por procesos técnicos como flujos de trabajo técnicos o flujos de trabajo de campañas.

  Para obtener más información sobre la cuenta externa, consulte [página](../config/external-accounts.md).

* **Asignación de envíos** permite supervisar las actividades y las modificaciones recientes realizadas en las asignaciones de envío.

  Para obtener más información sobre la asignación de envíos, consulte esta sección [página](../audiences/target-mappings.md).

* **Aplicación web** permite comprobar las modificaciones realizadas en los formularios web en Campaign V8 utilizados para crear páginas con campos de entrada y selección, y que pueden incluir datos de la base de datos.

  Para obtener más información sobre la aplicación web, consulte [página](../dev/webapps.md).

* **Oferta** permite comprobar las actividades y las últimas modificaciones realizadas en las ofertas.

  Para obtener más información sobre la oferta, consulte esta [página](../interaction/interaction.md).

* **Operador** permite supervisar las actividades y las modificaciones recientes realizadas en los operadores.

  Para obtener más información sobre los operadores, consulte [página](../interaction/interaction-operators.md).

+++

## Acceso a Pista de auditoría {#accessing-audit-trail}

Para acceder a la de **[!UICONTROL Audit trail]**:

1. Acceda a la **[!UICONTROL Explorer]** de la instancia.

1. En el **[!UICONTROL Administration]** menú, seleccione **[!UICONTROL Audit]** entonces **[!UICONTROL Audit Trail]**.

   ![](assets/audit-trail-1.png)

1. El **[!UICONTROL Audit trail]** se abre con la lista de las entidades. Adobe Campaign auditará las acciones de creación, edición y eliminación de las diferentes entidades.

   Seleccione una de las entidades para obtener más información sobre las últimas modificaciones.

1. El **[!UICONTROL Audit entity]** Esta ventana proporciona información más detallada sobre la entidad elegida, como:

   * **[!UICONTROL Type]**: Flujo de trabajo, opciones, envíos o esquemas.
   * **[!UICONTROL Entity]**: Nombre interno de las actividades.
   * **[!UICONTROL Modified by]**: Nombre de usuario de la última persona que modificó esta entidad por última vez.
   * **[!UICONTROL Action]**: última acción realizada en esta entidad, ya sea Creada, Modificada o Eliminada.
   * **[!UICONTROL Modification date]**: Fecha de la última acción realizada en esta entidad.

   ![](assets/audit-trail-2.png)

>[!NOTE]
>
>De forma predeterminada, el período de retención se establece en 180 días para **[!UICONTROL Audit logs]**. Este valor se puede modificar en el asistente de implementación.

## Habilitar/deshabilitar pista de auditoría {#enable-disable-audit-trail}

La pista de auditoría se puede activar o desactivar fácilmente para una actividad específica si, por ejemplo, desea ahorrar espacio en la base de datos.

Para ello:

1. Acceda a la **[!UICONTROL Explorer]** de la instancia.

1. En el **[!UICONTROL Administration]** menú, seleccione **[!UICONTROL Platform]** entonces **[!UICONTROL Options]**.

1. Seleccione una de las siguientes opciones en función de la entidad que desee activar/desactivar:

   * Para Flujo De Trabajo: **[!UICONTROL XtkAudit_Workflows]**
   * Para Esquemas: **[!UICONTROL XtkAudit_DataSchema]**
   * Para Opciones: **[!UICONTROL XtkAudit_Option]**
   * Para Envíos: **[!UICONTROL XtkAudit_Delivery]**
   * Para Cuenta Externa: **[!UICONTROL XtkAudit_ExtAccount]**
   * Para la asignación de envíos: **[!UICONTROL XtkAudit_DeliveryMapping]**
   * Para la aplicación web: **[!UICONTROL XtkAudit_WebApp]**
   * Para la oferta: **[!UICONTROL XtkAudit_Offer]**
   * Para el operador: **[!UICONTROL XtkAudit_Operator]**
   * Para cada entidad: **[!UICONTROL XtkAudit_Enable_All]**

   ![](assets/audit-trail-3.png)

1. Cambie el **[!UICONTROL Value]** a 1 si desea activar la entidad o a 0 si desea desactivarla.

   ![](assets/audit-trail-4.png)

1. Haga clic en **[!UICONTROL Save]**.
