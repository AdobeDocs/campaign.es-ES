---
product: campaign
title: 'Prácticas recomendadas de interacción de Adobe Campaign '
description: Método de prácticas recomendadas para administrar el módulo de interacción en Adobe Campaign
exl-id: 28f3a5bc-67f5-413e-b2ba-35c341f9ec5f
source-git-commit: c19ac91fe7b4b825f75ec096320efabc3e78328c
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 70%

---

# Prácticas recomendadas de interacción{#interaction-best-practices}

## Recomendaciones generales {#general-recommendations}

La gestión de ofertas en Adobe Campaign requiere una gestión cuidadosa para funcionar de forma eficaz. Para evitar problemas, debe encontrar un equilibrio entre el número de contactos y el número de categorías de ofertas y ofertas.

Esta sección presenta las prácticas recomendadas para administrar el **Interacción** en Adobe Campaign, incluidas las reglas de idoneidad, los filtros predefinidos, las actividades de flujo de trabajo y las opciones de la base de datos.

* When **implementación y configuración de interacciones**, debe tener en cuenta las siguientes recomendaciones:

   * Para el motor por lotes (generalmente utilizado en comunicaciones salientes como el correo electrónico), el rendimiento es la preocupación principal, ya que se pueden manejar varios contactos al mismo tiempo. El típico obstáculo es el rendimiento de la base de datos.
   * La restricción principal del motor unitario (que generalmente se utiliza en comunicaciones entrantes como un banner en un sitio web) es la latencia, ya que alguien está esperando una respuesta. El típico obstáculo es el rendimiento de la CPU.
   * El diseño del catálogo de ofertas tiene un gran impacto en el rendimiento de Adobe Campaign 
   * Al trabajar con muchas ofertas, se recomienda dividirlas en varios catálogos de ofertas.

* A continuación se enumeran algunas prácticas recomendadas al trabajar con **reglas de elegibilidad**:

   * Simplificar las reglas. La complejidad de las reglas afecta al rendimiento a medida que amplía la búsqueda. Una regla compleja es cualquier regla que tenga más de cinco condiciones.
   * Para aumentar el rendimiento, las reglas se pueden dividir en distintos filtros predefinidos que se comparten en varias ofertas.
   * Coloque las reglas de la categoría de oferta más restrictivas en la posición más alta posible del árbol. En este caso, ponga en primer lugar el filtro para la mayoría de contactos, reduciendo el número de objetivo y evitará que se procesen más reglas.
   * Coloque las reglas más pesadas en términos de tiempo o procesamiento en la parte inferior del árbol. De este modo, estas reglas sólo se ejecutarán para los destinatarios restantes.
   * Comience en una categoría específica para evitar el escaneo del árbol completo.
   * Para ahorrar tiempo de procesamiento, precalcule se añade en lugar de crear reglas complejas con uniones. Para ello, intente almacenar los datos del cliente en una tabla de referencia que se pueda buscar en reglas de elegibilidad.
   * Utilice un número mínimo de ponderaciones para limitar el número de consultas.
   * Se recomienda tener un número limitado de ofertas por espacio de oferta. Esto garantiza una recuperación más rápida de las ofertas en un espacio determinado.
   * Utilice índices, especialmente en las columnas de búsqueda utilizadas frecuentemente.

* A continuación se enumeran algunas prácticas recomendadas con respecto a **tabla de propuestas**:

   * Utilice un número mínimo de reglas para realizar el procesamiento lo más rápidamente posible.
   * Limite el número de registros de la tabla de propuestas: mantenga únicamente los registros necesarios para realizar el seguimiento de su actualización de estado y lo que necesita las reglas, luego archívelo en otro sistema.
   * Realice un mantenimiento intensivo de la base de datos en la tabla de propuestas, como la regeneración de índices o la regeneración de tablas.
   * Limite el número de proposiciones solicitadas por destino. No configure más de lo que realmente va a utilizar.
   * Evite las uniones lo máximo posible en los criterios de regla.

## Sugerencias al administrar ofertas {#tips-managing-offers}

Esta sección contiene consejos más detallados sobre la administración de ofertas y el uso del módulo de interacción en Adobe Campaign.

### Varios espacios de oferta en un correo electrónico {#multiple-offer-spaces}

Cuando se incluyen ofertas en los envíos, las ofertas generalmente se seleccionan de forma ascendente en el flujo de trabajo de Campaign a través de un **Enriquecimiento** actividad de flujo de trabajo (u otra actividad similar).

Al seleccionar ofertas en una **Enriquecimiento** actividad, puede elegir qué espacio de oferta utilizar. Sin embargo, independientemente del espacio de oferta seleccionado, el menú de personalización de la entrega depende del espacio de oferta configurado en la entrega.

En el ejemplo siguiente, el espacio de oferta seleccionado en la entrega es **[!UICONTROL Email (Environment - Recipient)]**:

![](assets/Interaction-best-practices-offer-space-selected.png)

Si el espacio de oferta seleccionado en la entrega no tiene una función de renderización HTML configurada, no la va a ver en el menú de entrega y no va a estar disponible para su selección. Es independiente del espacio de oferta seleccionado en la variable **Enriquecimiento** actividad.

En el ejemplo siguiente, la función de renderización HTML está disponible en la lista desplegable porque el espacio de oferta seleccionado en la entrega tiene una función de renderización:

![](assets/Interaction-best-practices-HTML-rendering.png)

Esta función inserta un código como: `<%@ include proposition="targetData.proposition" view="rendering/html" %>`.

Al seleccionar la propuesta, el valor del atributo de **[!UICONTROL view]** es el siguiente:
* “rendering/html”: renderización html. Utiliza la función de renderización HTML.
* “offer/view/html”: contenido html. No utiliza la función de renderización HTML. Solo incluye el campo HTML.

Cuando se incluyen varios espacios de oferta en una entrega por correo electrónico único y algunos de ellos tienen funciones de renderización y otros no, se debe recordar qué ofertas utilizan qué espacios de oferta y qué espacios de oferta tienen funciones de renderización.

Por lo tanto, para evitar cualquier problema, se recomienda que todos los espacios de oferta tengan una función de renderización HTML definida, aunque el espacio de oferta solo requiera contenido HTML.

### Establezca la clasificación en la tabla del registro de propuestas {#rank-proposition-log-table}

Los espacios de oferta tienen la capacidad de almacenar datos en la tabla de propuesta cuando se generan o aceptan propuestas:

![](assets/Interaction-best-practices-offer-space-storage.png)

Sin embargo, esto solo se aplica a las interacciones entrantes.

También es posible almacenar datos adicionales en la tabla de propuestas cuando se utilizan interacciones salientes y también cuando se utilizan ofertas salientes sin el módulo de interacción.

Cualquier campo de la tabla temporal del flujo de trabajo cuyo nombre coincida con el nombre de un campo de la tabla de propuestas se copia en el mismo campo de la tabla de propuestas.

Por ejemplo, al seleccionar una oferta manualmente (sin interacción) en una **Enriquecimiento** actividad de flujo de trabajo, los campos estándar se definen de la siguiente manera:

![](assets/Interaction-best-practices-manual-offer-std-fields.png)

Se pueden agregar campos adicionales, como un `@rank` campo:

![](assets/Interaction-best-practices-manual-offer-add-fields.png)

Porque hay un campo en la tabla de propuestas llamado `@rank`, se copiará el valor de la tabla temporal del flujo de trabajo.

Para obtener más información sobre el almacenamiento de campos adicionales en la tabla de propuestas, consulte [esta sección](interaction-send-offers.md#storing-offer-rankings-and-weights).

En el caso de las ofertas salientes con interacción, esto resulta útil cuando se seleccionan varias ofertas y se desea registrar en qué orden se van a mostrar en un mensaje de correo electrónico.

También puede almacenar metadatos adicionales directamente en la tabla de propuestas, como el nivel de gasto actual, para mantener registros históricos sobre el gasto en el momento en que se generaron las ofertas.

Cuando se utiliza la interacción saliente, la variable `@rank` se puede agregar, como en el ejemplo anterior, pero su valor se establece automáticamente en función del orden devuelto por la interacción. Por ejemplo, si utiliza la interacción para seleccionar tres ofertas, la variable `@rank` tendrá los valores 1, 2 y 3 devueltos.

Al utilizar la interacción y seleccionar ofertas manualmente, el usuario puede combinar ambos métodos. Por ejemplo, el usuario puede configurar manualmente la variable `@rank` que será 1 para la oferta seleccionada manualmente y utilice una expresión como `"1 + @rank"` para las ofertas devueltas por interacción. Si damos por supuesto que la interacción selecciona tres ofertas, las ofertas devueltas por ambos métodos se van a clasificar de 1 a 4:

![](assets/Interaction-best-practices-manual-offer-combined.png)

### Ampliación del esquema nms:offer {#extending-nms-offer-schema}

Al ampliar el esquema nms:offer, asegúrese de seguir la estructura predeterminada ya configurada:
* Defina cualquier campo nuevo para almacenamiento de contenido en `<element name="view">`.
* Cada nuevo campo debe definirse dos veces. Una vez como campo XML normal y una vez como campo XML CDATA con “_jst” anexado al nombre. Por ejemplo:

   ```
   <element label="Price" name="price" type="long" xml="true"/>
   <element advanced="true" label="Script price" name="price_jst" type="CDATA" xml="true"/>
   ```

* Todos los campos que contengan direcciones URL que se van a rastrear deben colocarse bajo `<element name="trackedUrls">` que se encuentra en `<element name="view" >`.
