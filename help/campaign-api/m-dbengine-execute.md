---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%
---
# ejecutar

Ejecuta un comando SQL.

```text
execute (command [, value1, ... ])
```

## Parámetros

**comando** comando SQL.

**value1, ...** Variables del comando.

## Valor devuelto

El número de registros actualizados o insertados, si corresponde, al comando ejecutado; en caso contrario, cero.

## Observaciones

Las variables se utilizan para sustituir los parámetros del comando. El tipo de variable debe coincidir con el tipo declarado en el comando. Los tipos son los siguientes:

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
* $(dur) tiempo de espera en milisegundos (ms)

Los siguientes parámetros sustitutos se sustituyen automáticamente por un valor y no requieren una variable asociada.

* $(id) genera un identificador
* $(id:NmsTrackingLogId) genera un identificador gracias a una secuencia específica
* $(curdate) Fecha y hora actuales

El operador necesita derechos &quot;sql&quot; para utilizar esta función; de lo contrario, se genera una excepción.

## Funciones

**Método de clase:** [DBEngine](c-dbengine.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
