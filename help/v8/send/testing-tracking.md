---
title: Prueba del seguimiento de mensajes
description: Obtenga información sobre cómo probar el seguimiento de mensajes antes de realizar envíos
feature: Monitoring
role: User
level: Beginner
exl-id: 16ad36b7-c13e-4b77-86ca-41c9ef174172
source-git-commit: edbe7ab49a628436dfb4d27ae17122917d7371e9
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 3%

---

# Prueba del seguimiento de mensajes {#testing-tracking}

Antes de realizar el envío a toda la audiencia, es esencial probar la funcionalidad de seguimiento para asegurarse de que todos los vínculos funcionan correctamente y de que los datos de seguimiento se capturan correctamente. Este proceso de verificación le ayuda a identificar y corregir cualquier problema de seguimiento antes de que la campaña se ponga en marcha, lo que evita posibles problemas con las redirecciones de vínculos, el seguimiento de la carga de píxeles o la recopilación de datos.

El seguimiento de pruebas le permite:

* Compruebe que todos los vínculos del mensaje se rastrean correctamente y que se redirigen correctamente
* Confirme que el vínculo de la página espejo funciona y se rastrea
* Asegúrese de que los píxeles de seguimiento se cargan correctamente para el seguimiento de aperturas
* Compruebe que los parámetros personalizados en las direcciones URL se capturan con precisión
* Validar que el flujo de trabajo técnico de seguimiento procese los datos correctamente.

Puede probar el seguimiento en páginas espejo, &quot;logs&quot; de correo electrónico y vínculos siguiendo los pasos a continuación:

## Paso 1: Creación de una entrega de prueba {#create-test-delivery}

1. Cree un nuevo envío de correo electrónico que se utilice para realizar pruebas. [Aprenda a crear un envío](../start/create-message.md)
1. Diseñe el contenido del correo electrónico con los vínculos que desee rastrear. [Más información sobre el diseño del contenido del correo electrónico](defining-the-email-content.md)
1. Añada un bloque de personalización de página espejo en el contenido del correo electrónico. [Más información sobre los bloques de personalización](personalization-blocks.md)

   ![](assets/mirror-page-insert.png)

1. Especifique el usuario que debe recibir el correo electrónico. Dado que este usuario debe abrir el correo electrónico y hacer clic en los vínculos que contiene, asegúrese de seleccionar una dirección de destinatario de la prueba que usted controle. [Más información sobre los perfiles de prueba](../audiences/test-profiles.md)

## Paso 2: Envío de la entrega de prueba {#send-test}

1. Compruebe que el seguimiento esté habilitado en la configuración de envío:
   * Abra **[!UICONTROL Properties]** de su envío
   * Ir a la sección **[!UICONTROL Tracking & Images]**
   * Asegúrese de que **[!UICONTROL Activate tracking]** esté marcado
   * Asegúrese de que **[!UICONTROL Opens tracking]** esté marcado si desea rastrear aperturas

   ![](assets/s_ncs_user_email_del_tracking_param.png)

[Más información acerca de las opciones de seguimiento de URL](url-tracking.md)

1. Realice la entrega al destinatario de la prueba. [Más información sobre los envíos](configure-and-send.md)

## Paso 3: Verificar la funcionalidad de seguimiento {#verify-tracking}

1. Una vez que haya recibido el correo electrónico, ábralo y haga clic en el vínculo de la página espejo. [Más información sobre las páginas espejo](mirror-page.md)
1. Haga clic en varios vínculos del correo electrónico para generar los datos de seguimiento.
1. Una vez que se le haya redirigido correctamente a la página espejo, obtenga acceso a la carpeta **[!UICONTROL Administration > Production > Technical workflows]**. [Más información sobre los flujos de trabajo](../config/workflows.md)
1. Abra el flujo de trabajo **[!UICONTROL Tracking]**.
1. Inicie el flujo de trabajo o haga clic con el botón derecho en la actividad **[!UICONTROL Scheduler]** y seleccione **[!UICONTROL Execute pending task now]**.
1. Espere unos 30 segundos para que el flujo de trabajo procese los registros de seguimiento.
1. Seleccione la ficha **[!UICONTROL Audit]** del flujo de trabajo. Asegúrese de que se encuentre al menos un registro de seguimiento. Haga clic en **[!UICONTROL Refresh]** si no ve ningún registro nuevo.

1. Compruebe los registros de seguimiento en el envío:
   * Volver a su envío
   * Seleccione la ficha **[!UICONTROL Tracking]**
   * Compruebe que la lista de registros de seguimiento aparece con las direcciones URL donde se hizo clic y otros eventos de seguimiento

   ![](assets/s_ncs_user_delivery_tracking_tab.png)

## Paso 4: Compruebe la pestaña de seguimiento de destinatarios {#check-recipient-tracking}

1. Vaya a la página de perfil del destinatario que utilizó para la prueba. [Más información sobre la visualización de perfiles](../audiences/view-profiles.md)
   * La página de perfil del destinatario se encuentra en la carpeta **[!UICONTROL Profiles and Targets > Recipients]** de forma predeterminada.

1. Seleccione la pestaña **[!UICONTROL Tracking]** [Más información sobre los registros de seguimiento](tracking-logs.md)

   ![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

1. Compruebe que los registros de seguimiento aparecen con:
   * El valor **[!UICONTROL Mirror Page]** en la columna **[!UICONTROL Type]**
   * **[!UICONTROL Open]** valores en la columna **[!UICONTROL Type]** para aperturas de correo electrónico
   * **[!UICONTROL Email click]** valores en la columna **[!UICONTROL Type]** para clics en vínculos

## Prueba de seguimiento de resolución de problemas {#troubleshooting-tracking-test}

Si no aparecen los registros de seguimiento:

1. **Compruebe la configuración de envío**: Vaya al envío y acceda a su **[!UICONTROL Properties]** para asegurarse de que las opciones **[!UICONTROL Activate tracking]** y **[!UICONTROL Opens tracking]** estén seleccionadas. [Más información acerca de las opciones de seguimiento de URL](url-tracking.md)

1. **Compruebe el flujo de trabajo de seguimiento**: asegúrese de que el flujo de trabajo técnico de **[!UICONTROL Tracking]** se está ejecutando sin errores. [Obtenga información acerca de la solución de problemas del flujo de trabajo de seguimiento](tracking-logs.md#check-tracking-workflow)

1. **Comprobar formato de dirección URL**: compruebe que las direcciones URL tengan el formato correcto y estén delimitadas por delimitadores. [Más información acerca de la configuración de vínculos rastreados](tracked-links.md)

1. **Revisar el comportamiento del cliente de correo electrónico**: Algunos clientes de correo electrónico pueden bloquear los píxeles de seguimiento o modificar los vínculos. Pruebe con diferentes clientes de correo electrónico. [Más información sobre las prácticas recomendadas de entrega](../start/delivery-best-practices.md)

1. **Esperar al procesamiento**: El flujo de trabajo de seguimiento se ejecuta cada hora de forma predeterminada. Si lo almacena en déclencheur manualmente, deje tiempo suficiente para el procesamiento antes de comprobar los resultados. [Más información sobre los registros de seguimiento](tracking-logs.md)

## Temas relacionados {#related-topics}

* [Obtenga información sobre cómo configurar los vínculos rastreados](tracked-links.md)
* [Obtenga información sobre cómo acceder a los registros de seguimiento](tracking-logs.md)
* [Comprensión de los informes de seguimiento](../reporting/delivery-reports.md#tracking-indicators)

