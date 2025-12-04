---
title: Acceder a registros de seguimiento
description: Obtenga información sobre cómo acceder e interpretar los registros de seguimiento
feature: Monitoring
role: User
level: Beginner
exl-id: df494786-5950-4646-aa9c-4dde45845057
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 19%

---

# Acceder a registros de seguimiento {#accessing-the-tracking-logs}

Cuando se realiza el envío y el seguimiento está activado, el flujo de trabajo técnico **[!UICONTROL Tracking]** recopila los datos de seguimiento. Se ejecuta cada hora de forma predeterminada.

## Visualización del seguimiento en perfiles de destinatario {#recipient-tracking}

Esta información aparece en la pestaña **[!UICONTROL Tracking]** del perfil de los destinatarios objetivo del envío, como en el siguiente ejemplo:

![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

Esta pestaña muestra todas las direcciones URL rastreadas y seleccionadas por el destinatario, incluidas:

* La URL donde se hizo clic
* La fecha y la hora del clic
* El envío en el que se encontró la dirección URL
* Cualquier otra información de seguimiento relevante

Puede filtrar y ordenar esta información para analizar el comportamiento de los destinatarios e identificar patrones de participación.

## Ver seguimiento en envíos {#delivery-tracking}

También se puede acceder a la información de seguimiento a través de la pestaña **[!UICONTROL Tracking]** de la entrega.

![](assets/s_ncs_user_select_tracking_tab_from_del.png)

Desde esta pestaña, puede ver:

* **[!UICONTROL Tracking statistics]**: proporciona información general sobre aperturas, clics y otros eventos de seguimiento
* **[!UICONTROL URLs and click streams]**: muestra en qué vínculos se hizo clic y cuántas veces
* **[!UICONTROL Hot clicks]**: muestra una representación visual de dónde hicieron clic los destinatarios en el mensaje
* **[!UICONTROL Tracking logs]**: proporciona registros de seguimiento detallados e individuales

## Seguimiento de resolución de problemas {#troubleshooting}

>[!NOTE]
>
>Si no ve la pestaña **[!UICONTROL Tracking]** de un envío, significa que el seguimiento no está activado. Consulte [esta sección](tracked-links.md) para obtener información sobre cómo configurar el seguimiento.

### Compruebe el flujo de trabajo técnico Tracking {#check-tracking-workflow}

El flujo de trabajo técnico de seguimiento debe estar en ejecución para recopilar datos de seguimiento. Puede encontrar el flujo de trabajo técnico de seguimiento en la carpeta **[!UICONTROL Administration > Production > Technical workflows]**.

Para verificar el flujo de trabajo:

1. Abrir el flujo de trabajo **[!UICONTROL Tracking]**
1. Comprobar la última fecha de ejecución
1. Compruebe que no haya errores en los registros del flujo de trabajo

Si el flujo de trabajo no se está ejecutando o tiene errores, póngase en contacto con el administrador del sistema.

## Verificar la recopilación de datos de seguimiento

Después de enviar una entrega con el seguimiento habilitado:

1. Espere a que se ejecute el flujo de trabajo de seguimiento (de forma predeterminada, cada hora)
1. Abra la entrega y vaya a la pestaña **[!UICONTROL Tracking]**
1. Compruebe que aparecen los datos de seguimiento
1. Si no aparece ningún dato, compruebe que:
   * El seguimiento se ha activado en la configuración de envío
   * Se está ejecutando el flujo de trabajo técnico de seguimiento
   * Los destinatarios abrieron el correo electrónico e hicieron clic en los vínculos

## Temas relacionados {#related-topics}

* [Obtenga información sobre cómo configurar los vínculos rastreados](tracked-links.md)
* [Obtenga información sobre cómo probar el seguimiento](testing-tracking.md)
* [Comprensión de los informes de seguimiento](../reporting/delivery-reports.md#tracking-indicators)

