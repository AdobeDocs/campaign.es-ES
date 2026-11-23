---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# getCurrentDate

Devuelve la fecha actual del servidor de la base de datos.

```text
getCurrentDate ()
```

## Parámetros

Ninguna.

## Valor devuelto

La fecha actual del servidor de la base de datos.

## Observaciones

Ejemplo:

```javascript
      date = formatDate(getCurrentDate(),"%4Y/%2M/%2D %02H:%02N:%02S")
```

Para obtener más información sobre la función formatDate(), consulte [formatDate(date, format)](f-formatdate.md)

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
