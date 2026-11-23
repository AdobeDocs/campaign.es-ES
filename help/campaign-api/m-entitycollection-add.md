---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 6%
---
# añadir

Agrega una nueva entidad a la colección.

```text
add ( [index ], xml)
```

## Parámetros

**índice**: la entidad se agregará en este punto de índice. Si no se especifica este argumento, la entidad se anexará al final de la lista.

**xml** La entidad que se va a insertar en el formulario XML.

## Valor devuelto

El elemento creado.

## Observaciones

En el ejemplo siguiente se muestran dos formas diferentes de agregar un elemento nuevo a una colección. La primera solución pasa la definición completa del elemento al método add(), mientras que la segunda pasa y el elemento &lt;attachment/> vacío asigna los atributos de la manera normal.

```javascript
var delivery = NLWS.nmsDelivery.load("12435")

delivery.attachment.add(
  {attachment: {
    compressMode: "print", filterActive: "false", label: "First File", 
    nameScriptActive: "false", type: "normal", upload: "false", 
    name: { $: "file1.txt" }
  }})

var attach = delivery.attachment.add()
attach.label            = "Second File"
attach.name             = "file2.txt"
attach.compressMode     = "print"
attach.type             = "normal"
attach.filterActive     = false
attach.nameScriptActive = false
attach.upload           = false

delivery.save()
```

Las dos soluciones son equivalentes, pero la segunda permite utilizar los tipos de JavaScript correspondientes a los tipos de atributos, mientras que la primera solo admite cadenas.

## Funciones

**Método de clase:** [EntityCollection](c-entitycollection.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
