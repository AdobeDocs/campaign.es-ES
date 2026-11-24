---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 5%
---
# sqlGetDouble

Devuelve un número resultante de una consulta SQL.

```text
sqlGetDouble (query [, value1, ... ])
```

## Parámetros

**query** La consulta SQL.

**value1, ...** Variables de la consulta SQL.

## Valor devuelto

El valor numérico que coincide con la consulta.

## Observaciones

Las variables reemplazan los parámetros del comando. El tipo de variable debe coincidir con el parámetro declarado en el comando. Estas variables están disponibles en una declaración de tipo &quot;select&quot; o &quot;update&quot;. Tenemos los siguientes tipos:

* Cadena de $(sz)
* Nota: $(m)
* $(l) long
* $(s) corto(s)
* $(b) byte
* $(d) doble
* $(f) flotante
* $(ts) marca de tiempo
* Fecha de $(dt)
* Hora de $(tm)
* $(dur) intervalo de tiempo en milisegundos (ms)

Los siguientes parámetros de sustitución (solo válidos para una &quot;actualización&quot;) se sustituyen automáticamente por un valor y no necesitan una variable vinculada.

* $(id) genera un identificador
* $(id:NmsTrackingLogId) genera un identificador utilizando una secuencia específica
* $(curdate) Fecha y hora actuales

El uso de variables no altera el rendimiento de Adobe Campaign. La consulta SQL debe seleccionar una sola línea y un único campo de tipo numérico. El operador debe tener el derecho &quot;sql&quot; para utilizar esta función; de lo contrario, se genera una excepción. Ejemplo:

```javascript
      var number = sqlGetDouble('select price from priceTable where sTaxes =$(d) order by tsCreated DESC LIMIT 1', taxes)
```

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
