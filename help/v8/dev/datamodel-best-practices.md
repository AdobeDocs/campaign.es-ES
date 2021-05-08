---
solution: Campaign
product: Adobe Campaign
title: Prácticas recomendadas del modelo de datos
description: Conozca las prácticas recomendadas de extensión del modelo de datos de Campaign
translation-type: tm+mt
source-git-commit: 8da6928096feec988d6495fdb617dda7d7cac6ff
workflow-type: tm+mt
source-wordcount: '2663'
ht-degree: 4%

---

# Prácticas recomendadas del modelo de datos{#data-model-best-practices}

Este documento describe las recomendaciones clave al diseñar el modelo de datos de Adobe Campaign.

El sistema Adobe Campaign es muy flexible y se puede ampliar más allá de la implementación inicial. Sin embargo, aunque las posibilidades son infinitas, es fundamental tomar decisiones sabias y construir bases sólidas para empezar a diseñar su modelo de datos.

Para comprender mejor las tablas integradas de Campaign y cómo se relacionan entre sí, consulte [esta sección](datamodel.md) .

:bulb: Lea [esta sección](schemas.md) para empezar a utilizar esquemas de Campaign.

:bulb: Obtenga información sobre cómo configurar esquemas de extensión para ampliar el modelo de datos conceptuales de la base de datos de Adobe Campaign en [esta página](extend-schema.md).

## Arquitectura del modelo de datos {#data-model-architecture}

Adobe Campaign es un potente sistema de administración de campañas en canales múltiples que puede ayudarle a alinear sus estrategias en línea y sin conexión para crear experiencias personalizadas con los clientes.

### Enfoque centrado en el cliente {#customer-centric-approach}

Aunque la mayoría de los proveedores de servicios de correo electrónico se comunican a los clientes mediante un enfoque centrado en la lista, Adobe Campaign depende de una base de datos relacional para aprovechar una vista más amplia de los clientes y sus atributos.

Para acceder a la descripción de cada tabla, vaya a **[!UICONTROL Admin > Configuration > Data schemas]**, seleccione un recurso de la lista y haga clic en la pestaña **[!UICONTROL Documentation]**.


>[!NOTE]
>
>Adobe Campaign permite crear una [tabla de destinatarios personalizada](custom-recipient.md). Sin embargo, en la mayoría de los casos, se recomienda aprovechar la [tabla de destinatarios](datamodel.md#ootb-profiles) integrada que ya tiene tablas y características adicionales prediseñadas.

### Datos para Adobe Campaign {#data-for-campaign}

¿Qué datos se deben enviar a Adobe Campaign? Es fundamental determinar los datos necesarios para sus actividades de marketing.

>[!NOTE]
>
>Adobe Campaign no es ni un almacén de datos ni una herramienta de creación de informes. Por lo tanto, no intente importar todos los clientes posibles y su información asociada en Adobe Campaign ni importe los datos que solo se utilizarán para generar informes.

Para tomar la decisión de si un atributo sería necesario o no en Adobe Campaign, pregúntese si correspondería a una de estas categorías:

* Atributo utilizado para la **segmentación**
* Atributo utilizado para **procesos de administración de datos** (cálculo agregado, por ejemplo)
* Atributo utilizado para **personalización**

Si no se incluye en ninguno de estos parámetros, lo más probable es que no necesite este atributo en Adobe Campaign.

### Opción de tipos de datos {#data-types}

Para garantizar una buena arquitectura y un buen rendimiento de su sistema, siga las prácticas recomendadas a continuación para configurar los datos en Adobe Campaign.

* Una tabla grande debería tener principalmente campos numéricos y contener vínculos a tablas de referencia (cuando se trabaja con la lista de valores).
* El atributo **expr** permite definir un atributo de esquema como campo calculado en lugar de como valor de conjunto físico en una tabla. Esto puede permitir el acceso a la información en un formato diferente (por ejemplo, en cuanto a la edad y la fecha de nacimiento) sin necesidad de almacenar ambos valores. Esta es una buena forma de evitar la duplicación de campos. Por ejemplo, la tabla de destinatarios utiliza una expresión para el dominio , que ya está presente en el campo de correo electrónico.
* Sin embargo, cuando el cálculo de la expresión es complejo, no se recomienda utilizar el atributo **expr** ya que el cálculo sobre la marcha puede afectar al rendimiento de las consultas.
* El tipo **XML** es una buena forma de evitar la creación de demasiados campos. Pero también ocupa espacio en disco, ya que utiliza una columna CLOB en la base de datos. También puede generar consultas SQL complejas y afectar al rendimiento.
* La longitud de un campo **string** siempre debe definirse con la columna . De forma predeterminada, la longitud máxima en Adobe Campaign es 255, pero Adobe recomienda mantener el campo más corto si ya sabe que el tamaño no excederá una longitud más corta.
* Es aceptable tener un campo más corto en Adobe Campaign que en el sistema de origen si está seguro de que el tamaño del sistema de origen se sobreestimó y no se alcanzaría. Esto podría significar una cadena más corta o un número entero menor en Adobe Campaign.

### Elección de campos {#choice-of-fields}

Un campo debe almacenarse en una tabla si tiene un propósito de objetivo o personalización. En otras palabras, si un campo no se utiliza para enviar un correo electrónico personalizado o se utiliza como criterio en una consulta, ocupará innecesariamente espacio en disco.


### Elección de claves {#choice-of-keys}

Además del **autouuid** definido de forma predeterminada en la mayoría de las tablas, debe considerar la posibilidad de agregar algunas claves lógicas o empresariales (número de cuenta, número de cliente, etc.). Se puede utilizar más adelante para importar/reconciliación o paquetes de datos. Para obtener más información, consulte [Identifiers](#identifiers).

Las claves eficientes son esenciales para el rendimiento. Siempre debe preferirse los tipos de datos numéricos como claves para las tablas.

<!-- ### Dedicated tablespaces {#dedicated-tablespaces}

The tablespace attribute in the schema allows you to specify a dedicated tablespace for a table.

The installation wizard allows you to store objects by type (data, temporary).

Dedicated tablespaces are better for partitioning, security rules, and allow fluid and flexible administration, better optimization, and performance. -->

## Identificadores {#identifiers}

Los recursos de Adobe Campaign tienen tres identificadores y es posible añadir un identificador adicional.

En la tabla siguiente se describen estos identificadores y su finalidad.

| Identifier | Descripción | Prácticas recomendadas |
|--- |--- |--- |
| Id | <ul><li>El id es la clave principal física de una tabla de Adobe Campaign. Para las tablas integradas, se trata de un ID único universal (UUID)</li><li>Este identificador debe ser único. </li><li>Un UUID puede ser visible en una definición de esquema.</li></ul> | <ul><li>Los identificadores generados automáticamente no deben utilizarse como referencia en un flujo de trabajo o en una definición de paquete.</li><li>El ID de una tabla es un UUID y este tipo no debe cambiarse.</li></ul> |
| Nombre (o nombre interno) | <ul><li>Esta información es un identificador único de un registro de una tabla. Este valor se puede actualizar manualmente, normalmente con un nombre generado.</li><li>Este identificador mantiene su valor cuando se implementa en una instancia diferente de Adobe Campaign y no debe estar vacío.</li></ul> | <ul><li>Cambie el nombre del registro generado por Adobe Campaign si el objeto está diseñado para implementarse de un entorno a otro.</li><li>Cuando un objeto tiene un atributo de espacio de nombres (*schema*, por ejemplo), este área de nombres común se utilizará en todos los objetos personalizados creados. Algunas áreas de nombres reservadas no deben usarse: *nms*, *xtk*.</li><li>Cuando un objeto no tiene área de nombres (*workflow* o *delivery*, por ejemplo), esta noción de área de nombres se agregaría como prefijo de un objeto de nombre interno: *namespaceMyObjectName*.</li><li>No utilice caracteres especiales como espacio &quot;&quot;, semicolumna &quot;:&quot; o guión &quot;-&quot;. Todos estos caracteres se sustituirían por un guión bajo &quot;_&quot; (carácter permitido). Por ejemplo, &quot;abc-def&quot; y &quot;abc:def&quot; se almacenarían como &quot;abc_def&quot; y se sobrescribirían entre sí.</li></ul> |
| Etiqueta | <ul><li>La etiqueta es el identificador comercial de un objeto o registro en Adobe Campaign.</li><li>Este objeto permite espacios y caracteres especiales.</li><li>No garantiza la exclusividad de un registro.</li></ul> | <ul><li>Se recomienda determinar una estructura para las etiquetas de objeto.</li><li>Esta es la solución más fácil de usar para identificar un registro u objeto para un usuario de Adobe Campaign.</li></ul> |

La clave principal de Adobe Campaign es un UUID generado automáticamente para todas las tablas integradas. También se puede utilizar un UUID para tablas personalizadas.

Aunque el número de ID sea infinito, debe cuidar el tamaño de la base de datos para garantizar un rendimiento óptimo. Para evitar cualquier problema, asegúrese de ajustar la configuración de depuración de la instancia. Para obtener más información, consulte [esta sección](#data-retention).


## Claves internas personalizadas {#custom-internal-keys}

Se requieren claves principales para cada tabla creada en Adobe Campaign.

La mayoría de las organizaciones están importando registros de sistemas externos. Aunque la clave física de la tabla de destinatarios es el atributo &quot;id&quot;, también es posible determinar una clave personalizada.

Esta clave personalizada es la clave principal del registro real en el sistema externo que alimenta a Adobe Campaign.

Al crear una tabla personalizada, tiene dos opciones:
* Una combinación de clave generada automáticamente (id) y clave interna (custom). Esta opción es interesante si la clave del sistema es una clave compuesta o no un número entero. Los integradores proporcionarán un mayor rendimiento en las mesas grandes y se unirán a otras tablas.
* Uso de la clave principal como clave principal del sistema externo. Esta solución suele ser preferible, ya que simplifica el enfoque para importar y exportar datos, con una clave coherente entre los distintos sistemas. Se debe desactivar el autoid si la clave se denomina &quot;id&quot; y se espera que se rellene con valores externos (no autogenerados).

>[!CAUTION]
>
>Un autouuid no debe utilizarse como referencia en flujos de trabajo.


## Enlaces y cardinalidad {#links-and-cardinality}

### Vínculos {#links}

Tenga cuidado con la integridad &quot;propia&quot; de las tablas grandes. La eliminación de registros que tienen tablas grandes con integridad &quot;propia&quot; puede detener la instancia. La tabla está bloqueada y las eliminaciones se realizan una por una. Así que es mejor usar integridad &quot;neutral&quot; en tablas secundarias que tienen grandes volúmenes.

Declarar un vínculo como una unión externa no es bueno para el rendimiento. El registro de id cero emula la funcionalidad de unión externa. No es necesario declarar las uniones externas si el vínculo utiliza el autouuid.

Aunque es posible unir cualquier tabla en un flujo de trabajo, Adobe recomienda definir vínculos comunes entre los recursos directamente en la definición de la estructura de datos.

El vínculo se debe definir en alineación con los datos reales de las tablas. Una definición incorrecta podría afectar a los datos recuperados mediante vínculos, por ejemplo, duplicando registros de forma inesperada.

Asigne un nombre al vínculo de forma coherente con el nombre de la tabla: el nombre del vínculo debería ayudar a comprender cuál es la tabla distante.

No asigne a un vínculo el nombre &quot;id&quot; como sufijo. Por ejemplo, asígnele el nombre &quot;transaction&quot; en lugar de &quot;transactionId&quot;.

De forma predeterminada, Adobe Campaign crea un vínculo utilizando la clave principal de la tabla externa. Para una mayor claridad, es preferible definir explícitamente la unión en la definición del vínculo.

### Cardinalidad {#cardinality}

Al diseñar un vínculo, asegúrese de que el registro de destino sea único cuando se haya declarado una relación 1-1. De lo contrario, la unión puede devolver varios registros cuando solo se espera uno. Esto da como resultado errores durante la preparación del envío cuando &quot;la consulta devuelve más filas de las esperadas&quot;. Establezca el nombre del vínculo en el mismo nombre que el esquema de destino.

Defina un vínculo con una cardinalidad (1-N) en el esquema del lado (1). Por ejemplo, la relación Recipient (1) - (N) Transaction debe definirse en el esquema de transacción.

Tenga en cuenta que la cardinalidad inversa de un vínculo es (N) de forma predeterminada. Es posible definir un vínculo (1-1) añadiendo el atributo revCardinality=&#39;single&#39; a la definición del vínculo.

Si el vínculo inverso no debe ser visible para el usuario, puede ocultarlo con la definición del vínculo revLink=&#39;_NONE_&#39;. Un buen caso de uso para esto es definir un vínculo del destinatario a la última transacción completada, por ejemplo. Solo es necesario ver el vínculo del destinatario a la última transacción y no es necesario que el vínculo inverso esté visible desde la tabla de transacciones.

Los vínculos que realizan una unión externa (1-0.0.1) deben utilizarse con cuidado, ya que afectarán al rendimiento del sistema.

## Retención de datos {#data-retention}

Adobe Campaign no es ni un almacén de datos ni una herramienta de creación de informes. Por lo tanto, para garantizar un buen rendimiento de la solución Adobe Campaign, el crecimiento de las bases de datos debe mantenerse bajo control. Para lograrlo, puede ser útil seguir algunas de las prácticas recomendadas a continuación.

Independientemente de la retención, las tablas de registro predeterminadas de Campaign tienen períodos de retención predefinidos, que generalmente limitan el almacenamiento de datos a seis meses o menos.

A continuación se muestran los valores de retención predeterminados para las tablas predeterminadas. Tenga en cuenta que los administradores técnicos de Adobe configuran los ajustes de retención durante la implementación y los valores pueden variar en función de los requisitos de los clientes.

* **Seguimiento consolidado**: 1 año
* **Registros de envío**: 6 meses
* **Registros de seguimiento**: 1 año
* **Envíos eliminados**: 1 semana
* **Importar rechazos**: 6 meses
* **Perfiles de visitante**: 1 mes
* **Propuestas de oferta**: 1 año
* **Eventos**: 1 mes
* **Estadísticas del procesamiento de eventos**: 1 año
* **Eventos archivados**: 1 año
* **Eventos de canalización ignorados**: 1 mes

>[!CAUTION]
>
>Las tablas personalizadas no se depuran con el proceso de limpieza estándar. Aunque esto puede no ser necesario en el primer día, no olvide crear un proceso de depuración para las tablas personalizadas, ya que esto podría provocar problemas de rendimiento.

Existen varias soluciones para minimizar la necesidad de registros en Adobe Campaign:
* Exporte los datos en un almacén de datos fuera de Adobe Campaign.
* Genere valores agregados que utilicen menos espacio mientras sean suficientes para sus prácticas de marketing. Por ejemplo, no necesita el historial completo de transacciones con el cliente en Adobe Campaign para realizar un seguimiento de las últimas compras.

Puede declarar el atributo &quot;deleteStatus&quot; en un esquema. Es más eficaz marcar el registro como eliminado y posponer la eliminación en la tarea de limpieza.

: globo_voz: Como usuario de Cloud Services administrados, póngase en contacto con los consultores de Adobe o administradores técnicos para obtener más información sobre la retención o si necesita configurar la retención para tablas personalizadas.

## Rendimiento {#performance}

Para garantizar un mejor rendimiento en cualquier momento, siga las prácticas recomendadas a continuación.

### Recomendaciones generales {#general-recommendations}

* Evite utilizar operaciones como &quot;CONTIENE&quot; en consultas. Si sabe para qué se espera y desea que se filtre, aplique la misma condición con un &quot;EQUAL TO&quot; u otros operadores de filtro específicos.
* Intente asegurarse de que los procesos como la importación y exportación se producen fuera del horario laboral.
* Asegúrese de que haya una programación para todas las actividades diarias y cumpla con la programación.
* Si uno o varios de los procesos diarios fallan y si es obligatorio ejecutarlo ese mismo día, asegúrese de que no haya procesos conflictivos en ejecución cuando se inicie el proceso manual, ya que esto podría afectar al rendimiento del sistema.
* Asegúrese de que ninguna de las campañas diarias se ejecuta durante el proceso de importación o cuando se ejecuta cualquier proceso manual.
* Utilice una o varias tablas de referencia en lugar de duplicar un campo en cada fila. Al utilizar pares clave/valor, se prefiere elegir una clave numérica.
* Una cadena corta sigue siendo aceptable. En caso de que las tablas de referencias ya estén implementadas en un sistema externo, reutilizar la misma facilitará la integración de datos con Adobe Campaign.

### Relaciones de uno a varios {#one-to-many-relationships}

* El diseño de datos afecta a la capacidad de uso y la funcionalidad. Si diseña su modelo de datos con muchas relaciones de uno a varios, a los usuarios les resultará más difícil construir una lógica significativa en la aplicación. La lógica de filtro &quot;uno a varios&quot; puede resultar difícil para los especialistas en marketing que no son técnicos construir y comprender correctamente.
* Es bueno tener todos los campos esenciales en una tabla porque facilita a los usuarios la creación de consultas. A veces también es bueno para el rendimiento duplicar algunos campos entre tablas si puede evitar una unión.
* Algunas funcionalidades integradas no podrán hacer referencia a relaciones &quot;uno a varios&quot;, por ejemplo, la fórmula de Ponderación de ofertas y los Envíos.

## Tablas grandes {#large-tables}

Adobe Campaign se basa en motores de base de datos de terceros. Según el proveedor, la optimización del rendimiento para tablas más grandes puede requerir un diseño específico.

A continuación se describen algunas prácticas recomendadas comunes que deben seguirse al diseñar el modelo de datos con tablas grandes y uniones complejas.

* Cuando utilice tablas de destinatarios personalizadas adicionales, asegúrese de que tiene una tabla de registro dedicada para cada asignación de envío.
* Reduzca el número de columnas, especialmente identificando aquellas que no se utilizan.
* Optimice las relaciones del modelo de datos evitando las uniones complejas, como las uniones en varias condiciones o varias columnas.
* Para las claves de unión, utilice siempre datos numéricos en lugar de cadenas de caracteres.
* Reduzca al máximo la profundidad de la retención de registros. Si necesita un historial más profundo, puede acumular cálculos y/o administrar tablas de registro personalizadas para almacenar un historial más grande.

### Tamaño de las tablas {#size-of-tables}

El tamaño de la tabla es una combinación del número de registros y el número de columnas por registro. Ambos pueden afectar al rendimiento de las consultas.

* Una tabla **de tamaño pequeño** es similar a la tabla Envío.
* Una tabla **de tamaño medio** es el mismo que el tamaño de la tabla de destinatarios. Tiene un registro por cliente.
* Una tabla **de tamaño grande** es similar a la tabla Registro amplio. Tiene muchos registros por cliente.
Por ejemplo, si la base de datos contiene 10 millones de destinatarios, la tabla Registro amplio contiene entre 100 y 200 millones de mensajes y la tabla Entrega contiene unos pocos miles de registros.

El número de filas también afecta al rendimiento. La base de datos de Adobe Campaign no está diseñada para almacenar datos históricos que no se utilizan activamente con fines de segmentación o personalización; se trata de una base de datos operativa.

Para evitar cualquier problema de rendimiento relacionado con el alto número de filas, mantenga los registros necesarios en la base de datos. Cualquier otro registro debe exportarse a un almacén de datos de terceros y eliminarse de la base de datos operativa de Adobe Campaign.

Estas son algunas prácticas recomendadas con respecto al tamaño de las tablas:

* Diseñe tablas grandes con menos campos y datos numéricos.
* No utilice un gran tipo de columna para almacenar números pequeños como valores booleanos.
* Elimine las columnas no utilizadas de la definición de tabla.
* No mantenga los datos históricos o inactivos en la base de datos de Adobe Campaign (exportación y limpieza).
