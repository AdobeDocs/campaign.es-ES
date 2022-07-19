---
product: campaign
title: Introducción a las tipologías de campaña
description: Obtenga información sobre cómo configurar e implementar tipologías de campaña
feature: Typology Rules
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 69%

---

# Introducción a las tipologías de campaña{#about-campaign-typologies}

Campaign Optimization (optimización de la campaña) es el módulo de Adobe Campaign que permite controlar, filtrar y monitorizar las entregas. Para evitar conflictos entre campañas, Adobe Campaign puede probar distintas combinaciones mediante la aplicación de reglas de restricción específicas. Esto garantiza que los mensajes enviados respondan de la mejor forma a las necesidades y expectativas de los clientes, de acuerdo con las políticas de comunicación de la compañía.

![](assets/do-not-localize/how-to-video.png) [Descubra esta función en vídeo](#typologies-video)

>[!NOTE]
>
>Según la oferta, Campaign Optimization puede estar incluido o ser un complemento. Compruebe el acuerdo de licencia.

## Reglas de tipología y tipologías {#typology-rules}

Con Adobe Campaign puede diseñar y aplicar cuatro tipos **reglas de tipología**:

* Reglas de **filtrado**, que permiten excluir parte del objetivo según los criterios. [Más información](filtering-rules.md).
* Reglas de **presión**, que permiten controlar la fatiga de marketing. [Más información](pressure-rules.md).
* Reglas de **capacidad** que permiten limitar las cargas para garantizar condiciones de procesamiento óptimas. [Más información](consistency-rules.md#controlling-capacity).
* Reglas de **control** que permiten comprobar la validez de los mensajes antes de enviarlos. [Más información](control-rules.md).

Una vez creadas, las reglas de tipología se agrupan en campañas **tipologías** a los que se hace referencia en los envíos. [Más información](#apply-typologies).

Una tipología de campaña puede contener varias reglas de tipología, pero una entrega solo puede hacer referencia a una tipología.

Las reglas y tipologías de tipología integradas están disponibles en la **[!UICONTROL Administration > Campaign management > Typology management]** del explorador de Campaign.

Para cada tipología, la variable **[!UICONTROL Rules]** permite añadir, eliminar o ver las reglas de tipología que se pueden aplicar.

![](assets/campaign_opt_rules_tab.png)

## Pasos clave para aplicar tipologías {#apply-typologies}

A continuación se enumeran los pasos clave para crear y aplicar una tipología a las entregas:

1. Cree reglas de tipología y una tipología para hacer referencia a ellas.
Los pasos detallados se enumeran en la siguiente sección:
   * [Reglas de presión](pressure-rules.md)
   * [Reglas de filtrado](filtering-rules.md)
   * [Reglas de capacidad](consistency-rules.md)
   * [Reglas de control](control-rules.md)

1. Configure su envío para utilizar la tipología creada. [Más información](apply-rules.md#apply-a-typology-to-a-delivery).
1. Pruebe y controle el comportamiento a través de simulaciones de campañas. [Más información](campaign-simulations.md).

Durante la preparación de la entrega, los destinatarios se excluyen cuando se cumple el criterio. Puede comprobar los registros para controlar las exclusiones.

En [esta página](pressure-rules.md#use-cases-on-pressure-rules) se encuentran disponibles ejemplos de uso de las reglas de tipología de presión.

## Tutoriales en vídeo {#typologies-video}

### Configuración de la administración de la fatiga mediante reglas de tipología

En este vídeo se explica cómo implementar la administración de la fatiga en Adobe Campaign mediante reglas de tipología.

>[!VIDEO](https://video.tv.adobe.com/v/25090?quality=12)

### Configuración de la gestión de la fatiga mediante filtros predefinidos

La administración de la fatiga controla la frecuencia y la cantidad de mensajes para evitar el exceso de solicitudes de destinatarios. Si no tiene el módulo de optimización de la campaña en la instancia de campaña, puede configurar un filtro predefinido que filtrará la población de destinatarios por el número de mensajes recibidos.
En este vídeo se explica cómo implementar la administración de fatiga en Adobe Campaign mediante filtros.

>[!VIDEO](https://video.tv.adobe.com/v/25091?quality=12)


