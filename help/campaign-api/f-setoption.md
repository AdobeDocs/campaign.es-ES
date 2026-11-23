---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 8%
---
# setOption

Cambia el valor de una opción de la tabla de opciones.

```text
setOption (name, value, description )
```

## Parámetros

**nombre** Nombre de la opción.

**valor** Valor de la opción.

**description** Valor de la descripción (opcional).

## Valor devuelto

Ninguna.

## Observaciones

Los diferentes tipos de datos son:

* texto,
* entero,
* coma flotante,
* Fecha y hora,
* texto largo

Tenga en cuenta que el tipo longText y integer no se puede crear desde la API.

Para estos dos tipos, primero debe crear la opción desde la consola y, a continuación, puede administrar los valores mediante la API setOption.

**Ejemplo:**

```javascript
               //create option of type Date+Time'
               var ourDate = getCurrentDate();
               setOption("testOptionDateTime",ourDate,"option of type Date+Time");
                              
               //create option of type Floating point'
               setOption("testOptionFloat",1,"option of type Floating point");
               
               //create option of type Text'
               setOption("testOptionText","I am a text","option of type Text");               
           
```

Si desea eliminar la descripción, debe llamar a la API con una descripción vacía (setOption(name,value,&quot;&quot;&quot;).

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
