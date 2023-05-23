---
title: Prácticas recomendadas del modelo de datos
description: Conozca las prácticas recomendadas de extensión del modelo de datos de Campaign
feature: Data Model
role: User, Developer
level: Beginner, Intermediate
exl-id: bdd5e993-0ce9-49a8-a618-ab0ff3796d49
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '2717'
ht-degree: 4%

---

# Prácticas recomendadas del modelo de datos{#data-model-best-practices}

Este documento describe las recomendaciones clave al diseñar el modelo de datos de Adobe Campaign.

El sistema Adobe Campaign es muy flexible y se puede ampliar más allá de la implementación inicial. Sin embargo, aunque las posibilidades son infinitas, es fundamental tomar decisiones sabias y construir bases sólidas para empezar a diseñar el modelo de datos.

Para comprender mejor las tablas integradas de Campaign y cómo se relacionan entre sí, consulte [esta sección](datamodel.md).

![](../assets/do-not-localize/glass.png) Leer más [esta sección](schemas.md) para empezar a usar los esquemas de Campaign.

![](../assets/do-not-localize/glass.png) Obtenga información sobre cómo configurar esquemas de extensión para ampliar el modelo de datos conceptuales de la base de datos de Adobe Campaign en [esta página](extend-schema.md).

## Arquitectura del modelo de datos {#data-model-architecture}

Adobe Campaign es un potente sistema de administración de campañas en canales múltiples que le ayuda a alinear sus estrategias en línea y sin conexión para crear experiencias personalizadas con los clientes.

### Enfoque centrado en el cliente {#customer-centric-approach}

Aunque la mayoría de los proveedores de correo electrónico se comunican con los clientes mediante un enfoque centrado en listas, Adobe Campaign depende de una base de datos relacional para aprovechar una vista más amplia de los clientes y sus atributos.

Para acceder a la descripción de cada tabla, vaya a **[!UICONTROL Admin > Configuration > Data schemas]**, seleccione un recurso de la lista y haga clic en **[!UICONTROL Documentation]** pestaña.


>[!NOTE]
>
>Adobe Campaign permite crear un [tabla de destinatarios personalizada](custom-recipient.md). Sin embargo, en la mayoría de los casos, se recomienda aprovechar el integrado [Tabla de destinatarios](datamodel.md#ootb-profiles) que ya tiene tablas y funciones adicionales creadas previamente.

### Datos para Adobe Campaign {#data-for-campaign}

¿Qué datos deben enviarse a Adobe Campaign? Es fundamental determinar los datos necesarios para las actividades de marketing.

>[!NOTE]
>
>Adobe Campaign no es un almacén de datos ni una herramienta de creación de informes. Por lo tanto, no intente importar todos los clientes posibles y su información asociada en Adobe Campaign, ni importe datos que solo se utilizarán para crear informes.

Para tomar la decisión de si un atributo sería necesario o no en Adobe Campaign, pregúntese si caería dentro de una de estas categorías:

* Atributo utilizado para **segmentación**
* Atributo utilizado para **procesos de administración de datos** (cálculo acumulado, por ejemplo)
* Atributo utilizado para **personalización**

Si no entra en ninguna de estas situaciones, lo más probable es que no necesite este atributo en Adobe Campaign.

### Elección de tipos de datos {#data-types}

Para garantizar la buena arquitectura y el rendimiento de su sistema, siga las prácticas recomendadas a continuación para configurar los datos en Adobe Campaign.

* En una tabla grande, se pueden insertar campos numéricos o de cadena y agregar vínculos a tablas de referencia (cuando se trabaja con listas de valores).
* El **expr** El atributo permite definir un atributo de esquema como un campo calculado en lugar de como un valor físico definido en una tabla. Esto puede permitir el acceso a la información en un formato diferente (como por ejemplo, edad y fecha de nacimiento) sin necesidad de almacenar ambos valores. Esta es una buena manera de evitar la duplicación de campos. Por ejemplo, la tabla Destinatario utiliza una expresión para el dominio, que ya está presente en el campo de correo electrónico.
* Sin embargo, cuando el cálculo de la expresión es complejo, no se recomienda utilizar la variable **expr** como cálculo sobre la marcha puede afectar al rendimiento de las consultas.
* El **XML** El tipo es una buena manera de evitar la creación de demasiados campos. Pero también ocupa espacio en disco, ya que utiliza una columna CLOB en la base de datos. También puede generar consultas SQL complejas y afectar al rendimiento.
* La longitud de un **cadena** El campo siempre debe definirse con la columna. De forma predeterminada, la longitud máxima en Adobe Campaign es de 16 K, pero Adobe recomienda mantener el campo más corto si ya sabe que el tamaño no excederá una longitud más corta.
* Es aceptable tener un campo más corto en Adobe Campaign que en el sistema de origen si está seguro de que el tamaño en el sistema de origen se ha sobreestimado y no se alcanzaría. Esto podría significar una cadena más corta o un entero más pequeño en Adobe Campaign.

### Elección de campos {#choice-of-fields}

Es necesario almacenar un campo en una tabla si tiene un propósito de segmentación o personalización. En otras palabras, si un campo no se utiliza para enviar un correo electrónico personalizado o se utiliza como criterio en una consulta, ocupará innecesariamente espacio en disco.

### Elección de claves {#choice-of-keys}

Además de las **autouuid** y **autopk** definido de forma predeterminada en la mayoría de las tablas, debe considerar la posibilidad de agregar algunas claves lógicas o empresariales (número de cuenta, número de cliente, etc.). Se puede utilizar más adelante para importaciones/reconciliación o paquetes de datos. Para obtener más información, consulte [Identificadores](#identifiers).

Las claves eficientes son esenciales para el rendimiento. Con Snowflake, puede insertar tipos de datos numéricos o basados en cadenas como claves para tablas.

>[!NOTE]
>
>El **autouuid** el atributo solo se aplica a [Implementaciones empresariales (FDAC)](../architecture/enterprise-deployment.md).

## Identificadores {#identifiers}

Los recursos de Adobe Campaign tienen tres identificadores y es posible añadir uno adicional.

En la tabla siguiente se describen estos identificadores y su propósito.

| Identifier | Descripción | Prácticas recomendadas |
|--- |--- |--- |
| Identificación | <ul><li>El ID es la clave primaria física de una tabla de Adobe Campaign. Para tablas integradas, es un ID único universal (UUID)</li><li>Este identificador debe ser único. </li><li>Un UUID puede ser visible en una definición de esquema.</li></ul> | <ul><li>Los identificadores generados automáticamente no deben utilizarse como referencia en un flujo de trabajo o en una definición de paquete.</li><li>El ID de una tabla es un UUID y este tipo no debe cambiarse.</li></ul> |
| Nombre (o nombre interno) | <ul><li>Esta información es un identificador único de un registro de una tabla. Este valor se puede actualizar de forma manual, normalmente con un nombre generado.</li><li>Este identificador mantiene su valor cuando se implementa en una instancia diferente de Adobe Campaign y no debe estar vacío.</li></ul> | <ul><li>Cambie el nombre del registro generado por Adobe Campaign si el objeto debe implementarse de un entorno a otro.</li><li>Cuando un objeto tiene un atributo namespace (*esquema* por ejemplo), este área de nombres común se aprovechará en todos los objetos personalizados creados. Algunas áreas de nombres reservadas no deben usarse: *nms*, *xtk*, etc.  Tenga en cuenta que algunas áreas de nombres solo son internas. [Más información](schemas.md#reserved-namespaces).</li><li>Cuando un objeto no tiene ningún área de nombres (*workflow* o *envío* por ejemplo), esta noción de área de nombres se agregaría como prefijo de un objeto de nombre interno: *namespaceMyObjectName*.</li><li>No utilice caracteres especiales como el espacio &quot;&quot;, el punto y coma &quot;:&quot; o el guión &quot;-&quot;. Todos estos caracteres se sustituirían por un guion bajo &quot;_&quot; (carácter permitido). Por ejemplo, &quot;abc-def&quot; y &quot;abc:def&quot; se almacenarían como &quot;abc_def&quot; y se sobrescribirían mutuamente.</li></ul> |
| Etiqueta | <ul><li>La etiqueta es el identificador comercial de un objeto o registro en Adobe Campaign.</li><li>Este objeto permite espacios y caracteres especiales.</li><li>No garantiza la exclusividad de un registro.</li></ul> | <ul><li>Se recomienda determinar una estructura para las etiquetas de objetos.</li><li>Esta es la solución más fácil de usar para identificar un registro u objeto para un usuario de Adobe Campaign.</li></ul> |

En el contexto de un [Implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), la clave principal de Adobe Campaign es un UUID generado automáticamente para todas las tablas integradas. También se puede utilizar un UUID para tablas personalizadas. [Más información](../architecture/keys.md)

Incluso si el número de ID es infinito, debe cuidar el tamaño de la base de datos para garantizar un rendimiento óptimo. Para evitar cualquier problema, asegúrese de ajustar la configuración de depuración de la instancia. Para obtener más información, consulte [esta sección](#data-retention).


## Claves internas personalizadas {#custom-internal-keys}

Las claves principales son necesarias para cada tabla creada en Adobe Campaign.

La mayoría de las organizaciones están importando registros de sistemas externos. Aunque la clave física de la tabla de destinatarios es el atributo &quot;id&quot;, es posible determinar además una clave personalizada.

Esta clave personalizada es la clave principal del registro real en el sistema externo que alimenta a Adobe Campaign.

Al crear una tabla personalizada, tiene dos opciones:
* Una combinación de clave generada automáticamente (id) y clave interna (personalizada). Esta opción es interesante si la clave del sistema es una clave compuesta o no un número entero. Con Snowflake, los enteros o las claves basadas en cadenas proporcionarán un mayor rendimiento en tablas grandes y se unirán con otras tablas.
* Uso de la clave principal como clave principal externa del sistema. Esta solución suele ser la preferida, ya que simplifica el método de importación y exportación de datos, con una clave coherente entre los distintos sistemas. **Autouuid** debe deshabilitarse si la clave se denomina &quot;id&quot; y se espera que se rellene con valores externos (no generados automáticamente).

>[!CAUTION]
>
>* Un autouuid no debe utilizarse como referencia en flujos de trabajo.
> * El **autouuid** el atributo solo se aplica a [Implementaciones empresariales (FDAC)](../architecture/enterprise-deployment.md).
>


## Vínculos y cardinalidad {#links-and-cardinality}

### Vínculos {#links}

Tenga cuidado con la integridad &quot;propia&quot; en tablas grandes. La eliminación de registros que tienen tablas grandes en integridad &quot;propia&quot; puede detener potencialmente la instancia. La tabla está bloqueada y las eliminaciones se realizan una por una. Por lo tanto, es mejor utilizar la integridad &quot;neutral&quot; en tablas secundarias que tengan grandes volúmenes.

Declarar un vínculo como una unión externa no es bueno para el rendimiento. El registro de ID cero emula la funcionalidad de unión externa. En el contexto de un [Implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), no es necesario declarar uniones externas si el vínculo utiliza el **autouuid**.

Aunque es posible unir cualquier tabla en un flujo de trabajo, Adobe recomienda definir vínculos comunes entre recursos directamente en la definición de la estructura de datos.

El vínculo debe definirse en consonancia con los datos reales de las tablas. Una definición incorrecta podría afectar a los datos recuperados mediante vínculos como, por ejemplo, la duplicación inesperada de registros.

Asigne un nombre al vínculo que sea coherente con el nombre de la tabla: el nombre del vínculo debe ayudar a comprender qué es la tabla distante.

No asigne un nombre a un vínculo con &quot;id&quot; como sufijo. Por ejemplo, asígnele el nombre &quot;transaction&quot; en lugar de &quot;transactionId&quot;.

De forma predeterminada, Adobe Campaign crea un vínculo con la clave principal de la tabla externa. Para una mayor claridad, es preferible definir explícitamente la unión en la definición del vínculo.

### Cardinalidad {#cardinality}

Cuando diseñe un vínculo, asegúrese de que el registro de destino sea único cuando se haya declarado una relación 1-1. De lo contrario, la unión puede devolver varios registros cuando solo se espera uno. Esto provoca errores durante la preparación del envío cuando &quot;la consulta devuelve más filas de lo esperado&quot;. Establezca el nombre del vínculo con el mismo nombre que el esquema de destino.

Defina un vínculo con una cardinalidad (1-N) en el esquema del lado (1). Por ejemplo, la relación Destinatario (1) - (N) Transacción debe definirse en el esquema de transacción.

Tenga en cuenta que una cardinalidad inversa de un vínculo es (N) de forma predeterminada. Es posible definir un vínculo (1-1) añadiendo el atributo revCardinality=&#39;single&#39; a la definición del vínculo.

Si el vínculo inverso no debe ser visible para el usuario, puede ocultarlo con la definición del vínculo revLink=&#39;_NINGUNO_&#39;. Un buen caso de uso para esto es definir un vínculo desde el destinatario a la última transacción completada, por ejemplo. Solo necesita ver el vínculo del destinatario a la última transacción y no se requiere que ningún vínculo inverso sea visible desde la tabla de transacciones.

Los vínculos que realizan una unión externa (1-0..1) deben utilizarse con cuidado, ya que afectarán al rendimiento del sistema.

## Retención de datos {#data-retention}

Adobe Campaign no es un almacén de datos ni una herramienta de creación de informes. Por lo tanto, para garantizar el buen rendimiento de la solución de Adobe Campaign, el crecimiento de la base de datos debe mantenerse bajo control. Para lograrlo, puede ser útil seguir algunas de las prácticas recomendadas a continuación.

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
>Las tablas personalizadas no se depuran con el proceso de limpieza estándar. Aunque esto puede no ser necesario en el primer día, no olvide crear un proceso de depuración para las tablas personalizadas, ya que podría provocar desafíos de rendimiento.

Hay algunas soluciones para minimizar la necesidad de registros en Adobe Campaign:
* Exporte los datos en un almacén de datos fuera de Adobe Campaign.
* Genere valores agregados que utilicen menos espacio a la vez que sean suficientes para sus prácticas de marketing. Por ejemplo, no necesita el historial completo de transacciones de clientes en Adobe Campaign para realizar un seguimiento de las últimas compras.

Puede declarar el atributo &quot;deleteStatus&quot; en un esquema. Es más eficaz marcar el registro como eliminado y posponer la eliminación en la tarea de limpieza.

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, póngase en contacto con los consultores o administradores técnicos de Adobe para obtener más información sobre la retención o si necesita establecer la retención de tablas personalizadas.

## Rendimiento {#performance}

Para garantizar un mejor rendimiento en cualquier momento, siga las prácticas recomendadas a continuación.

### Recomendaciones generales {#general-recommendations}

* Evite utilizar operaciones como &quot;CONTAINS&quot; en consultas. Si sabe lo que se espera y desea filtrar, aplique la misma condición con un operador &quot;EQUAL TO&quot; u otro operador de filtro específico.
* Intente y asegúrese de que los procesos de importación y exportación se produzcan fuera del horario laboral.
* Asegúrese de que haya un horario para todas las actividades diarias y apéguese al horario.
* Si uno o varios de los procesos diarios fallan y si es obligatorio ejecutarlos ese mismo día, asegúrese de que no haya procesos en conflicto ejecutándose cuando se inicie el proceso manual, ya que esto podría afectar el rendimiento del sistema.
* Asegúrese de que ninguna de las campañas diarias se ejecute durante el proceso de importación o cuando se ejecute cualquier proceso manual.
* Utilice una o varias tablas de referencia en lugar de duplicar un campo en cada fila. Al utilizar pares clave/valor, se prefiere elegir una clave numérica.
* Una cadena corta sigue siendo aceptable. Si las tablas de referencias ya están en su lugar en un sistema externo, la reutilización de las mismas facilitará la integración de datos con Adobe Campaign.

### Relaciones &quot;uno a varios&quot; {#one-to-many-relationships}

* El diseño de datos afecta la facilidad de uso y la funcionalidad. Si diseña el modelo de datos con muchas relaciones &quot;uno a varios&quot;, a los usuarios les resulta más difícil construir una lógica significativa en la aplicación. La lógica de filtro uno a varios puede resultar difícil para los especialistas en marketing no técnico de construir y comprender correctamente.
* Es bueno tener todos los campos esenciales en una tabla porque facilita a los usuarios la creación de consultas. A veces también es bueno para el rendimiento duplicar algunos campos entre tablas si se puede evitar una combinación.
* Algunas funcionalidades integradas no podrán hacer referencia a relaciones &quot;uno a varios&quot;, por ejemplo, la fórmula de ponderación de oferta y las entregas.

## Mesas grandes {#large-tables}

Adobe Campaign se basa en motores de base de datos de terceros. Según el proveedor, la optimización del rendimiento para tablas más grandes puede requerir un diseño específico.

A continuación se describen algunas prácticas recomendadas comunes que deben seguirse al diseñar el modelo de datos con tablas grandes y uniones complejas.

* Cuando utilice tablas de destinatarios personalizadas adicionales, asegúrese de tener una tabla de registro dedicada para cada asignación de entrega.
* Reduzca la cantidad de columnas, especialmente identificando las que no se utilizan.
* Optimice las relaciones del modelo de datos evitando uniones complejas, como uniones en varias condiciones o varias columnas.
* Para las claves de combinación, puede utilizar valores numéricos o basados en cadenas.
* Reduzca al máximo la profundidad de la retención de registros. Si necesita un historial más profundo, puede acumular cálculos o gestionar tablas de registro personalizadas para almacenar un historial más grande.

### Tamaño de las tablas {#size-of-tables}

El tamaño de la tabla es una combinación del número de registros y el número de columnas por registro. Ambos pueden afectar al rendimiento de las consultas.

* A **de pequeño tamaño** es similar a la tabla Delivery.
* A **tamaño medio** es el mismo tamaño que la tabla de destinatarios. Tiene un registro por cliente.
* A **de gran tamaño** es similar a la tabla Registro general. Tiene muchos registros por cliente.
Por ejemplo, si la base de datos contiene 10 millones de destinatarios, la tabla Registro general contiene entre 100 y 200 millones de mensajes, y la tabla Envío contiene algunos miles de registros.

El número de filas también afecta al rendimiento. La base de datos de Adobe Campaign no está diseñada para almacenar datos históricos que no se utilizan de forma activa con fines de segmentación o personalización; se trata de una base de datos operativa.

Para evitar cualquier problema de rendimiento relacionado con el alto número de filas, mantenga únicamente los registros necesarios en la base de datos. Cualquier otro registro debe exportarse a un almacén de datos de terceros y eliminarse de la base de datos operativa de Adobe Campaign.

Estas son algunas prácticas recomendadas con respecto al tamaño de las tablas:

* Diseñe tablas grandes con menos campos y más datos numéricos.
* No utilice el tipo de columna de número grande para almacenar números pequeños como valores booleanos.
* Elimine las columnas no utilizadas de la definición de la tabla.
* No mantenga datos históricos o inactivos en la base de datos de Adobe Campaign (exportación y limpieza).
