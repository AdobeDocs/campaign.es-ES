---
solution: Campaign
product: Adobe Campaign
title: 'Interacción de campaña: administración de ofertas'
description: Introducción a la administración de ofertas
feature: Información general
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 37%

---

# Interacción y gestión de ofertas{#interaction-and-offer-management}

Campaign viene con un módulo de **Interaction** que permite responder en tiempo real durante una interacción con un contacto determinado (un cliente o destinatario) mediante la realización de una o varias ofertas adaptadas. Por ejemplo, estas pueden ser mensajes de comunicación sencillos, ofertas especiales sobre uno o varios productos o un servicio.

Puede crear un catálogo de ofertas que interactúe con los canales salientes (correo electrónico, correo postal, SMS) para seleccionar la mejor oferta y enviarla a un contacto en un contexto determinado. La mejor selección de ofertas para un destinatario se basa en **reglas de idoneidad**. La selección de una oferta de entre un conjunto de ofertas relevantes se determina mediante reglas de prioridad. Las reglas de presentación de ofertas tienen en cuenta el historial del contacto y ayudan a evitar que reciban la misma oferta varias veces.

La interacción permite crear y gestionar un catálogo de ofertas y configurar las reglas de idoneidad y los temas de la aplicación vinculados a ellas. Según el canal elegido, el contenido de la oferta puede personalizarse gracias a las diversas funciones de renderización. Finalmente, puede utilizar el módulo de simulación para calcular el impacto de la presentación de una oferta.

## Conceptos y terminología

Descubra los términos específicos de la oferta y las directrices relacionadas antes de comenzar.

* **** Los entornos incluyen un catálogo de ofertas y espacios de oferta (vínculos). Es necesario crear un entorno mediante la dimensión de segmentación.
Hay dos tipos de entornos:

   * **Entorno** de diseño: las ofertas se crean en el entorno de diseño, así como en las reglas de tipología y . Las reglas de tipología determinan las ofertas que se presentan (o no) a una persona objetivo. La tabla de personas a las que se dirigen las ofertas y la tabla para almacenar todas las propuestas de ofertas también se definen en este entorno. El nodo **[!UICONTROL Design environment]** contiene subcarpetas del espacio de ofertas, filtros predefinidos y categorías de las ofertas. A cada **[!UICONTROL Design environment]**, le corresponde un **[!UICONTROL Live environment]** de solo lectura, generado a partir de este mismo **[!UICONTROL Design environment]**.
   * **Entorno** en directo: entorno vinculado a un  **[!UICONTROL Design environment]** que contiene ofertas de solo lectura cuyo contenido e idoneidad se han aprobado a través de  **[!UICONTROL Design environment]**. Se deben seleccionar para presentarlos insertados en un mensaje.

* El **Offer space** es una ubicación (carpeta) que define la ubicación donde se expone la oferta. Al crear un espacio de oferta, se puede especificar el canal, crear el contenido de la oferta mediante funciones de renderización, especificar el orden de las ofertas y su modo: modo unitario o por lotes (predeterminado). El espacio de oferta es la interfaz entre el canal y el motor de oferta.
* El **Catálogo de ofertas** es un conjunto de ofertas definidas en Adobe Campaign que se puede seleccionar durante una interacción. El catálogo se organiza de forma jerárquica con cada nodo correspondiente a una categoría.
* Una **Category** es una carpeta vinculada al catálogo de ofertas en un entorno, que organiza las ofertas en función de la naturaleza, la fecha de idoneidad y el tema de la aplicación. Una categoría puede contener subcategorías que heredan todas las características de la categoría principal. Las reglas de idoneidad se pueden definir para una categoría a fin de compartirlas en varias ofertas.
* **Los** temas de la aplicación son palabras clave definidas en la categoría, que permiten filtrar ofertas cuando se presentan restringiendo la selección de ofertas a una o dos categorías.
* **Las** reglas de idoneidad son restricciones aplicadas a un entorno, categoría u oferta, relacionadas con el periodo de validez, el objetivo y el peso. Permiten garantizar que una oferta está en línea con el contacto de destino.

   En los entornos, las reglas de idoneidad incluyen reglas de presentación aplicadas a las ofertas y a las personas objetivo.

   En las categorías, las reglas de idoneidad permiten limitar la validez de la categoría en el tiempo, definir los temas de la aplicación y determinar las personas objetivo. También pueden recibir un peso multiplicador durante un periodo determinado. Esto le permite compartir las reglas para las ofertas en otras categorías y simplificar así la administración.

   En las ofertas, las reglas de idoneidad permiten limitar la validez de las ofertas en el tiempo y determinar las personas objetivo.

* El **Arbitrage** es la acción de seleccionar ofertas que se mostrarán en un entorno (ofertas aptas). El arbitraje clasifica las ofertas por prioridad según los criterios definidos en las categorías, ofertas y ofertas de contexto.
* Una **Outbound interaction** llama al motor de interacción desde una lista de contactos (utilizada para enviar correos electrónicos, correo postal, etc.). Se aplican las mismas reglas y procesos a cada contacto. Este tipo de interacción se procesa generalmente en modo por lotes.
* El **Batch mode** permite seleccionar la mejor oferta para un conjunto de contactos. Las reglas de idoneidad/priorización se aplican a todos los contactos del conjunto. Este modo se utiliza generalmente para interacciones salientes.
* El **Unitary mode** permite procesar un solo contacto a la vez. Este modo se utiliza generalmente para mensajes transaccionales.
* **Las** ofertas aptas son ofertas que satisfacen las restricciones definidas por adelantado y que se pueden ofrecer de forma coherente a un objetivo.
* **Las** reglas de presentación son reglas de tipología a las que se hace referencia en el entorno de oferta, lo que permite excluir algunas ofertas teniendo en cuenta el historial de propuestas.
* **** Fórmulas de ponderación que permiten calcular con precisión la importancia de una oferta, para poder seleccionar la oferta más relevante. Los pesos se definen en las ofertas. Las ofertas elegibles se tienen en cuenta en orden de peso reducido.
* **La** función de renderización se define en el espacio de oferta para crear su representación de oferta en función de los atributos definidos en la oferta. Existen tres modos de función de renderización diferentes: HTML, XML y texto.
* **La** propuesta de oferta es el resultado de la acción que consiste en presentar una o varias ofertas a un contacto en un espacio determinado (titular de un sitio web, correo electrónico o SMS, por ejemplo). Este resultado se almacena en la tabla de ofertas propuestas. No obstante, no es obligatorio guardar las propuestas.
* **** Simulationes un módulo que permite probar la presentación de las ofertas en los destinatarios objetivo antes de enviar las ofertas.
* La **Preview** de la oferta muestra la oferta tal como se muestra en su carpeta. Es accesible desde la ventana de configuración de la oferta o el perfil de contacto.
* **Los** filtros predefinidos son reglas de filtrado que pueden tener en cuenta los parámetros de oferta (por ejemplo, un código de oferta). Se pueden reutilizar una vez creadas las ofertas.
* Una **Offer representation** es una información que el canal utiliza para mostrar la oferta. La representación de la oferta puede crearse a partir de la función de procesamiento del espacio en el que la oferta se representa o se introduce directamente en la interfaz (por ejemplo, en el bloque HTML). Una oferta puede representarse por el espacio.

## Introducción a las ofertas

A continuación se enumeran los pasos clave para comenzar.

### Configurar su plataforma

Antes de empezar, como **Administrator** de Campaign, asegúrese de realizar las siguientes tareas en entornos de diseño:

1. Crear perfiles de usuario. [Más información](interaction-operators.md).
1. (opcional) Cree un entorno de oferta para cada dimensión de segmentación. [Obtenga más información](interaction-env.md)
1. Cree reglas de tipología para cada entorno. [Más información](../../interaction/using/managing-offer-presentation.md#creating-and-referencing-an-offer-presentation-rule).
1. Cree espacios de oferta para cada entorno y configure las funciones de renderización. [Más información](../../interaction/using/creating-offer-spaces.md).
Si el espacio está definido mediante un canal unitario en modo identificado, se deben especificar los parámetros avanzados para este espacio.

### Crear y publicar el catálogo de ofertas {#managing-the-offer-catalog-}

Como **Offer manager** debe realizar las siguientes tareas:

1. Cree categorías de oferta en entornos de diseño. [Más información](../../interaction/using/creating-offer-categories.md).
1. Cree ofertas en entornos de diseño. [Más información](../../interaction/using/creating-an-offer.md).
1. Apruebe y publique ofertas en uno o varios espacios para que estén disponibles en entornos interactivos para el gestor de envíos. [Más información](../../interaction/using/approving-and-activating-an-offer.md).

### Aproveche el catálogo de ofertas {#using-the-offer-catalog-}

Como **Delivery manager** debe realizar las siguientes tareas:

1. Cree una campaña.
1. Haga referencia a una oferta de la campaña o la entrega. [Más información](../../interaction/using/about-outbound-channels.md).

