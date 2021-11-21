---
product: campaign
title: Presentar ofertas a perfiles anónimos (interacción entrante)
description: Obtenga información sobre cómo presentar ofertas a perfiles anónimos
exl-id: b7a04360-f8c6-4c69-9594-2b44d3f819b7
source-git-commit: 00a88cf9217faf32070a3cd34a2c1ae5243d9a6e
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 75%

---

# Interacciones anónimas{#anonymous-interactions}

## Entorno para interacciones anónimas {#environment-for-anonymous-interactions}

De forma predeterminada, Campaign **Interacción** viene con un entorno preconfigurado para dirigirse a la tabla de destinatarios integrada (ofertas identificadas). Si necesita establecer como objetivo otra tabla, una tabla de visitante para ofertas anónimas o una tabla de destinatarios personalizada, por ejemplo, debe utilizar el asistente de asignación de destino para crear el entorno. [Más información sobre los entornos](interaction-env.md).

Cuando se crea un entorno anónimo a través del asistente para la creación de asignaciones, la casilla **[!UICONTROL Environment dedicated to incoming anonymous interactions]** se marca automáticamente en la pestaña **[!UICONTROL General]** del entorno.

El **[!UICONTROL Targeting dimension]** se completa automáticamente. De manera predeterminada, se vincula a la tabla del visitante.

Aparece el campo **[!UICONTROL Visitor folder]**. Se completa automáticamente para vincular la carpeta **[!UICONTROL Visitors]**. Este campo permite elegir dónde almacenar los perfiles de visitantes.

![](assets/anonymous_environment_option.png)

>[!NOTE]
>
>Si se desea filtrar varios tipos de visitantes, por ejemplo, en el caso de ofertas anónimas presentadas para una o más marcas, se debe crear un entorno para cada marca y una carpeta de tipo **[!UICONTROL Visitors]** cada entorno.

## Catálogo de ofertas para interacciones anónimas {#offer-catalog-for-anonymous-interactions}

Al igual que las interacciones de salida, las interacciones entrantes se organizan en un catálogo de ofertas que consta de categorías y ofertas.

Para crear categorías y espacios, aplique el mismo proceso que para los visitantes identificados. Consulte [Crear una categoría de oferta](interaction-offer-catalog.md#creating-offer-categories) y [Creación de un entorno de oferta](interaction-env.md#creating-an-offer-environment)).

## Visitantes anónimos {#anonymous-visitors}

Los visitantes anónimos pueden enviarse a un proceso de identificación de cookie cuando se conectan. Este reconocimiento implícito se basa en el historial del explorador del visitante.

Durante este paso, se realiza una comparación entre los datos que recuperan las cookies y los de la base de datos. En algunos casos, los visitantes se reconocen (y luego se identifican implícitamente); en otros casos, no se reconocen (y por lo tanto permanecen anónimos).

Para ejecutar este análisis para el espacio de ofertas, marque la opción **[!UICONTROL Implicitly identify the individual based on their browser history]**.

![](assets/identification_anonymous_visitors.png)

## Procesamiento de visitantes anónimos sin identificar {#processing-unidentified-anonymous-visitors}

Tras el análisis, si un visitante anónimo no se identifica, se puede almacenar sus datos en un espacio determinado. Esto permite sugerir ofertas especialmente destinadas a este tipo de visitante, que coincide con las reglas especificadas de tipología.

Si no hay ningún elemento que permita identificar un contacto o si no se desea sugerir una oferta identificada a un contacto que pueda identificarse implícitamente, se puede optar por realizar una reserva en un entorno anónimo.

Para ello, marque la casilla de verificación **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]** y, a continuación, especifique el entorno dedicado a estos visitantes no identificados en el **[!UICONTROL Linked anonymous space]** al especificar un espacio de ofertas.

![](assets/anonymous_to_anonymous_environment.png)
