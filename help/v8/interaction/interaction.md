---
title: 'Interacción de campaña: administración de ofertas'
description: Introducción a la Administración de ofertas
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 4da3e69a-6230-4c94-a6f1-4e8c01e854ba
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '1608'
ht-degree: 50%

---

# Administración de interacciones en tiempo real

Campaign incluye un **Interacción** módulo que permite responder en tiempo real durante una interacción a un contacto determinado proponiéndole una o varias ofertas específicas. Estas ofertas pueden ser mensajes de comunicación sencillos, ofertas especiales sobre uno o varios productos o un servicio.

Puede crear un catálogo de ofertas que interactúe con sus canales salientes (correo electrónico, correo directo, SMS) para seleccionar la mejor oferta y enviarla a un contacto en un contexto determinado. La selección de la mejor oferta para un destinatario se basa en **reglas de elegibilidad**. La selección de una oferta de entre un conjunto de ofertas relevantes se determina mediante reglas de prioridad. Las reglas de presentación de ofertas tienen en cuenta el historial del contacto y ayudan a evitar que reciban la misma oferta varias veces.

La interacción permite crear y gestionar un catálogo de ofertas y configurar las reglas de idoneidad y los temas de la aplicación vinculados a ellas. Según el canal elegido, el contenido de la oferta puede personalizarse gracias a las diversas funciones de renderización. Finalmente, puede utilizar el módulo de simulación para calcular el impacto de la presentación de una oferta.

![](assets/interaction-cycle.png)

En primer lugar, se produce un contacto entre un cliente y una empresa a través de un canal de comunicación: puede ser un sitio web (interacción saliente), un correo electrónico, un SMS, una notificación push (interacciones entrantes). [Más información](#interaction-types)

Este contacto llama al motor de oferta. (1)

Cuando se activa el motor de oferta, se seleccionan una o varias ofertas del catálogo de ofertas en función de la configuración del número de ofertas de la propuesta. (2)

A continuación, se aplican las reglas de idoneidad: las mejores ofertas se seleccionan en función de las reglas de idoneidad, las fechas de inicio y finalización de las ofertas, los datos de perfil y el comportamiento en tiempo real del cliente. (3)

El historial de propuestas de perfil se actualiza una vez realizada la selección, para evitar la duplicación de las ofertas presentadas. (4)

Finalmente, se propone la mejor oferta al objetivo. (5)

## Introducción a las ofertas

A continuación se enumeran los pasos clave para el inicio.

### Configurar su plataforma

Antes de empezar, como campaña **Administrador**, asegúrese de realizar las siguientes tareas en entornos de diseño:

1. Crear perfiles de usuario. [Más información](interaction-operators.md)
1. (Opcional) Cree un entorno de oferta para cada dimensión de segmentación. [Más información](interaction-env.md)
1. Cree reglas de tipología para cada entorno. [Más información](interaction-offer.md#offer-presentation)
1. Cree espacios de oferta para cada entorno y configure las funciones de renderización. [Más información](interaction-offer-spaces.md)
Si el espacio se define mediante un canal unitario en modo identificado, se deben especificar los parámetros avanzados para este espacio.

   >[!NOTE]
   >
   >Si el espacio está definido mediante un canal unitario en modo identificado, se deben especificar los parámetros avanzados para este espacio.

1. Configure el Motor de oferta para que las interacciones entrantes presenten y actualicen una o varias ofertas.

   Los distintos modos de integración se detallan en [esta sección](interaction-present-offers.md).

   >[!NOTE]
   >
   >Cuando se crea un espacio de oferta en el canal web entrante, se debe configurar el sitio web para que muestre esta oferta.
   >

### Creación y publicación del catálogo de ofertas {#managing-the-offer-catalog-}

Como un **Gestor de ofertas** debe:

1. Cree categorías de oferta en entornos de diseño. [Más información](interaction-offer-catalog.md#creating-offer-categories)
1. Cree ofertas en entornos de diseño. [Más información](interaction-offer.md)
1. Apruebe y publique ofertas en uno o varios espacios para que estén disponibles en entornos interactivos para el administrador de envíos. [Más información](interaction-offer.md#approve-offers)

### Uso del catálogo de ofertas {#using-the-offer-catalog-}

As a **Gestor de envíos**  debe:

1. Cree una campaña.
1. Hacer referencia a una oferta en la campaña o en la entrega. [Más información](interaction-send-offers.md).

## Glosario

Descubra los términos específicos de la oferta y las directrices relacionadas antes de empezar.

* **Environment**: define lo que incluye un catálogo de ofertas y los enlaces (espacios de oferta). Cree un entorno mediante la dimensión de segmentación. Hay dos tipos de entornos:

   * **Design environment**: entorno en el que se crean y/o se definen las reglas tipológicas (reglas que determinan las ofertas para presentarlas, o no, a una persona destinataria). En esta sección también se definen la lista de personas que reciben las ofertas y la lista de almacenamiento de todas ellas. El **[!UICONTROL Design environment]** El nodo contiene subcarpetas del espacio de ofertas, filtros predefinidos y categorías de las ofertas. A cada **[!UICONTROL Design environment]**, le corresponde un **[!UICONTROL Live environment]** de solo lectura, generado a partir de este mismo **[!UICONTROL Design environment]**.
   * **Live environment**: entorno vinculado a **[!UICONTROL Design environment]**. Contiene ofertas de solo lectura cuyo contenido e idoneidad se han aprobado a través de la **[!UICONTROL Design environment]**. Están disponibles para mostrarse en un sitio web o insertarse en un mensaje.

* **Offer space**: carpeta que determina la ubicación donde se expone la oferta. Al definir un espacio, puede:
   * seleccione el canal
   * elija si se puede utilizar en modo unitario (de forma predeterminada: solo en modo por lotes)
   * crear el contenido de la oferta mediante funciones de renderización
   * especifique las ofertas que desea presentar

  Un espacio es una interfaz entre el canal y el motor de oferta.

  >[!CAUTION]
  >
  >Un espacio de oferta no es un canal de comunicación, coincide con una ubicación de presentación específica del canal. Por ejemplo, las ofertas expuestas en un sitio web pueden ocupar dos espacios en la misma página. En este caso, tiene dos espacios para el mismo canal.
  >
  >Los espacios deben definirse en las especificaciones y no deben modificarse durante el proyecto.

* **Offer catalog**: conjunto de ofertas definidas en Adobe Campaign que se puede seleccionar durante una interacción. El catálogo se organiza de forma jerárquica con cada nodo correspondiente a una categoría.
* **Category**: una carpeta relacionada con el catálogo de ofertas en un entorno, que organiza las ofertas según la naturaleza, la fecha de idoneidad y el tema de la aplicación. Una categoría puede contener subcategorías que heredan todas las características de la categoría principal. Las reglas de idoneidad se pueden definir para una categoría a fin de compartirlas en varias ofertas.
* **Application themes**: las palabras clave definidas en la categoría permiten filtrar ofertas cuando se presentan en un canal entrante o saliente y restringen la selección de ofertas a una o dos categorías.

  >[!NOTE]
  >
  >Las categorías secundarias heredan los temas identificados en la categoría principal.

* **Reglas de elegibilidad**: restricciones aplicadas a un entorno, categoría u oferta sobre el periodo de validez, el destinatario y el peso. Permiten garantizar que una oferta está en línea con el contacto de destino.

  En los entornos, las reglas de idoneidad incluyen reglas de presentación aplicadas a las ofertas y a los destinatarios.

  En las categorías, las reglas de idoneidad permiten: limitar la validez de la categoría en el tiempo, definir los temas de la aplicación y determinar las personas objetivo. También pueden recibir un peso multiplicador durante un tiempo determinado. Esto le permite compartir las reglas para las ofertas en otras categorías y simplificar así la administración.

  En las ofertas, las reglas de idoneidad permiten limitar la validez de las ofertas en el tiempo y determinar los destinatarios.

* **Arbitraje**: selección de ofertas para mostrar en un entorno (ofertas aptas). El principio de arbitraje clasifica las ofertas por prioridad según los criterios definidos en las categorías, ofertas y ofertas de contexto.
* **Contact**: un contacto de una interacción entrante. Durante el procesamiento de visualización del motor, el contacto se asocia a una dimensión de segmentación. Hay dos tipos de contactos:

   * **[!UICONTROL Identified contact]** : un contacto que se ha identificado voluntariamente en el canal. En las interacciones de salida, el contacto se identifica automáticamente.
   * **[!UICONTROL Anonymous contact]** : contacto que no se ha suscrito oficialmente a través del canal, pero que puede identificarse implícitamente mediante una cookie. Esta terminología solo se utiliza para interacciones entrantes.

     >[!NOTE]
     >
     >Los contactos no identificados y anónimos se atribuyen a la dimensión de segmentación del visitante.

* **Interacción saliente**: invoque al motor de oferta desde una lista de contactos (utilizada para enviar correos electrónicos, correo directo, etc.). Se aplican las mismas reglas y procesos a cada contacto. Este tipo de interacción se procesa generalmente en modo por lotes.
* **Inbound interaction**: interacción después de una llamada entrante generada por la acción de un contacto en el canal. Este tipo de interacción se procesa generalmente en modo unitario.
* **Batch mode**: el modo por lotes permite seleccionar la mejor oferta para un conjunto de contactos. Las reglas de idoneidad/priorización se aplican a todos los contactos del conjunto. Este modo se aplica generalmente a las interacciones salientes.
* **Unitary mode**: se procesa un solo contacto cada vez. Este modo se aplica generalmente a interacciones entrantes y mensajes transaccionales.
* **Modo de identificación**: hace referencia al estado de un contacto:

   * **[!UICONTROL explicit]** : los contactos se identifican mediante su inicio de sesión en la interfaz del canal.
   * **[!UICONTROL implicit]** : los contactos se identifican mediante una cookie (permanente o por sesión). Puede procesarse como contacto anónimo o identificado.
   * **[!UICONTROL anonymous]** : los contactos no se pueden identificar.

* **Oferta elegible**: ofrece a las reuniones las restricciones definidas por adelantado que pueden ofrecerse de forma coherente a un objetivo.
* **Presentation rules**: reglas de tipología a las que se hace referencia en el entorno de la oferta, que le permiten excluir algunas ofertas tomando en cuenta el historial de propuestas.
* **Grosor**: fórmulas que permiten calcular con precisión la relevancia de una oferta para seleccionar la oferta más relevante. Los pesos se definen en las ofertas. Las ofertas elegibles se tienen en cuenta en orden de peso descendiente.
* **Función de renderización**: función definida en el espacio de oferta para construir su representación de oferta en función de los atributos definidos en la oferta. Existen tres modos de función de renderización diferentes: HTML, XML y texto.
* **Offer proposition**: resultado de la acción que consiste en presentar una o varias ofertas a un contacto en un espacio determinado (titular de un sitio web, correo electrónico o SMS, por ejemplo). Este resultado se almacena en la tabla de ofertas propuestas. No obstante, no es obligatorio guardar las propuestas.
* **Simulation**: módulo que permite probar la presentación de las ofertas en los destinatarios objetivo antes de enviar las ofertas.
* **Preview**: previsualización de la oferta tal y como se muestra en su carpeta. Es accesible desde la ventana de configuración de la oferta o el perfil de contacto.
* **filtros predefinidos**: las reglas de filtrado predefinidas pueden tener en cuenta los parámetros de oferta (por ejemplo, un código de oferta). Se pueden reutilizar una vez creadas las ofertas.
* **Offer representation**: información utilizada por el canal para mostrar la oferta. La representación de la oferta puede crearse a partir de la función de procesamiento del espacio en el que la oferta se representa o se introduce directamente en la interfaz (por ejemplo, en el bloque HTML). Una oferta puede representarse por el espacio.
* **Changeover process**: un proceso activado en un entorno identificado, responsable de dirigir la llamada a un entorno anónimo si el contacto no se ha identificado explícitamente o está identificado de forma implícita.
