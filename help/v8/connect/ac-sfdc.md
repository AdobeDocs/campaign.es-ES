---
title: Trabajo con Campaign y SFDC
description: Aprenda a trabajar con Campaign y Salesforce.com
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 35%

---

# Trabajo con Campaign y SFDC{#crm-sfdc}

Obtenga información sobre cómo configurar el conector CRM de Campaign para conectar Campaign v8 a **Salesforce.com**.

Una vez completada la configuración, la sincronización de datos entre sistemas se realiza mediante una actividad de flujo de trabajo dedicada. [Más información](crm-data-sync.md).

>[!NOTE]
>
>Las versiones de SFDC compatibles se detallan en Campaign [Matriz de compatibilidad](../start/compatibility-matrix.md).


Siga los pasos a continuación para configurar una cuenta externa dedicada para importar y exportar datos de Salesforce a Adobe Campaign.

## Creación de la conexión{#new-sfdc-external-account}

En primer lugar, debe crear la cuenta externa de Salesforce.

1. Examine la **[!UICONTROL Administration > Platform > External accounts]** del explorador de Campaign y cree una cuenta externa.
1. Select **[!UICONTROL Salesforce.com]** cuenta externa en **Tipo** para obtener más información.
1. Introduzca la configuración para activar la conexión.

   ![](assets/sfdc-external-account.png)

   Para configurar la cuenta externa de Salesforce CRM para que funcione con Adobe Campaign, proporcione los siguientes detalles:

   * Introduzca su inicio de sesión de Salesforce en la **[!UICONTROL Account]** campo .
   * Escriba la contraseña de Salesforce.
   * Puede ignorar el **[!UICONTROL Client identifier]** campo .
   * Copiar/pegar Salesforce **[!UICONTROL Security token]**
   * Seleccione su **[!UICONTROL API version]**. Las versiones de API de SFDC compatibles se enumeran en Campaign [Matriz de compatibilidad](../start/compatibility-matrix.md).

1. Seleccione el **Habilitar** para activar la cuenta en Campaign.

>[!NOTE]
>
>Para aprobar la configuración, debe cerrar la sesión y volver a iniciarla en la consola de Adobe Campaign.

## Seleccionar tablas para sincronizar{#sfdc-create-tables}

Ahora puede configurar tablas para sincronizar.

1. Haga clic en el **[!UICONTROL Salesforce CRM configuration wizard...]**.
1. Seleccione las tablas que desea sincronizar e inicie el proceso.
1. Compruebe el esquema generado en Adobe Campaign en el nodo **[!UICONTROL Administration > Configuration > Data schemas]**.

   Ejemplo de **Salesforce** esquema importado en Campaign:

   ![](assets/sfdc-schemas.png)

## Sincronice las enumeraciones{#sfdc-enum-sync}

Una vez creado el esquema, puede sincronizar las enumeraciones automáticamente con Adobe Campaign a través de Salesforce.

1. Abra el asistente desde el  **[!UICONTROL Synchronizing enumerations...]** vínculo.
1. Seleccione la enumeración de Adobe Campaign que coincida con la enumeración de Salesforce.
Puede reemplazar todos los valores de una enumeración de Adobe Campaign con los del CRM: para hacerlo, seleccione **[!UICONTROL Yes]** en la columna **[!UICONTROL Replace]**.

   ![](assets/sfdc-enum.png)

1. Haga clic en **[!UICONTROL Next]** y luego **[!UICONTROL Start]** para comenzar a importar las enumeraciones.

1. Examine la **[!UICONTROL Administration > Platform > Enumerations]** para comprobar los valores importados.


Adobe Campaign y Salesforce.com ya están conectados. Puede configurar la sincronización de datos entre los dos sistemas.

Para sincronizar datos entre los datos de Adobe Campaign y SFDC, cree un flujo de trabajo y use el **[!UICONTROL CRM connector]** actividad.

Obtenga más información acerca de la sincronización de datos [en esta página](crm-data-sync.md).
