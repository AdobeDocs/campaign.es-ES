---
title: Restringir la vista IP
description: Obtenga información sobre cómo restringir la vista IP
feature: PI, Privacy
role: Developer
level: Intermediate, Experienced
exl-id: 1b833745-71d7-430d-ac7d-c830c78ea232
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# Restringir la vista IP{#restricting-pii-view}

## Información general {#overview}

Si necesita que los usuarios de marketing puedan acceder a los registros de datos, pero no desea que vean la información personal (PI) del destinatario, como el nombre, los apellidos o la dirección de correo electrónico, aplique las directrices que se indican a continuación para proteger la privacidad y evitar que los operadores de campaña habituales utilicen indebidamente los datos.

## Implementación {#implementation}

Se ha añadido a los esquemas un atributo específico que se puede aplicar a cualquier elemento o atributo, complementa el atributo existente **[!UICONTROL visibleIf]**. Este atributo es: **[!UICONTROL accessibleIf]**. Cuando contiene una expresión XTK relacionada con el contexto del usuario actual, puede aprovechar **[!UICONTROL HasNamedRight]** o **[!UICONTROL $(login)]**, por ejemplo.

A continuación, puede encontrar un ejemplo de una extensión de esquema de destinatario que muestra este uso:

```
<srcSchema desc="Recipient table (profiles" entitySchema="xtk:srcSchema" extendedSchema="xxl:nmsRecipientXl"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
           name="recipient" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Recipient table (profiles" img="xxl:recipient.png" label="Recipients"
           labelSingular="Recipient" name="recipient">
    <attribute name="firstName" accessibleIf="$(login)=='admin'"/>
    <attribute name="lastName" visibleIf="$(login)=='admin'"/>
    <attribute name="email" accessibleIf="$(login)=='admin'"/>
  </element>
</srcSchema>
```

Las propiedades principales son:

* **[!UICONTROL visibleIf]** : oculta los campos de los metadatos, por lo que no se puede acceder a ellos dentro de una vista de esquema, una selección de columna o un generador de expresiones. Pero esto no oculta ningún dato. Si el nombre del campo se introduce manualmente en una expresión, se muestra el valor.
* **[!UICONTROL accessibleIf]** : oculta los datos (reemplazándolos por valores vacíos) de la consulta resultante. Si visibleIf está vacío, obtiene la misma expresión que **[!UICONTROL accessibleIf]**.

Estas son las consecuencias de utilizar este atributo en Campaign:

* Los datos no se mostrarán mediante el editor de consultas genérico en la consola.
* Los datos no estarán visibles en las listas de información general y en la lista de registros (consola).
* Los datos pasarán a ser de solo lectura en la vista detallada.
* Los datos solo se pueden utilizar dentro de los filtros (lo que significa que, con algunas estrategias de dicotomía, aún puede adivinar los valores).
* Cualquier expresión que se cree mediante un campo restringido queda restringida a: lower(@email) se vuelve tan accesible como @email.
* En un flujo de trabajo, puede añadir la columna restringida a la población de destino como una columna adicional de la transición, pero los usuarios de Adobe Campaign siguen sin poder acceder a ella.
* Al almacenar la población de destino en un grupo (lista), las características de los campos almacenados son las mismas que la fuente de los datos.
* De forma predeterminada, el código JS no puede acceder a los datos.

## Recomendaciones {#recommendations}

En cada entrega, las direcciones de correo electrónico se copian en la variable **[!UICONTROL broadLog]** y el **[!UICONTROL forecastLog]** tablas: como consecuencia, esos campos también deben protegerse.

A continuación se muestra un ejemplo de extensión de tabla de registro para implementar esto:

```
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:broadLogRcp" img="nms:broadLog.png"
           label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:broadLog.png" label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema desc="Delivery messages being prepared." entitySchema="xtk:srcSchema"
           extendedSchema="nms:tmpBroadcast" img="" label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Delivery messages being prepared." label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:excludeLogRcp" img="nms:excludeLog.png"
           label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:excludeLog.png" label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
```

>[!CAUTION]
>
>Esta restricción se aplica solo a los usuarios no técnicos y no aísla los datos: un usuario técnico, con permisos relacionados, puede recuperar datos.
