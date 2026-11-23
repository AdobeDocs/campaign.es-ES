---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 9%
---
# getDBMSType

Devuelve el tipo de servidor de la base de datos.

```text
getDBMSType ( [name ] [, checkIfUpdated ])
```

## Parámetros

**nombre** Nombre del origen de datos.

**checkIfUpdated** Compruebe que el esquema se haya actualizado en la caché. Sin impacto si el esquema ya tiene instancias en el script.

## Valor devuelto

Cadena de texto que contiene el tipo de servidor de la base de datos.

## Observaciones

Si no se especifica el origen de datos, la función utiliza &#39;nms:default&#39; de forma predeterminada. El origen de datos debe existir; de lo contrario, se genera una excepción.

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
