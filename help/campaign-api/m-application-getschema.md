---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 9%
---
# getSchema

Devuelve una asignación a un esquema de Adobe Campaign o nulo si el esquema no existe.

```text
getSchema (name [, checkIfUpdated ])
```

## Parámetros

**nombre** Nombre de esquema completo.

**checkIfUpdated** Compruebe si el esquema se ha actualizado en la caché. No afecta al esquema si ya se ha creado una instancia en el script.

## Valor devuelto

Una asignación de esquema (consulte el objeto [Schema](c-schema.md)) o el método inicia una excepción si ningún esquema coincide con el nombre.

## Observaciones

Todos los esquemas creados en una secuencia de comandos permanecen asignados en la memoria hasta el final de la secuencia de comandos. Ejemplo:

```javascript
      var schema = application.getSchema("nms:recipient")
```

## Funciones

**Método de clase:** [Aplicación](c-application.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
