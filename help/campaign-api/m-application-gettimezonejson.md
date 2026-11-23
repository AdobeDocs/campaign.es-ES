---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 5%
---
# getTimezoneJson

Devuelve una cadena de caracteres que es la representación JSON de la lista de diferencias horarias con la hora UTC y su fecha de inicio en comparación con el periodo UNIX de una zona horaria.

```text
getTimezoneJson ( [timezone ])
```

## Parámetros

**huso horario**: nombre de la zona horaria para la que necesita devolver la lista de diferencias horarias en comparación con UTC. Cada diferencia horaria está vinculada a una fecha de inicio aplicable hasta la siguiente fecha de inicio. Si no se devuelve ningún valor, utiliza la zona horaria del operador predeterminado.

## Valor devuelto

Devuelve una cadena de caracteres que es la representación JSON de las diferencias horarias que se aplican en función de las fechas. La cadena JSON devuelta se evalúa en una tabla de {startDate, offset} parejas. La cadena de caracteres devuelta tiene la siguiente forma:

```javascript
[
  {"startDate" : -1855958901000, "offset" : 0},
  {"startDate" : -1689814800000, "offset" : 3600000}
]
```

* startDate es la hora Posix a partir de la cual se aplica el lapso.
* desplazamiento es el valor en milisegundos de la diferencia horaria con UTC. Por ejemplo, UTC+02:00 es igual a 7200000.

## Observaciones

Se llama a getTimezoneJson a través de la instancia de la aplicación.

```javascript
var tzList = eval(application.getTimezoneJson());
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
