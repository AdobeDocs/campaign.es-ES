---
product: campaign
title: Introducción a las tipologías de campaña
description: Obtenga información sobre cómo configurar e implementar tipologías de campaña
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 55%

---

# Introducción a las tipologías de campaña{#about-campaign-typologies}

**Campaign Optimization (optimización de la campaña) es el módulo de Adobe Campaign que permite controlar, filtrar y monitorizar las entregas.** Para evitar conflictos entre campañas, Adobe Campaign puede probar distintas combinaciones mediante la aplicación de reglas de restricción específicas. Esto garantiza que los mensajes enviados respondan de la mejor forma a las necesidades y expectativas de los clientes, de acuerdo con las políticas de comunicación de la compañía.

![](assets/do-not-localize/how-to-video.png) [Descubra esta función en vídeo](#typologies-video)

>[!NOTE]
>
>Según la oferta, Campaign Optimization puede estar incluido o ser un complemento. Compruebe el acuerdo de licencia.

## Reglas de tipología y tipologías {#typology-rules}

De forma predeterminada, Campaign incluye tipologías y reglas de tipología integradas.

Una tipología es un conjunto de reglas de verificación aplicadas a todos los mensajes durante el análisis de la entrega.

Una tipología de campaña puede contener varias reglas de tipología, pero un envío solo puede hacer referencia a una tipología.

Las reglas y tipologías de tipología integradas están disponibles en el **[!UICONTROL Administration > Campaign management > Typology management]** del explorador de Campaign.

Para cada tipología, las variables **[!UICONTROL Rules]** Esta pestaña permite añadir, eliminar o ver las reglas de tipología que se pueden aplicar.

![](assets/campaign_opt_rules_tab.png)

Una vez creadas, las reglas de tipología se agrupan en campaña **tipologías** a los que se hace referencia en las entregas. [Más información](#apply-typologies).


Campaign viene con un conjunto de opciones predeterminadas **Filtrado** y **Control** reglas:

* **Filtrado** Las reglas de se utilizan para excluir parte del destinatario según ciertos criterios. [Más información](filtering-rules.md).
* **Control** Las reglas de permiten comprobar la validez de los mensajes antes de enviarlos. [Más información](control-rules.md).

El complemento Optimización de la campaña proporciona dos tipos adicionales de **reglas de tipología**:

* Reglas de **presión**, que permiten controlar la fatiga de marketing. [Más información](pressure-rules.md).
* Reglas de **capacidad** que permiten limitar las cargas para garantizar condiciones de procesamiento óptimas. [Más información](consistency-rules.md#controlling-capacity).


>[!NOTE]
>
>Si utiliza el complemento **Interacción** módulo para administrar ofertas, también puede crear **Presentación de ofertas** reglas de tipología para controlar el flujo de propuestas de ofertas utilizando reglas de presentación. [Más información](../../v8/interaction/interaction-offer.md#offer-presentation).


## Pasos clave para crear y utilizar tipologías {#apply-typologies}

Para crear y utilizar una tipología para las entregas, siga los pasos a continuación:

1. Cree reglas de tipología y una tipología para hacerles referencia.
Los pasos detallados se enumeran en la siguiente sección:

   * [Reglas de filtrado](filtering-rules.md)
   * [Reglas de control](control-rules.md)
   * [Reglas de presión](pressure-rules.md)
   * [Reglas de capacidad](consistency-rules.md)

1. Configure su envío para utilizar la tipología creada. [Más información](apply-rules.md#apply-a-typology-to-a-delivery).
1. Pruebe y controle el comportamiento a través de simulaciones de campañas. [Más información](campaign-simulations.md).

Durante la preparación de la entrega, los destinatarios se excluyen cuando se cumple el criterio. Puede comprobar los registros para controlar las exclusiones.

En [esta página](pressure-rules.md#use-cases-on-pressure-rules) se encuentran disponibles ejemplos de uso de las reglas de tipología de presión.

## Tutoriales en vídeo {#typologies-video}

### Configuración de la administración de la fatiga mediante reglas de tipología

En este vídeo se explica cómo implementar la administración de la fatiga en Adobe Campaign mediante reglas de tipología.

>[!VIDEO](https://video.tv.adobe.com/v/333787?quality=12)

### Configuración de la administración de la fatiga mediante filtros predefinidos

La administración de la fatiga controla la frecuencia y la cantidad de mensajes para evitar el exceso de solicitudes de destinatarios. Si no tiene el módulo de optimización de la campaña en la instancia de campaña, puede configurar un filtro predefinido que filtrará la población de destinatarios por el número de mensajes recibidos.
En este vídeo se explica cómo implementar la administración de fatiga en Adobe Campaign mediante filtros.

>[!VIDEO](https://video.tv.adobe.com/v/333778?quality=12)
