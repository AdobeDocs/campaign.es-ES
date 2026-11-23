---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 13%
---
# integridad

Devuelve el tipo de integridad del vínculo.

```text
integrity
```

## Observaciones

La propiedad puede tener uno de los siguientes valores:

* Vínculo de tipo Schema.INTEGRITY\_NORMAL - &quot;Normal&quot;.
* Schema.INTEGRITY\_DEFINE: vínculo de tipo &quot;Definir&quot;.
* Schema.INTEGRITY\_NEUTRAL: vínculo de tipo &quot;neutral&quot;.
* Schema.INTEGRITY\_USED: vínculo de tipo &quot;usado&quot;.
* Schema.INTEGRITY\_OWN: vínculo de tipo &quot;own&quot;.
* Schema.INTEGRITY\_OWNCOPY: vínculo de tipo &quot;owncopy&quot;.

## Funciones

**Propiedad de la clase:** [NodoEsquema](c-schemanode.md)

**Sólo lectura:**

Sí

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
