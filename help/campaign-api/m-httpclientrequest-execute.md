---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 6%
---
# ejecutar

Ejecuta la consulta HTTP.

```text
execute ( [hasProxy ] [, async ] [, reuseaddr ] [, context ] [, timeout ])
```

## Parámetros

**hasProxy** Boolean establecido en true si necesita utilizar un proxy HTTP. De forma predeterminada, se establece en false.

**async** Boolean establecido en true si la consulta es asincrónica. De forma predeterminada, se establece en false.

**reuseaddr** valor booleano establecido en true si el socket subyacente debe permitir la reutilización de direcciones locales. De forma predeterminada, se establece en false.

**context** El contexto es cualquier objeto que se reenviará al segundo argumento de la función [complete](p-httpclientrequest-complete.md) en caso de una consulta asincrónica.De forma predeterminada, se establece en null.

**tiempo de espera** máximo en milisegundos en caso de consulta asincrónica. Si no se define este parámetro, el tiempo de espera es de 5 minutos.

## Valor devuelto

Ninguna.

## Observaciones

Si la conexión HTTP falla, se genera una excepción. La propiedad [response](p-httpclientrequest-response.md) solo se vuelve válida después de una llamada correcta a la función execute. Ejemplo:

```javascript
          
        var http = new HttpClientRequest("http://www.google.com")
        http.method = "GET"
        // Note: Here, http.response == undefined
        http.execute()
        var response = http.response
      
```

## Funciones

**Método de clase:** [HttpClientRequest](c-httpclientrequest.md)

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
