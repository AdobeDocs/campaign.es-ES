---
product: campaign
title: Aplicación de reglas de tipología
description: Aprenda a aplicar reglas de tipología
feature: Typology Rules
exl-id: 4ec3bbe1-fc4c-4b1e-989c-f4dcf8ee8d5e
source-git-commit: a8568e0c1e9af11b533b7d435691dc12cc0a2485
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 85%

---

# Aplicación de reglas de tipología{#applying-rules}

## Aplicación de una tipología a una entrega {#apply-a-typology-to-a-delivery}

Para aplicar las reglas de tipología creadas, asócielas a una tipología y, a continuación, haga referencia a esta tipología en su envío.

Para realizar esto, siga los pasos a continuación:

1. Cree una tipología de campaña.

   Se accede a las tipologías a través de la variable **[!UICONTROL Administration > Campaign Management > Typology management]** > **[!UICONTROL Typologies]** del explorador de Campaign.

1. Vaya a la pestaña **[!UICONTROL Rules]**, haga clic en el botón **[!UICONTROL Add]** y seleccione las reglas que desea aplicar con esta tipología.

   ![](assets/campaign_opt_pressure_sample_1_6.png)

1. Guarde la tipología: se añade a la lista de tipologías existentes.
1. Abra la entrega al que desee aplicar las reglas.
1. Vaya a las propiedades de entrega y abra **[!UICONTROL Typology]** pestaña.
1. Seleccione la tipología en la lista desplegable.

   ![](assets/campaign_opt_pressure_sample_1_7.png)

   >[!NOTE]
   >
   >La tipología se puede definir en la plantilla de envíos para que se aplique automáticamente a todas las entregas creadas con esta plantilla.

## Definición de condiciones de aplicación {#define-application-conditions}

Puede restringir el campo de aplicación de una regla según sus necesidades (excepto para reglas de control).

Puede configurar las reglas de tipología para que influyan solo sobre algunos envíos a los que están vinculados o ciertos destinatarios a los que va dirigidos una entrega.

Para definir las condiciones de aplicación de una regla, en la pestaña **[!UICONTROL Edit the rule application conditions...]**, haga clic en la pestaña **[!UICONTROL General]**.

A continuación, utilice el editor de consultas para definir las condiciones de filtrado. En el siguiente ejemplo, la regla de capacidad respeta solo los envíos con la palabra “oferta” en su etiqueta o los envíos creados antes del 1 de abril de 2013.

![](assets/campaign_opt_create_capacity_criterion.png)

>[!NOTE]
>
>En el caso de las reglas de filtrado, puede seleccionar la condición de aplicación de los criterios de filtrado: pueden depender de la entrega o de la descripción de la entrega. [Más información](filtering-rules.md#condition-a-filtering-rule).

## Ajuste de frecuencia de cálculo {#adjust-calculation-frequency}

La mediación se vuelve a ejecutar automáticamente cada noche a través del flujo de trabajo de limpieza de la base de datos. Sin embargo, los valores se pueden guardar más allá de este periodo.

De hecho, algunos cálculos utilizan valores que no cambian diariamente. Por lo tanto, sería irrelevante recalcular los datos todos los días y sobrecargar la base de datos para nada. Por ejemplo, si un proceso enriquece la base de datos de marketing con puntuaciones de tendencia de los clientes y adquiere información cada semana, no es necesario recalcular los datos basados en estos valores todos los días.

Para hacerlo, el campo **[!UICONTROL Frequency]** en la pestaña **[!UICONTROL General]** permite definir un periodo máximo durante el cual se guarda el objetivo. De forma predeterminada, el valor **0** indica que el cálculo sigue siendo válido hasta la siguiente ejecución de mediación diaria.

Para guardar los resultados más allá de este periodo, introduzca un valor mayor que 12 en el campo **[!UICONTROL Frequency]**: una vez transcurrido este periodo, todas las reglas se vuelven a aplicar.

La opción **[!UICONTROL Re-apply the rule at the start of personalization]** permite aplicar la regla automáticamente durante la fase de personalización, incluso si el periodo indicado en el campo **[!UICONTROL Frequency]** aún es válido.

## Selección de la fase de la aplicación de regla {#selecting-the-rule-application-phase}

Las reglas de tipología se aplican en una secuencia específica durante las fases de objetivo, análisis y personalización de los envíos correspondientes.

### Orden de ejecución {#execution-order}

En el modo de operación estándar, las reglas se aplican en la siguiente secuencia:

1. Reglas de control, si se aplican al principio del objetivo.
1. Reglas de filtrado:

   * Reglas de aplicación nativas para la clasificación de direcciones: dirección definida/dirección no verificada/dirección en lista de bloqueados/dirección en cuarentena/calidad de la dirección.
   * Reglas de filtrado definidas por el usuario.
   * Deduplicación sobre la dirección o el identificador (se aplica si es necesario).

1. Reglas de presión.
1. Reglas de capacidad.
1. Reglas de control, si se aplican al final del objetivo.
1. Reglas de control, si se aplican al inicio de la personalización. Si las reglas de usuario (filtrado/presión/capacidad) han caducado y necesitan ser recalculadas, se aplican durante este paso.
1. Reglas de control, si se aplican al final de la personalización.

>[!NOTE]
>
>Si trabaja con el módulo Campaign Interaction, las reglas de elegibilidad se aplican al mismo tiempo que las reglas de filtrado (para ofertas encontradas en las descripciones de entrega) o durante la fase de personalización, durante la llamada al motor de ofertas.

Puede adaptar la secuencia de ejecución de las reglas que tienen el mismo tipo utilizando el campo correspondiente en la pestaña **[!UICONTROL General]** de la regla. Cuando se ejecutan varias reglas durante la misma fase de procesamiento de mensajes, se puede configurar su secuencia de ejecución en el campo **[!UICONTROL Execution sequence]**.

Por ejemplo, una regla de presión con un orden de ejecución de 20 se ejecuta antes que una regla de presión con un orden de ejecución de 30.

### Reglas de control {#control-rules}

Para **[!UICONTROL Control]** En las reglas de, puede decidir en qué punto del ciclo de vida de la entrega se aplica la regla: antes o después del objetivo, al comienzo de la personalización, al final del análisis. En la pestaña **[!UICONTROL Phase]** de la regla de tipología, seleccione el valor que se deba aplicar en la lista desplegable del campo **[!UICONTROL General]**.

![](assets/campaign_opt_define_control_phase.png)

Los valores posibles son:

* **[!UICONTROL At the start of targeting]**

  Para evitar que el paso de personalización se ejecute en caso de errores, puede aplicar la regla de control aquí.

* **[!UICONTROL After targeting]**

  Si necesita conocer el volumen del destino para aplicar la regla de control, seleccione esta fase.

  Por ejemplo, la regla de control **[!UICONTROL Check proof size]** se aplica después de cada fase de objetivos: esta regla evita la personalización de los mensajes si hay demasiados destinatarios de prueba.

* **[!UICONTROL At the start of personalization]**

  Esta fase debe estar seleccionada si el control afecta a la aprobación de la personalización de mensajes. La personalización del mensaje se lleva a cabo durante la fase de análisis.

* **[!UICONTROL At the end of the analysis]**

  Cuando una comprobación requiera que se complete la personalización de mensajes, seleccione esta fase.

## Configuraciones adicionales {#additional-configurations}

### Control del tráfico SMTP saliente {#control-outgoing-smtp-traffic}

Como opción, puede utilizar el campo **[!UICONTROL Managing affinities with IP addresses]** para relacionar envíos al servidor de entrega (MTA) con esta afinidad. Esto permite limitar el número de correos electrónicos para envíos específicos hacia equipos o direcciones de salida.

![](assets/campaign_opt_select_ip_affinity.png)

>[!NOTE]
>
>La administración de la afinidad no se aplica a tipologías de **[!UICONTROL Filtering]**.

<!--
>Affinities are defined in the instance configuration file, on the Adobe Campaign server. For more on this, refer to [this section](../../installation/using/about-initial-configuration.md).-->

### Optimización de la campaña y marketing distribuido {#campaign-optimization-and-distributed-marketing}

La pestaña **[!UICONTROL Distributed Marketing]** permite definir la reasignación de tipologías y las reglas que se aplican cuando una campaña compartida se ha solicitado o está reservada. Las reglas o tipologías definidas para una entidad local (vinculadas a las reglas o tipologías definidas a nivel de la entidad central) sustituyen a las reglas o tipologías vinculadas a la entidad central. La reasignación le permite adaptar las reglas de la entidad central a las entidades locales que encargan la campaña.

![](assets/simu_campaign_opti_distrib_mkg.png)

>[!NOTE]
>
>En las tipologías y en las reglas de tipologías, se añade la pestaña **[!UICONTROL Distributed Marketing]** si la licencia incluye esta opción: compruebe el contrato de licencia.\
>Para obtener más información sobre marketing distribuido, consulte [esta sección](../distributed-marketing/about-distributed-marketing.md).
